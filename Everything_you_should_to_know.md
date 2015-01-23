# Everything you should to know starting work as a tester in InsightConnect project but you afraid to ask :)

#### Useful knowledge for tester in InsightConnect

## Git

### What is Git

TBA

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

## Change log

| Version |   Changes   |        Author        |    Date    |
|---------|-------------|----------------------|------------|
|     0.1 | First draft | Łukasz Wojciechowski | 2015-01-13 |
