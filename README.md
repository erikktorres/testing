testing
=======

This repository contains Tidepool's manual test scripts and notes on testing strategy

This document is aimed at people who are not tidepool employees, and therefore don't have commit rights to Tidepool's repositories. There will be some notes for employees as well.

(NOTE: as of 13 Sept 2014, we have no scripts here yet -- we're just getting this started.)

# Getting started

First, [create a GitHub account](https://github.com) if you don't already have one, and [set up git](https://help.github.com/articles/set-up-git)

Next, you need a copy of this repository. So [fork it](https://help.github.com/articles/fork-a-repo).

From there, you have to clone the fork to your own machine so you have everything locally (that's the "keep your fork synced" part of the fork instructions).

You can use the command line to do this, or you can use the GitHub app [for Mac](https://mac.github.com) or [for Windows](https://windows.github.com).

Finally, if you haven't agreed to our VCLA, please follow the directions on [our contributors page](http://developer.tidepool.io/contributors/). 

# Setting up a version for test

* Make sure [your fork is up to date](https://help.github.com/articles/syncing-a-fork). 
* If you have a local repository, refresh it from the fork:
```
    git pull origin master
```
* Figure out what the version identifier is for the version you're testing. It may be the blip version ID (and if Tidepool is asking you to test it, we'll tell you what it should be). Let's pretend it's latest-awesome-version.
* If there is already a folder for latest-awesome-version, you're done and can run tests.
* If there is not a version folder, create one by copying the contents of the script folder to it -- and add a date prefix, then commit that folder:
```
    cp -r scripts 20140913-latest-awesome-version
    git add 20140913-latest-awesome-version
    git commit -m "Starting latest-awesome-version"
```

## To run a test:

* Find the test you want to run by looking in the version folder. It will have a filename that looks like ```001-smoketest.md```
* Copy the test to the same name, but add your github name:
```
    cp 001-smoketest.md 001-smoketest-kentquirk.md
```
* Now open the file you just created and start doing the test. As you do the steps of the test, please put an X in the checkboxes. They look like ```- [ ]``` -- make them look like ```- [x]``` instead.
* If you find a bug, please write up the bug in a github issue and include a brief explanation and a link to the bug on the line of the test. Example:
```
    - [x] Add a comment to a BG reading and make sure the comment appears on the timeline. (Note -- comment did not appear -- issue #tideline/321)
```
* Please check only the items that you actually test. If a bug prevents you from continuing, make a note of it and leave the remaining items unchecked.
* Feel free to write as much as you need to, and don't worry too much about formatting. It's more important to get the information down than to make it pretty.
* Save the file you've been editing!

## To run multiple tests

* Repeat the process above for each individual test.

## When finished

* Do a git add and commit:
```
    git add 001-smoketest-kentquirk.md 002-login-kentquirk.md
    git commit -m "Early testing"
```
* Now push to master:
```
    git push origin master
```
* Now your test results are on GitHub, but Tidepool doesn't know about them yet. You need to submit a [Pull Request](https://help.github.com/articles/using-pull-requests) to Tidepool. For testing work, we'll basically just accept your results into our repository -- but if we have questions, we'll get back to you.

