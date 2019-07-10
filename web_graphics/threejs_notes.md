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

In your static directory, create a folder called ```.../three```.

(here we assume your web app is in ```~/sites/web_graphics```...)

```
$ mkdir ~/sites/web_graphics/three
```


