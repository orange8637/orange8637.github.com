---
layout: post
title: "随时随地配置octopress本地环境"
date: 2012-09-03 20:01
comments: true
categories: [web]
---

> 最近帮南都报社的一小子买了台10.6寸上网本，为了自己也尝尝新电脑玩，将我自己那台14寸笔记本格了，把两台电脑都装了ubuntu12.04 & win7双系统。自然是以前的octopress配置都没了，所以我要在两台电脑都配置好octopress本地环境，创造一个写博客的好环境。

----

> ###一.安装ruby,git等软件依赖###

```
kiwi@kiwi:~$ sudo apt-get install git
kiwi@kiwi:~$ sudo apt-get install ruby1.9.3
kiwi@kiwi:~$ sudo gem install bundler --pre
kiwi@kiwi:~$ bundle install
```

----
> ###二.从github上获取你的博客###
```
kiwi@kiwi:~$ git clone -b source git@github.com:orange8637/orange8637.github.com octopress
kiwi@kiwi:~$ cd octopress/
kiwi@kiwi:~$ git clone git@github.com:orange8637/orange8637.github.com _deploy 
```
> 由于octopress这个项目和我们其他的github项目不同，它可不是只有一个master分支的，所以我们要理清一个关系:文件目录octopress对应远程和本地的source分支，_deploy目录对应远程和本地的master分支。

```
kiwi@kiwi:~/octopress$ git branch
* source
kiwi@kiwi:~/octopress$ cd _deploy/
kiwi@kiwi:~/octopress/_deploy$ git branch
* master
```

----

> 好了。不到10条指令，源速度够快的话，10分钟我们就配好了octopress环境，就是这么简单，没有数据库史上最快的可以版本控制的博客环境就可以工作了。多`rake new_post`吧。
