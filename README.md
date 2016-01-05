# Git-for-beginners
*Modified based on (c) 2011 Jacob Biesinger's document (jake.biesinger@gmail.com)*

Git is a widely-used [version control system](https://en.wikipedia.org/wiki/Version_control) for software development. In a nutshell, it keeps track of modifications you have done on your source code. You can easily switch back and forth your source code between different versions. It's also much less painful to collaborate with other people's code with version control system.

Setting up a local Git repository
=================================
First, you need to set up your info, e.g.:
```
$ git config --global user.name "Yi Li"
$ git config --global user.email "yil8@uci.edu"
```
Say you already have a working directory full of code and you'd like to turn it into a git repository. First, you need to initialize a new git repo in that directory, then add the files you want tracked. Here, I'll add a python source file and everything under the Doc directory.
```
$ cd ~/Projects/WGS
$ git init
Initialized empty Git repository in /home/yili/Desktop/WGS/.git/
$ git add test.py Doc
$ git commit -a  # a text editor will open awaiting your commit message, can also use -m "message here"
```
When you did the commit, you pushed your changes to your local “miniserver”. After making more changes to these same files, just do a “git commit -a” to save all the changes, or you can select which files to commit with “git commit my_file1 myfile2”.


Setting up the remote Github server
==================================
If we want to work with the Gitub server, we need to first create a repository on the Github. Please refer to [Github Hello World](https://guides.github.com/activities/hello-world/) for how to create a repository. Once we've created a repository, e.g. Git_for_beginners like this current one, we can make a local copy(clone) from the Github server using the HTTPS link.

```
$ git clone https://github.com/CipherGene/Git_for_beginners.git
Cloning into 'Git_for_beginners'...
remote: Counting objects: 4, done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (4/4), done.
Checking connectivity... done.
```
We can now jump into the local repository and rename the remote server.
```
$ cd Git_for_beginners
$ git remote
origin
$ git remote rename origin github
$ git remote
github
```
We can again add new files:
```
$ git add test.py
$ git commit -a
```
Now we want to push the change on local repository to the remote Github server
```
$ git push github master
Username for 'https://github.com': yil8
Password for 'https://yil8@github.com': 
Everything up-to-date
```
You can then refresh the Git_for_beginners repository and find the test.py has been added. 

To get updates from the Github server
```
$ git pull github master
From https://github.com/CipherGene/Git_for_beginners
 * branch            master     -> FETCH_HEAD
Already up-to-date.
```

Once you've got the basics, I would recommend learning how to work with branches. They allow you to work in parallel on divergent features and eventually to share them and merge them back together smartly.

[List of tutorials](http://sixrevisions.com/resources/git-tutorials-beginners/)

