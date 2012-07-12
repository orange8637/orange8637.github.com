---
layout: post
title: "C++缓冲区"
date: 2012-07-10 11:30
comments: true
categories: [c/c++]
---
>先提出问题，以后在解决。
>案例1

```cpp 键盘输入流缓冲区
#include <iostream>  
using namespace std;  
int main()  
{  
	char name[10];
	cin.getline(name,5);
	cout<<name;
	cin.getline(name,5);
	cout<<name;
	return 0;  
}
```	

>案例2

```cpp 文件输入流缓冲区
#include<iostream>
#include<stdio.h>
#include<map>
using namespace std;
int main()
{
	freopen("data.in", "r", stdin);
	map<char*,double> m;
	char name[100];
	double score;
	for(int i=0;i<2;i++)
	{
		//scanf("%s %lf", name, &score);
		cin>>name>>score;
		m[name] = score;
	}
	for(map<char*,double>::iterator it=m.begin(); it!=m.end(); it++)
	{
		printf("%s %lf\n", it->first, it->second);
	}
	return 0;
}
```

>附上原文本文件
```html data.in
apple 92.3
orange 94.5
```
