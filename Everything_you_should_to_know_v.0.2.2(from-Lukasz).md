# Everything you should know starting work as a tester in InsightConnect project but you afraid to ask :)

#### Useful knowledge for tester in InsightConnect

##Table of contents:##
<!-- MarkdownTOC depth=3 autolink=true bracket=round -->

- [Git](#git)
  - [What is Git](#what-is-git)
  - [What for we use it.](#what-for-we-use-it)
  - [Pay attention:](#pay-attention)
  - [Mostly used commands](#mostly-used-commands)
- [Linux](#linux)
  - [What is Linux and why we use it.](#what-is-linux-and-why-we-use-it)
  - [Useful commands](#useful-commands)
- [Cucumber/Gherkin](#cucumbergherkin)
  - [General knowledge.](#general-knowledge)
  - [Sample Scenario](#sample-scenario)
  - [Sample Scenario Outline](#sample-scenario-outline)
- [Selenium](#selenium)
  - [General knowledge.](#general-knowledge-1)
  - [Page Object Pattern.](#page-object-pattern)
- [Java](#java)
  - [Why Java](#why-java)
- [Maven](#maven)
  - [What for](#what-for)
  - [How we use it](#how-we-use-it)
- [Other](#other)
  - [Markdown](#markdown)
- [Change log](#change-log)

<!-- /MarkdownTOC -->


## Git

### What is Git

**[Git][]** is open source Destributed Version Control System.
The major difference between Git and any other VCS (Subversion and friends included) is the way Git thinks about its data. Conceptually, most other systems store information as a list of file-based changes. Git thinks of its data more like a set of snapshots of a miniature filesystem. Every time you commit, or save the state of your project in Git, it basically takes a picture of what all your files look like at that moment and stores a reference to that snapshot.

The basic Git workflow goes something like this:

1. You modify files in your working directory.
2. You stage the files, adding snapshots of them to your staging area.
3. You do a commit, which takes the files as they are in the staging area and stores that snapshot permanently to your Git directory.

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

### Pay attention:

This is the main thing to remember about Git if you want the rest of your learning process to go smoothly. Git has three main states that your files can reside in: committed, modified, and staged. Committed means that the data is safely stored in your local database. Modified means that you have changed the file but have not committed it to your database yet. Staged means that you have marked a modified file in its current version to go into your next commit snapshot.

This leads us to the three main sections of a Git project: the **Git directory**, the **working directory**, and the **staging area**.

The **Git directory** is where Git stores the metadata and object database for your project. This is the most important part of Git, and it is what is copied when you clone a repository from another computer.

The **working directory** is a single checkout of one version of the project. These files are pulled out of the compressed database in the Git directory and placed on disk for you to use or modify.

The **staging area** is a file, generally contained in your Git directory, that stores information about what will go into your next commit. It’s sometimes referred to as the “index”, but it’s also common to refer to it as the staging area.

### Mostly used commands

##### [git clone][]
The `git clone` command clones a repository into a newly created directory, creates remote-tracking branches for each branch in the cloned repository (visible using git branch -r), and creates and checks out an initial branch that is forked from the cloned repository’s currently active branch.

Syntax:

    git clone [--template=<template_directory>]
                 [-l] [-s] [--no-hardlinks] [-q] [-n] [--bare] [--mirror]
                 [-o <name>] [-b <name>] [-u <upload-pack>] [--reference <repository>]
                 [--separate-git-dir <git dir>]
                 [--depth <depth>] [--[no-]single-branch]
                 [--recursive | --recurse-submodules] [--] <repository>
                 [<directory>]

##### [git pull][]

The `git pull` command is basically a combination of the `git fetch` and `git merge` commands, where Git will fetch from the remote you specify and then immediately try to merge it into the branch you’re on.

Syntax:

       git pull [options] [<repository> [<refspec>...]]

##### [git status][4]

The `git status` command will show you the different states of files in your working directory and staging area. Which files are modified and unstaged and which are staged but not yet committed. In it’s normal form, it also will show you some basic hints on how to move files between these stages.

##### [git add][5]

The `git add` command adds content from the working directory into the staging area (or “index”) for the next commit. When the `git commit` command is run, by default it only looks at this staging area, so `git add` is used to craft what exactly you would like your next commit snapshot to look like.

Syntax:

       git add [-n] [-v] [--force | -f] [--interactive | -i] [--patch | -p]
                 [--edit | -e] [--[no-]all | --[no-]ignore-removal | [--update | -u]]
                 [--intent-to-add | -N] [--refresh] [--ignore-errors] [--ignore-missing]
                 [--] [<pathspec>...]


##### [git rm][6]

The `git rm` command is used to remove files from the staging area and working directory for Git. It is similar to git add in that it stages a removal of a file for the next commit.

Syntax:

       git rm [-f | --force] [-n] [-r] [--cached] [--ignore-unmatch] [--quiet] [--] <file>...

##### [git commit][7]

The `git commit`  command takes all the file contents that have been staged with git add and records a new permanent snapshot in the database and then moves the branch pointer on the current branch up to it. In simple words this command records changes to the repository.

Syntax:

       git commit [-a | --interactive | --patch] [-s] [-v] [-u<mode>] [--amend]
                  [--dry-run] [(-c | -C | --fixup | --squash) <commit>]
                  [-F <file> | -m <msg>] [--reset-author] [--allow-empty]
                  [--allow-empty-message] [--no-verify] [-e] [--author=<author>]
                  [--date=<date>] [--cleanup=<mode>] [--[no-]status]
                  [-i | -o] [-S[<keyid>]] [--] [<file>...]


##### [git push][8]

The `git push` command is used to communicate with another repository, calculate what your local database has that the remote one does not, and then pushes the difference into the other repository. It requires write access to the other repository and so normally is authenticated somehow.

Syntax:

       git push [--all | --mirror | --tags] [--follow-tags] [-n | --dry-run] [--receive-pack=<git-receive-pack>]
                  [--repo=<repository>] [-f | --force] [--prune] [-v | --verbose] [-u | --set-upstream]
                  [--force-with-lease[=<refname>[:<expect>]]]
                  [--no-verify] [<repository> [<refspec>...]]


##### [git checkout][9]

The `git checkout` command is used to switch branches and check content out into your working directory.

Syntax:

       git checkout [-q] [-f] [-m] [<branch>]
       git checkout [-q] [-f] [-m] --detach [<branch>]
       git checkout [-q] [-f] [-m] [--detach] <commit>
       git checkout [-q] [-f] [-m] [[-b|-B|--orphan] <new_branch>] [<start_point>]
       git checkout [-f|--ours|--theirs|-m|--conflict=<style>] [<tree-ish>] [--] <paths>...
       git checkout [-p|--patch] [<tree-ish>] [--] [<paths>...]


##### [git stash][10]

The `git stash`  command is used to temporarily store uncommitted work in order to clean out your working directory without having to commit unfinished work on a branch.

Syntax:

       git stash list [<options>]
       git stash show [<stash>]
       git stash drop [-q|--quiet] [<stash>]
       git stash ( pop | apply ) [--index] [-q|--quiet] [<stash>]
       git stash branch <branchname> [<stash>]
       git stash [save [-p|--patch] [-k|--[no-]keep-index] [-q|--quiet]
                    [-u|--include-untracked] [-a|--all] [<message>]]
       git stash clear
       git stash create [<message>]
       git stash store [-m|--message <message>] [-q|--quiet] <commit>

##### [git clean][11]

The `git clean` command is used to remove unwanted files from your working directory. This could include removing temporary build artifacts or merge conflict files.

Syntax:

    git clean [-d] [-f] [-i] [-n] [-q] [-e <pattern>] [-x | -X] [--] <path>...

##### [git tag][12]

The `git tag` command is used to give a permanent bookmark to a specific point in the code history. Generally this is used for things like releases.

Syntax:

       git tag [-a | -s | -u <key-id>] [-f] [-m <msg> | -F <file>]
               <tagname> [<commit> | <object>]
       git tag -d <tagname>...
       git tag [-n[<num>]] -l [--contains <commit>] [--points-at <object>]
               [--column[=<options>] | --no-column] [<pattern>...]
               [<pattern>...]
       git tag -v <tagname>...

##### [git branch][13]

The `git branch` command is actually something of a branch management tool. It can list the branches you have, create a new branch, delete branches and rename branches

Syntax:

       git branch [--color[=<when>] | --no-color] [-r | -a]
               [--list] [-v [--abbrev=<length> | --no-abbrev]]
               [--column[=<options>] | --no-column]
               [(--merged | --no-merged | --contains) [<commit>]] [<pattern>...]
       git branch [--set-upstream | --track | --no-track] [-l] [-f] <branchname> [<start-point>]
       git branch (--set-upstream-to=<upstream> | -u <upstream>) [<branchname>]
       git branch --unset-upstream [<branchname>]
       git branch (-m | -M) [<oldbranch>] <newbranch>
       git branch (-d | -D) [-r] <branchname>...
       git branch --edit-description [<branchname>]

---
## Linux

### What is Linux and why we use it.



 Linux has a reputation as a very efficient and fast-performing system.

### Useful commands

#### [cd][]

The `cd` command, which stands for "change directory", changes the shell's current working directory.

#### [cp][]

The `cp` command is used to copies files and directories.

  Syntax:

        cp [OPTION]... [-T] SOURCE DEST
        cp [OPTION]... SOURCE... DIRECTORY
        cp [OPTION]... -t DIRECTORY SOURCE...

#### [mv][]

The `mv` command is used to move or rename files.

  Syntax:

        mv [OPTION]... [-T] SOURCE DEST
        mv [OPTION]... SOURCE... DIRECTORY
        mv [OPTION]... -t DIRECTORY SOURCE...

#### [rm][]

  The `rm` command removes (deletes) files or directories.

  Syntax:

        rm [OPTION]... FILE...


#### [sudo][]

  sudo, sudoedit — execute a command as another user.

  sudo allows a permitted user to execute a command as the superuser or another user, as specified by the security policy.

#### [mkdir][]

Short for "make directory", `mkdir` is used to create directories on a file system.

  Syntax:

       mkdir [OPTION]... NAME..

  `mkdir` creates each directory NAME in the order given.  It reports
  an error if NAME already exists, unless the `-p` option is given and
  NAME is a directory.

#### touch

  The touch command is the easiest way to create new, empty files. It is also used to change the timestamps (i.e., dates and times of the most recent access and modification) on existing files and directories. By default, `touch' sets file timestamps to the current time.

  Synopsis:

       touch [OPTION]... file_name(s)...

#### cat

Syntax:

     cat [OPTION] [FILE]...


#### ls

The `ls` program lists information about files (of any type, including
directories).

#### grep

#### find

#### man

#### clear

#### reset

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

### Markdown

**Markdown** is a text markup language which allows you to create documents of all types

----
## Change log

| Version  | Changes       | Author                | Date         |
| -------- | ------------- | --------------------- | ------------ |
| 0.1      | First draft   | Łukasz Wojciechowski  | 2015-01-13   |
| 0.2      | Second draft  | Olena Marchenko       | 2015-01-16   |

[git]: http://git-scm.com
[git clone]: http://git-scm.com/book/en/v2/Git-Commands-Getting-and-Creating-Projects#git-clone "Read more on www.git-scm.com"
[git pull]: http://git-scm.com/book/en/v2/Git-Commands-Sharing-and-Updating-Projects#git-pull "Read more on www.git-scm.com"
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
[cd]: http://www.computerhope.com/unix/ucd.htm "Read more"
[mv]: http://www.computerhope.com/unix/umv.htm "Read more"
[cp]: http://www.computerhope.com/unix/ucp.htm "Read more"
[rm]: http://www.computerhope.com/unix/urm.htm "Read more"
[sudo]: http://www.computerhope.com/unix/sudo.htm "Read more"
[mkdir]: http://www.computerhope.com/unix/umkdir.htm "Read more"