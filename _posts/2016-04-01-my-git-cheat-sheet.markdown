---
title: My git cheat sheet
tags: git, cheat
summary: I first learned about git at a startup I worked for, but I never really learned it. So it made sense that, since I wanted to start this blog and it involved Github, I should learn more about it.
image: /assets/2016-04-01/hero.jpg
---

I first learned about git at a startup I worked for, but I never really learned it. So it made sense that, since I wanted to start this blog and it involved Github, I should learn more about it. Since I'm a more practical person, I opted for a quick intro course on <a href="https://www.codecademy.com/learn/learn-git" target="_blank">Code Academy</a>. I first created this cheat sheet on Google Keep, but it now makes more sense to keep it here.

<br/>

`git init`: initializes git;

`git remote add {remote-repo} {GitHub repo URL}`: links to the existing remote-repo;

`git clone {URL of online repo}`: copies a repo into the folder;

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

`git fetch`: gets the latest changes from the remote repo

`git merge {branch-name}`: merges branch-name into working branch;

`git pull {remote-repo} {local-repo}`: executes a `git fetch` followed by `git merge`;

`git branch -d {branch-name}`: deletes the branch;

`git clone {remote-name} {local-name}`: clones the remote repo into your local;

`git remote -v`: list all remote repos;

`git remote rename {current name} {new name}`: changes the name of an existing remote;

`git push {remote-repo} {local-repo}`: pushes my branch to the remote repo;
