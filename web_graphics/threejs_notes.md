# ThreeJS Class Notes

Here we will set up a small ThreeJS project using static files and conventional JavaScript. 

Feel free to play with WebPack some other day! :-) . Seriously, there is a pretty nice ThreeJS book coming out which includes a lot of directions on how to use the Javascript modular architecture to construct apps. The key words here are "is coming out" meaning it's not really settled yet. Until it is, we're doing it this way for now since I have learned two lessons: We don't have time to both debug and learn WebPack and if we did I don't think PA is the platform for doing it. So it's not really necessary if we get the files directly. 

## Get the ThreeJS files from Git

Make a ```~/projects``` folder and navigate to it. I keep all my basic Git clones in my ```~/projects``` folder. 

```
$ mkdir ~/projects
$ cd ~/projects
```

Get the ```ThreeJS``` code. This will take a few minutes.

```
$ git clone https://github.com/mrdoob/three.js.git
```

## Copy the base ThreeJS files to your web app

In your static directory, create a folder called ```vendor``` and navigate to it. A _vendor_ folder is usually a location that holds code you got from somewhere else and are using in your project. Presumably with permission, of course. 

(here we assume your web app is in ```~/sites/web_graphics```...)

```
$ mkdir ~/sites/web_graphics/static/vendor
$ cd ~/sites/web_graphics/static/vendor
```

Make ```vendor/threejs``` folders and copy the basic file there.

```
$ mkdir -p ~/sites/web_graphics/static/vendor/three.js/build
$ cd ~/sites/web_graphics/static/vendor/three.js/build
$ cp ~/projects/three.js/build/three.min.js .
$ ls
three.min.js
```

Change back to the static directory

```
$ cd ~/sites/web_graphics/static/three
```

## Put the basic HTML page in place

Put this page at ```~/sites/web_graphics/static/three/example-1.html```

```
<html>
	<head>
		<title>My first three.js app</title>
		<style>
			body { margin: 0; }
			canvas { width: 100%; height: 100% }
		</style>
	</head>
	<body>
		<script src="/static/vendor/three.js/build/three.min.js"></script>
		<script>
			var scene = new THREE.Scene();
			var camera = new THREE.PerspectiveCamera( 75, window.innerWidth/window.innerHeight, 0.1, 1000 );

			var renderer = new THREE.WebGLRenderer();
			renderer.setSize( window.innerWidth, window.innerHeight );
			document.body.appendChild( renderer.domElement );

			var geometry = new THREE.BoxGeometry( 1, 1, 1 );
			var material = new THREE.MeshBasicMaterial( { color: 0x00ff00 } );
			var cube = new THREE.Mesh( geometry, material );
			scene.add( cube );

			camera.position.z = 5;

			var animate = function () {
				requestAnimationFrame( animate );

				cube.rotation.x += 0.01;
				cube.rotation.y += 0.01;

				renderer.render( scene, camera );
			};

			animate();
		</script>
	</body>
</html>
```

Don't forget to save the file!

## Check out the result

Refresh the web app and check out the result. 
