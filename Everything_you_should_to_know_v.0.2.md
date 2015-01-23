# Everything you should to know starting work as a tester in InsightConnect project but you afraid to ask :)

#### Useful knowledge for tester in InsightConnect

## Git

### What is Git

**[Git][1]** is open source Destributed Version Control System. 
The major difference between Git and any other VCS (Subversion and friends included) is the way Git thinks about its data. Conceptually, most other systems store information as a list of file-based changes. Git thinks of its data more like a set of snapshots of a miniature filesystem. Every time you commit, or save the state of your project in Git, it basically takes a picture of what all your files look like at that moment and stores a reference to that snapshot.

The basic Git workflow goes something like this:

1. You modify files in your working directory.
+  You stage the files, adding snapshots of them to your staging area.
*  You do a commit, which takes the files as they are in the staging area and stores that snapshot permanently to your Git directory.


### What for we use it.

We use git to keeping order in our files.
All documentations, tests and other useful files are stored in git repositories.
Through the use of Git we are sure that files which we use are correct and we all have the same file.

#### Our repositories

##### isc-qa (link?)

In this repository we keep the Java code for our automation.

##### isc-qa-scenarios (link?)

In this repository we keep our documentation and scenarios in feature files.

##### isc-qa-tools (link?)

In this repository we keep tools, scripts and files used in testing.

###Terms

**Working directory** is TBA
**Staged area**

### Mostly used commands. - TBA SYNTAX of commands

##### [git clone][2]
The `git clone` command is actually something of a wrapper around several other commands. It creates a new directory, goes into it and runs git init to make it an empty Git repository, adds a remote (git remote add) to the URL that you pass it (by default named origin), runs a git fetch from that remote repository and then checks out the latest commit into your working directory with git checkout.

#####[git pull][3]

The `git pull` command is basically a combination of the `git fetch` and `git merge` commands, where Git will fetch from the remote you specify and then immediately try to merge it into the branch you’re on.

#####[git status][4]

The `git status` command will show you the different states of files in your working directory and staging area. Which files are modified and unstaged and which are staged but not yet committed. In it’s normal form, it also will show you some basic hints on how to move files between these stages.

#####[git add][5]

The `git add` command adds content from the working directory into the staging area (or “index”) for the next commit. When the `git commit` command is run, by default it only looks at this staging area, so `git add` is used to craft what exactly you would like your next commit snapshot to look like.

#####[git rm][6]

The `git rm` command is used to remove files from the staging area and working directory for Git. It is similar to git add in that it stages a removal of a file for the next commit.

#####[git commit][7]

The `git commit`  command takes all the file contents that have been staged with git add and records a new permanent snapshot in the database and then moves the branch pointer on the current branch up to it.

#####[git push][8]

The `git push` command is used to communicate with another repository, calculate what your local database has that the remote one does not, and then pushes the difference into the other repository. It requires write access to the other repository and so normally is authenticated somehow.

#####[git checkout][9]

The `git checkout` command is used to switch branches and check content out into your working directory.

#####[git stash][10]

The `git stash`  command is used to temporarily store uncommitted work in order to clean out your working directory without having to commit unfinished work on a branch.

#####[git clean][11]

The `git clean` command is used to remove unwanted files from your working directory. This could include removing temporary build artifacts or merge conflict files

#####[git tag][12]

The `git tag` command is used to give a permanent bookmark to a specific point in the code history. Generally this is used for things like releases.

#####[git branch][13]

The `git branch` command is actually something of a branch management tool. It can list the branches you have, create a new branch, delete branches and rename branches

---
## Linux

### What is Linux and why we use it.

 

 Linux has a reputation as a very efficient and fast-performing system. 

### Useful commands

####cd

####cp

copies files (or, optionally, directories). 

Syntax:

     cp [OPTION]... [-T] SOURCE DEST
     cp [OPTION]... SOURCE... DIRECTORY
     cp [OPTION]... -t DIRECTORY SOURCE...

####mv

Move (rename) files.

####rm

Remove files or directories.

Syntax:
       mv [OPTION]... [-T] SOURCE DEST
       mv [OPTION]... SOURCE... DIRECTORY
       mv [OPTION]... -t DIRECTORY SOURCE...


####sudo
####mkdir

creates directories with the specified names. 

Syntax:

     mkdir [OPTION]... NAME..

`mkdir' creates each directory NAME in the order given.  It reports
an error if NAME already exists, unless the `-p' option is given and
NAME is a directory.

* touch

The touch command is the easiest way to create new, empty files. It is also used to change the timestamps (i.e., dates and times of the most recent access and modification) on existing files and directories. By default, `touch' sets file timestamps to the current time.

Synopsis:

     touch [OPTION]... file_name(s)...

* cat

Syntax:

     cat [OPTION] [FILE]...


* ls

The `ls' program lists information about files (of any type, including
directories). 

---
## Cucumber/Gherkin

### General knowledge.

TBA

### Sample Scenario

    @tag
    Feature: Sample scenarios

    Scenario: Log in with correct credentials
      Given the Log in page is displayed
      When the user types in Login text field login
      And the user types in Password text field password
      And the user picks Log in button
      Then home page is displayed

### Sample Scenario Outline

    Scenario Outline: eating
      Given there are <start> cucumbers
      When I eat <eat> cucumbers
      Then I should have <left> cucumbers

    Examples:
      | start | eat | left |
      |  12   |  5  |  7   |
      |  20   |  5  |  15  |

---
## Selenium

### General knowledge.

TBA

### Page Object Pattern.

TBA

#### CSS selectors

TBA

---
## Java

### Why Java

TBA

---
## Maven

### What for

TBA

### How we use it

TBA

---
## Other

TBA

**Markdown** is a text markup language which allows you to create documents of all types

----
## Change log

| Version |   Changes   |        Author        |    Date    |
|:---------:|:-------------|:----------------------|:------------:|
|     0.1 | First draft | Łukasz Wojciechowski | 2015-01-13 |
|     0.2 | Second draft| Olena Marchenko      | 2015-01-16 |

[1]: http://git-scm.com 
[2]: http://git-scm.com/book/en/v2/Git-Commands-Getting-and-Creating-Projects#git-clone "Read more on www.git-scm.com"
[3]: http://git-scm.com/book/en/v2/Git-Commands-Sharing-and-Updating-Projects#git-pull "Read more on www.git-scm.com"
[4]: http://git-scm.com/book/en/v2/Git-Commands-Basic-Snapshotting#git-status "Read more on www.git-scm.com"
[5]: http://git-scm.com/book/en/v2/Git-Commands-Basic-Snapshotting#git-add "Read more on www.git-scm.com"
[6]: http://git-scm.com/book/en/v2/Git-Commands-Basic-Snapshotting#git-rm "Read more on www.git-scm.com"
[7]: http://git-scm.com/book/en/v2/Git-Commands-Basic-Snapshotting#git-commit "Read more on www.git-scm.com"
[8]: http://git-scm.com/book/en/v2/Git-Commands-Sharing-and-Updating-Projects#git-push "Read more on www.git-scm.com"
[9]: http://git-scm.com/book/en/v2/Git-Commands-Branching-and-Merging#git-checkout "Read more on www.git-scm.com"
[10]: http://git-scm.com/book/en/v2/Git-Commands-Branching-and-Merging#git-stash "Read more on www.git-scm.com"
[11]: http://git-scm.com/book/en/v2/Git-Commands-Basic-Snapshotting#git-clean "Read more on www.git-scm.com"
[12]: http://git-scm.com/book/en/v2/Git-Commands-Branching-and-Merging#git-branch "Read more on www.git-scm.com"
[13]: http://git-scm.com/book/en/v2/Git-Commands-Branching-and-Merging#git-branch "Read more on www.git-scm.com"
