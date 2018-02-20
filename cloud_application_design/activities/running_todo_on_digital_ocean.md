# Running _Todo_ on Digital Ocean

## 1. Get a machine (droplet)

* Log into Digital Ocean

* Request a droplet
  * No SSH keys this time
  * Small - 1 Gb

* Get the root password from email

* SSH into the machine

  * Using the machine's IP address
  * As root, e.g.

    * ```$ ssh root@123.124.125.126```

  * Use root password
  * Change to new password

## 2. Load software

```
$ apt-get update
$ apt-get upgrade
$ apt-get install python3-pip
$ pip3 install --upgrade pip
$ pip3 install bottle
$ pip3 install pymongo
$ pip3 install pytest
```

## 3. Set up Git config

Using your own name and email, configure git:

```
$ git config --global user.email "msmart86@kent.edu"
$ git config --global user.name "Maxwell Smart"
```

## 4. Get the application software

```
$ cd ~
$ git clone git clone https://github.com/drdelozier/todo_list.git
```

## 5. Run the application server

```
$ cd todo_list
$ python3 todo.py
```

---

### [[ www.drdelozier.net - Dr. Gregory S. DeLozier - Kent State ]](http://www.drdelozier.net)
