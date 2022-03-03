---
title: SimplePPT
date: 2021-11-21 20:16:45
tags:
- java
- 学校作业
- 项目
comments: true
toc: true
categories:
- [练手项目]
excerpt: SimplePPT，是一款基于Java Swing 开发的简易版PPT软件。
---

## 简介

SimplePPT，一款基于Java Swing 开发的简易版PPT软件。（NEU Java大作业）

项目地址：https://github.com/Bmaili/PPT_byJavaSwing



## 相关图片

![](http://bmalimarkdown.oss-cn-beijing.aliyuncs.com/img/IqMFsI.md.png)



![](http://bmalimarkdown.oss-cn-beijing.aliyuncs.com/img/image-20220301185743268.png)



## 功能

1.  新建、删除、打开、修改、保存幻灯片，播放幻灯片及翻页。

2.  在幻灯片页面上绘制基本图形、绘制任意线、添加文字。

3. 设定颜色、文字风格 、图形填充、线型设置。

4. 对幻灯版面上已有的基本图形、线形、文字进行选取、更改、移动。

5. 其它。

   

## 项目结构与文件说明

#### 总览

![](http://bmalimarkdown.oss-cn-beijing.aliyuncs.com/img/image-20220301190253235.png)



#### graph包

graph里存放了与图案相关的类。

之所以在所有图形类前加了“My”，是为了和Swing包里的同名类区别开。

MyShape.java是所有图形类的父类，抽象类，里面有如下属性：

![](http://bmalimarkdown.oss-cn-beijing.aliyuncs.com/img/clip_image002.jpg)

其中定义了绘图draw(),移动图像dragShapeXY()等方法，供不同的子类重写、实现。



MyCircle.java、MyRectangle.java等是具体的图案子类，见名知意，不多说，其中比较特别的是MyLine.java和Mytext.java类，绘画逻辑、移动逻辑等与其他图形不同，对父类方法进行重写，详情请看代码。

类图：

![](http://bmalimarkdown.oss-cn-beijing.aliyuncs.com/img/clip_image004.jpg)

 

#### saveobject包

Saveobject包里存放了可持久化保存的对象，即PPT和Page，PPT类维护了一个存放该PPT所有Page（页面）的列表。并且实现了保存文件、打开文件等有关于PPT的方法。

Page类维护了图形历史数据列表等。

![](http://bmalimarkdown.oss-cn-beijing.aliyuncs.com/img/clip_image006.jpg)

页面图形数据啥的就不序列化了，运行的时候再生成吧。

![](http://bmalimarkdown.oss-cn-beijing.aliyuncs.com/img/clip_image008.jpg)

同时实现了深拷贝、插背景图片等有关于Page的方法。

类图：

![](http://bmalimarkdown.oss-cn-beijing.aliyuncs.com/img/clip_image010.jpg)

 

#### ui包

Ui包里存放界面及其组件类，这些类里不仅实现了页面组件的排盘布局，也实现了对应用户操作的响应的事件。

MainJFram.java是主窗口类，负责将各组件启动并排版好。

TopMenuBar.java 是菜单栏类，负责菜单项的布局与菜单项对应动作事件的实现。

ModuleEditBar.java 是模式编辑类，负责该栏元素布局，以及画板的笔尺寸、颜色、图案选择等操作的逻辑实现。

PageListPanel.java 是页面列表操作类，负责左侧Page列表的相关逻辑实现和响应用户的操作。

DrawBoard.java 是此页画板的编辑类，当用户在此页画板上绘画时就是此类记录、响应、展示了用户的绘画数据。

大致关系如图：



![](http://bmalimarkdown.oss-cn-beijing.aliyuncs.com/img/image-20220301200737371.png)

 

PlayJFram是一个独立的窗口，负责播放PPT并响应用户的鼠标或键盘操作。

Welcome.sPage 为此软件启动后默认打开的PPT的第一页，即欢迎页，是一个序列化文件。

 


## 总结

这是一次非常Nice的练习，一个小小的项目里面就包含了很多OOP特性的使用。起初对学习swing还有些抵制，觉得这是些淘汰的技术以后也用不到，但学习并输出到这个项目中后，感觉还是受益良多。但比较遗憾的有两点：一是相对于swing来说，javafx更新颖能完成更多功能，但没有充足的时间和精力去学，有点可惜；二也是时间不够，许多当初计划完成的功能例如PPT上传、共享、下载等没有来得及实现。
