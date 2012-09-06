---
layout: post
title: "MySQL note 1"
date: 2012-09-06 20:23
comments: true
categories: [MySQL]
---

> 第一个学习的数据库，以MySQL开刀。

> Server version:mysql 5.5.24-0ubuntu0.12.04.1 (Ubuntu)

> 1.字符集修改

> mysql5.5版本以后不支持修改default-character-set方法，改为`vim sudo:/etc/mysql/my.cnf` ,在`[mysqld]`后添加

	character-set-server=utf8

