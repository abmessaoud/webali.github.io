---
layout: post
title: Update your fork directly on GitHub
---

How to update a forked repo and get the last updates from the original project?

![](../images/git-merge.png)

### Short answer

On your local CLI of the forked project, link the repo to the original project, fetch changes, do a merge, and finally push to your GitHub repo.

### Long answer  

We can update a forked git repository using one of the many GUIs for git, but we will do it in CLI. 

First under your repository directory:

<script src="https://gist.github.com/alibenmessaoud/db3fe7d02c8d09d98ec4a08adec60633.js"></script>

Shows URLs of remote repositories when listing your current remote connections: 

<script src="https://gist.github.com/alibenmessaoud/55f4fb755529a21d9aa8fc04c61eb81f.js"></script>

Enter a remote *upstream* repo to sync with your fork:

<script src="https://gist.github.com/alibenmessaoud/987216c1efc10e4e8227cb110a6848e6.js"></script>

Verify:

<script src="https://gist.github.com/alibenmessaoud/1af62097caf6839eb12f93b87d3d9c85.js"></script>

Fetch commits from the upstream repo. This will copy the commits from `master` branch into a local branch called `upstream/master`:

<script src="https://gist.github.com/alibenmessaoud/cf67b53f5bc85790c003514fcf675439.js"></script>

Merge changes from `upstream/master` into `master`:

<script src="https://gist.github.com/alibenmessaoud/6f1a8bee475ecf82f219274e06466352.js"></script>

Push changes to your repo:

<script src="https://gist.github.com/alibenmessaoud/b400190419fd8c4d1bb80742330a2032.js"></script>

### Reference

 https://rick.cogley.info/post/update-your-forked-repository-directly-on-github 