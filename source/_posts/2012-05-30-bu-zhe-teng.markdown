---
layout: post
title: "又折腾了一晚"
date: 2012-05-30 22:24
comments: true
categories: [web]
---
fuck xxx!
手贱把上次配置好的博客全删除了，而且是github上面的也删除了，无奈只得重新配置一次。
先分析一下目录树
```bash 目录树
.
├── _deploy
│   ├── about
│   ├── assets
│   │   └── jwplayer
│   │       └── glow
│   │           ├── controlbar
│   │           ├── display
│   │           ├── dock
│   │           ├── playlist
│   │           └── sharing
│   ├── blog
│   │   ├── 2012
│   │   │   └── 05
│   │   │       ├── 14
│   │   │       │   └── ubuntu-common-softwae
│   │   │       ├── 15
│   │   │       │   └── cao-zuo-xi-tong-zhong-de-linuxming-ling
│   │   │       └── 30
│   │   │           └── bu-zhe-teng
│   │   ├── archives
│   │   └── categories
│   │       ├── linux
│   │       └── thoughs
│   ├── images
│   ├── javascripts
│   │   ├── asides
│   │   └── libs
│   └── stylesheets
│       ├── bootstrap
│       └── syntax
├── plugins
├── public
│   ├── about
│   ├── assets
│   │   └── jwplayer
│   │       └── glow
│   │           ├── controlbar
│   │           ├── display
│   │           ├── dock
│   │           ├── playlist
│   │           └── sharing
│   ├── blog
│   │   ├── 2012
│   │   │   └── 05
│   │   │       ├── 14
│   │   │       │   └── ubuntu-common-softwae
│   │   │       ├── 15
│   │   │       │   └── cao-zuo-xi-tong-zhong-de-linuxming-ling
│   │   │       └── 30
│   │   │           └── bu-zhe-teng
│   │   ├── archives
│   │   └── categories
│   │       ├── linux
│   │       └── web
│   ├── images
│   ├── javascripts
│   │   ├── asides
│   │   └── libs
│   └── stylesheets
│       ├── bootstrap
│       └── syntax
├── sass
│   ├── base
│   ├── bootstrap
│   ├── custom
│   ├── partials
│   │   └── sidebar
│   └── syntax
└── source
    ├── about
    ├── assets
    │   └── jwplayer
    │       └── glow
    │           ├── controlbar
    │           ├── display
    │           ├── dock
    │           ├── playlist
    │           └── sharing
    ├── blog
    │   └── archives
    ├── images
    ├── _includes
    │   ├── asides
    │   ├── custom
    │   │   └── asides
    │   └── post
    ├── javascripts
    │   ├── asides
    │   └── libs
    ├── _layouts
    ├── _posts
    └── stylesheets
        ├── bootstrap
        └── syntax
```


```cpp hanoi.cpp
/*
* Filename: hanoi.cpp
* Last modified: 2012-05-30 18:47
* Author: Chen Jiang(姜晨) -- orange8637@gmail.com
* Description: 汉诺塔问题
*/
#include<stdio.h>
using namespace std;
void move(int n, char from, char to, char aux)
{
    if(n==1)
    {
        printf("move %d from %c to %c\n", n, from ,to);
    }
    else
    {
        move(n-1, from, aux, to);
        printf("move %d from %c to %c\n", n, from, to, aux);
        move(n-1, aux, to, from);
    }
}
int main()
{
        int n;
        scanf("%d",&n);
        move(n,'a','c','b');

    return 0;
}
```
