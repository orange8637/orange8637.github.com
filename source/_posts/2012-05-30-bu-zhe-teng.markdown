---
layout: post
title: "又折腾了一晚"
date: 2012-05-30 22:24
comments: true
categories: [web]
---
>本来上次已经配置好的博客，但是由于细节的不完善，手贱贱地把本地和远程分支上的配置都删除了，无奈只得重新来一次github上的octopress博客搭建。

>综合谷歌百度引擎，发现最好的教程仍然是[octopress官方博客](http://octopress.org/)。不得不承认octopress写博客的方式很hacker,所有的步骤都能在shell和vim完成。有了2次搭建的经历，终于对octopree的文件管理方式有了一些理解:上传到github上的有两个分支，一个是master,一个是source,而source是我们最重要的源码,两个分支分别对应文件目录的deploy和，source文件夹(注释在下面的目录树了)，所以下次在其他电脑上书写博客，一定要注意clone下来的目录，要先`git checkout source`分支，然后`rake setup_github_pages`才能`rake new_post['blog']` `rake generate` `rake deploy`。

>好了，终于可以随意自由markdown写博客了！:)

```bash octopress目录树
.
├── _deploy *github上origin服务器上的master分支,既最终部署的页面
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
├── public *本地rake generate,rake preview生成的页面
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
└── source *github上origin服务器上的source分支,源码存放地
    ├── about *主页上about栏markdown文件
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
    ├── images *博客本地配图存放地
    ├── _includes
    │   ├── asides
    │   ├── custom
    │   │   └── asides
    │   └── post
    ├── javascripts
    │   ├── asides
    │   └── libs
    ├── _layouts
    ├── _posts *博客所有markdown源文件
    └── stylesheets
        ├── bootstrap
        └── syntax
```
