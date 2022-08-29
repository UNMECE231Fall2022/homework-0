# Homework 0
Homework 0 of ECE 231: Intermediate Programming. 

Assigned 08/28/2022. Due 09/03/2022, 11:59 pm.


The goal for this homework is the get acquainted with the software that you are going to be using for the rest of the semester. By the end of this assignment you will achieve two things:

- Get a Linux system working
- Create a GitHub account & have Git working on your linux system

## Getting a Linux system
There are few ways of doing this:

### Linux
If you have a Linux machine (Ubuntu, Pop!OS, Redhat, Linux Mint, etc), please take a look at setting up your Github account and getting Git working on your machine.

### MacOS
You either can download Virtual Box from the section above or download Xcode to run C/C++ software. If you download Xcode you will be programming in your MacOS terminal.

### Windows
#### Virtual Box
You can download a virtual machine that can host a different operating system. I like to use VM Virtual Box (because its free) and the link to download the software is here:

[VM Virtual Box](https://www.virtualbox.org/wiki/Downloads)

Once you have downloaded Virtual Box feel free to download your favorite Linux OS, for first timers I recommend Ubuntu:
[Ubuntu OS](https://ubuntu.com/download)

Some notes about the configuration of the VM, please allocate (if possible) about 20 GB of storage space (at minimum 10 GB), and dedicate half or a quarter of your RAM to the VM.

#### Linux Subsystem for Windows
You either can dowload Virtual Box from the section above or activate and use the Linux system for Windows 10. You can follow the tutorial [here](https://www.maketecheasier.com/install-linux-subsystem-for-windows10/)

## Updating and downloading packages for your terminal (if you have MacOS skip this step)
Once you have set up your Linux (not MacOS) system and have your terminal up and running type the following commands:

```
sudo apt update
sudo apt upgrade -y
sudo apt dist-upgrade -y
```

This should update all current packages installed (and is needed before installing additional packages). After all the packages have been updated, type these commands:

```
sudo apt install vim gcc g++ make cmake git valgrind
```

## Using git and github
[Here](https://www.youtube.com/watch?v=w3jLJU7DT5E) is a quick video on what github is. Please create an account on [github](https://github.com/) and create a new repository. **WHEN YOU SIGN UP FOR GITHUB, PLEASE DO NOT USE YOUR UNM EMAIL, YOU WANT THIS ACCOUNT TO EXIST AFTER YOU GRADUATE. The idea is that you KEEP ADDING CODE THROUGHOUT YOUR CAREER AS A PROGRAMMER**. Feel free to name your new repository anything you want (please keep it appropriate and somewhat professional). Also, initialize your git repo with a README.md. You will be writing things like what kind of code the git repo has, what does the code do, how to use the code, etc..., to your README file. 

Once you have created your git repository (repo) in github, open a terminal and type:

```
git clone https://github.com/<github username>/<git repo name>
cd <git repo name>
```

Where \<github username\> is your github username and \<git repo name\> is the name of the git repo that you have just created. After this is done, type:

```
vim hello.c
```

Write a simple hello world program and add it to your git with this command:

```
git add hello.c
```

Now that you have added a program to your git and added it, you need to write a commit that documents what you have done. Here is an example:

```
git commit -m "Added a program called hello.c that prints Hello world!"
```

The only that should vary between git commits is what is between the double quotes. Please make your git commits meaningful. 

For more detailed commits I recommend the following command:

```
git commit
```

Lastly, type this command to upload changes to your git repo:

```
git push
```

You will be asked to enter your github username and password and BAM! you will have updated your repo, type this command to see your history of commits:
```    
git log
```

Once you have created your git repo and added hello.c and updated your git repo (your repo should have two commits), you are done! 

### Sidenote
Before using `git commit` as a way to commit what your changes are you should check to see if vim is your default text editor, the way to do this is
```
sudo update-alternatives --config editor
```
and choose your favorite text editor from there.

### Sidenote 2
You may type

```
git status
```

And you will find that git is keeping track of executables such as a.out, object files (.o), and source files (.c, .h, .cpp, .hpp). You can create a .gitignore (a hidden file), this file will tell git to not keep track of these files. You can create one that will not keep track of a.out and all object files with vim:

```
vim .gitignore
```

Inside of the file it should look like this:
 
```
*.o
a.out
```

You should NEVER add executables to your git respository. It is sketchy to do so, and **YOU WILL HAVE POINTS DEDUCED FROM YOUR ASSIGNMENT IF YOU HAVE EXECUTABLES OR OBJECT FILES (.o files) IN YOUR REPO!!!!**
