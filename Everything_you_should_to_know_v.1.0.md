# Everything you should to know starting work as a tester in InsightConnect project but you afraid to ask :)

#### Useful knowledge for tester in InsightConnect

## Git

**hello**

### What is Git

**Git** is open source Destributed Version Control System. 
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

##### isc-qa

In this repository we keep the Java code for our automation.

##### isc-qa-scenarios

In this repository we keep our documentation and scenarios in feature files.

##### isc-qa-tools

In this repository we keep tools, scripts and files used in testing.

### Mostly used commands.

* git clone
The git clone command is actually something of a wrapper around several other commands. It creates a new directory, goes into it and runs git init to make it an empty Git repository, adds a remote (git remote add) to the URL that you pass it (by default named origin), runs a git fetch from that remote repository and then checks out the latest commit into your working directory with git checkout.
* git pull
* git status
* git add
* git rm
* git commit
* git push
* git checkout
* git stash
* git clean
* git tag
* git branch

## Linux

### What is Linux and why we use it.

TBA

### Useful commands

* cd
* cp
* mv
* sudo
* mkdir
* touch
* cat

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

## Selenium

### General knowledge.

TBA

### Page Object Pattern.

TBA

#### CSS selectors

TBA

## Java

### Why Java

TBA

## Maven

### What for

TBA

### How we use it

TBA

## Other

TBA

Markdown is a text markup language which allows you to create documents of all types

## Change log

| Version |   Changes   |        Author        |    Date    |
|---------|-------------|----------------------|------------|
|     0.1 | First draft | Łukasz Wojciechowski | 2015-01-13 |
|     0.2 | Second draft| Olena Marchenko      | 2015-01-15 |

