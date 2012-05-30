---
layout: post
title: "操作系统实验中的linux命令"
date: 2012-05-15 16:10
comments: true
categories: [linux]
---

首先不推荐中大信科院自己的操作系统实验课,跟着老师学完，你只是windows里点点鼠标更熟练了。强烈推荐这份[南大操作系统实验](http://cslab.nju.edu.cn/opsystem/#MainPage),我也正在看，欢迎交流[@twitter](https://twitter.com/#!/bigbiepineapple)(求粉哟)
>实验依赖(ubuntu 12.04下)
    sudo apt-get install nasm
    sudo apt-get install vim
    sudo apt-get instsall virtualbox

第一次用markdown,好不熟悉,这是第二段?

因为怕考试时候忘了命令，所以将这些记下来。

>创建一个新的软盘
    dd if=/dev/zero of=floppy.img bs=512 count=2880

512Bx2880是不是正好等于1.44MB,只要修改bs（block size),count参数，你可以创建任何格式大小的磁盘镜像文件。抛弃你的botchs创建空软盘的老土方法吧,linux提供你所需要的任何机制。

>汇编编译及写引导扇区
    asm -> bin
    sudo nasm boot.asm -o boot.bin
    bin -> img
    sudo dd if=boot.bin of=a.img bs=512 count=1 conv=notrunc

>读出硬盘MBR
    sudo dd if=/dev/sda of=~/MYBoot.dat bs=512 count=1

>用vim取代winHex编辑16进制功能
    vim -b floppy.img
    :%!xxd
    do some rewrite...
    :%!xxd -r
    :wq

>往镜像文件添加文件
    sudo mkdir -p /mnt/floppy
    sudo mount floppy.img /mnt/floppy
    sudo cp *.com /mnt/floppy
    sudo umount /mnt/floppy

>反汇编
    ndisasm -o 0x7c00 boot.bin >> boot.asm
