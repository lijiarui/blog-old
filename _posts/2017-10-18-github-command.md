---
layout: post
title: "Github useful command"
date: 2017-10-18 00:00 +0800
author: lijiarui
---


I always foget the basic use of github... I used Evernote before but it really ugly when no markdown. So I came here...

<!--more-->

## Sync fork repo B_REPOSITORY with upstream repo A_REPOSITORY
1. clone repo B_REPOSITORY to local   
```
git clone B_REPOSITORY_URL
```
2. Add A_REPOSITORY as remote to local  B_REPOSITORY（mostly called upstream）   
```
git remote add upstream https://github.com/be-forked-repo.git
```
3. pull A_REPOSITORY remote（upstream）branch(like master)   
```
git pull upstream master
```
4. puah to github B_REPOSITORY   
```
git push origin master
```

## Add all update file
```
git add -u 
```

## Show log
```
git log
```

## Delete no related commit
```
git reset --hard <commit_id>
git push origin HEAD —force
```
If you didn't publish changes, to remove latest commit, you can do
```
$ git reset --hard HEAD^
```
(note that this would also remove all uncommitted changes; use with care).

If you already published to-be-deleted commit, use git revert
```
$ git revert HEAD
```

## Delete branch  
```
git branch -D testing
```
