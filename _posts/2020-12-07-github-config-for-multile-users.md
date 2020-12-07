---
layout: archive 
title:  "Github config for multiple users"
date:   2020-12-06 11:44:52 +0800
categories: jekyll update
---
## Background 
```
We sometimes use more than one github account to manage different repositories.
Even though we've set the config file(~/.ssh/config) correctly and test(ssh -T git@github.com) correctly, it will promote "permission denied(public key)" while we hit git push.

```
* The problem is that we need to clarify different hosts for different users.
* And make the Host of url in you repository config the same as that of ~/.ssh/config

### Here is the content of my git config file(~/.ssh/config):
```
Host github1     										# Do make the Host distinct from each other
   Hostname github.com 
   User mingzhi999 									# This is your github account name
   IdentityFile ~/.ssh/id_rsa_git	  # Please config your SSH key in your github settings

Host github2
   Hostname github.com 
   User lilu888 
   IdentityFile ~/.ssh/id_rsa_lilu_git
```

### The following is part of git config in my repository 
```
[remote "origin"]
	url = git@github2:lilu888/project.git
	fetch = +refs/heads/*:refs/remotes/origin/*
```
- Please pay attention the the format of url: git@Host:user/project.git

### Finally, there will be no errors with 'git push'
