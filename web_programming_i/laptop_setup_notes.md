```
Python 3.6

Get it from 
* homebrew (Mac)
* scoop.sh (Win)
* Anaconda (Mac/Win/Linux)
* apt-get using PPA (Linux)
* Python.org (Mac/Win)

Upgrade pip (or pip3)

After moving your code to PA, fix the WSGI file:

   from microblog import app as application  # noqa

### WARNING: These are instructor notes but probably won't entirely work for you
### as you should not be pushing to GH for the class repo. 
### We will work on this on Monday!

# Check to make sure you don't already have a .ssh/id_rsa* key

01:39 ~ $ cd ~
01:39 ~ $ ls .ssh
ls: cannot access .ssh: No such file or directory

# Create a new key, hit return as necessary

01:39 ~ $ ssh-keygen -t rsa -b 4096 -C "gdelozie@kent.edu"   
Generating public/private rsa key pair.
Enter file in which to save the key (/home/gdelozie/.ssh/id_rsa): Created directory '/home/gdelozie/.ssh'.
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /home/gdelozie/.ssh/id_rsa.
Your public key has been saved in /home/gdelozie/.ssh/id_rsa.pub.
The key fingerprint is:
53:3b:5c:d7:84:d5:21:18:ff:5b:eb:74:a6:a4:d9:e2 gdelozie@kent.edu
The key's randomart image is:
+--[ RSA 4096]----+
|           .o. +=|
|           .. oo.|
|          . ... .|
|         o o ..  |
|        S +    ..|
|         . .    +|
|              .+o|
|            .=oo.|
|           .E.o. |
+-----------------+

# verify the new key pair

01:41 ~ $ ls .ssh
id_rsa  id_rsa.pub

# set up the SSH agent

01:42 ~ $ eval "$(ssh-agent -s)"
Agent pid 2906    ~/.ssh/id_rsa                                                                     

# missing a command here for ssh_add, get that from GH, omit the -K part

Identity added: /home/gdelozie/.ssh/id_rsa (/home/gdelozie/.ssh/id_rsa)

01:44 ~ $ cat .ssh/id_rsa.pub
ssh-rsa AAAAB3NzaC1...
...Ast/yI4ICUvj4zOoozngSw== gdelozie@kent.edu

# copy that text from the console, paste into Github at [Settings/SSH key/New Key/...]

01:45 ~ $ ls
README.txt  mysite  mysite.original  tags  web_programming_i
01:46 ~ $ cd web*
01:46 ~/web_programming_i (master)$ git status
On branch master
Your branch is ahead of 'origin/master' by 2 commits.
  (use "git push" to publish your local commits)

nothing to commit, working directory clean

# Select simple push behavior

$ git config --global push.default simple

# verify your remote is HTTPS style

02:12 ~/web_programming_i (master)$ git remote -v
origin  https://github.com/drdelozier/web_programming_i.git (fetch)
origin  https://github.com/drdelozier/web_programming_i.git (push)

# Switch the remote to SSL style

02:13 ~/web_programming_i (master)$ git remote set-url origin git@github.com:drdelozier/web_programming_i.git

# Verify the remote is now SSL style (i.e. "git@github...")

02:14 ~/web_programming_i (master)$ git remote -v
origin  git@github.com:drdelozier/web_programming_i.git (fetch)
origin  git@github.com:drdelozier/web_programming_i.git (push)

# Get the status
02:14 ~/web_programming_i (master)$ git status
On branch master
Your branch is ahead of 'origin/master' by 2 commits.
  (use "git push" to publish your local commits)

nothing to commit, working directory clean

# Should be able to push without a password. First use of location will require yes/no response.

02:14 ~/web_programming_i (master)$ git push
The authenticity of host 'github.com (192.30.253.113)' can't be established.
RSA key fingerprint is 16:27:ac:a5:76:28:2d:36:63:1b:56:4d:eb:df:a6:48.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added 'github.com,192.30.253.113' (RSA) to the list of known hosts.
Counting objects: 11, done.
Delta compression using up to 2 threads.
Compressing objects: 100% (10/10), done.
Writing objects: 100% (10/10), 1.75 KiB | 0 bytes/s, done.
Total 10 (delta 2), reused 0 (delta 0)
remote: Resolving deltas: 100% (2/2), completed with 1 local object.
To git@github.com:drdelozier/web_programming_i.git
   21bf620..fb2661f  master -> master
02:14 ~/web_programming_i (master)$ 

# All done!
