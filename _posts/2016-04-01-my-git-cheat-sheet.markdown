---
layout: post
title: My git cheat sheet
tags: git, cheat
---

I first learned about git at a startup I worked for, but I never really learned it. So it made sense that, since I wanted to start this blog and it involved Github, I should learn more about it. Since I'm a more practical person, I opted for a quick intro course on <a href="https://www.codecademy.com/learn/learn-git" target="_blank">Code Academy</a>. I first created this cheat sheet on Google Keep, but it now makes more sense to keep it here.

<br/>

`git init`: create a repo based on working dir;

`git status`: checks the status of working dir and staging;

`git add {file1 file2}`: adds file to staging;

`git diff {file}`: checks difference between staged and local files;

`git log`: checks repo log;

`git commit -m "Message"`: commits to repo;

`git show HEAD`: displays head commit;

`git checkout HEAD {file}`: reverts file changes from HEAD to working dir;

`git reset HEAD {file}`: removes file from staging;

`git reset {SHA (first 7 digits)}`: resets HEAD to the specified SHA commit;

`git branch`: checks which branch the user is on;

`git branch {branch-name}`: creates new branch;

`git checkout {branch-name}`: branch becomes working dir;

`git merge {branch-name}`: merges branch-name into working branch;

`git branch -d {branch-name}`: deletes the branch;

`git clone {remote-name}` {local-name}: clones the remote repo into your local;

`git remote -v`: list all remote repos;

`git fetch`: gets the latest changes from the remote repo

`git push origin {branch-name}`: pushes my branch to the remote repo;