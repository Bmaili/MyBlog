---
title: 速率八十v吧
date: 2022-02-21 19:13:57
tags:
- Java
comments: true
toc: true
categories:
- [JVM]
- [测试]
---

## QT_Huffman Compression
基于Huffman算法的文本、位图压缩与解压软件

## 1. 成果截图：
![1.png](https://z3.ax1x.com/2021/05/09/gJfYDK.png)
![2.png](https://z3.ax1x.com/2021/05/09/gJfUED.png)
![3.png](https://z3.ax1x.com/2021/05/09/gJfaUe.png)
![4.png](https://z3.ax1x.com/2021/05/09/gJfJu6.png)

## 2. 功能说明：
这是我们的数据结构的小组课设，功能有二：

能即时地对输入的文本进行Huffman编码、解码，显示各字符的编码结果，利于使用者对Huffman的直观理解、学习。

利用Huffman编码对文本或位图文件进行数据压缩，同时将压缩信息也写入压缩文件内，故用户也可使用该软件解压之。

## 3. 运行环境
开发测试环境：Desktop QT 5.9.9 MinGW 32bit

编译时项目路径不能含中文

可使用Enigma Virtual Box之类的软件打包封装

## 4. 复盘
选择对BMP位图进行压缩一是因为题目要求，二是因为它的理论压缩比比较可观，压缩“效果好”。

现在来看这个软件还是有许多值得改进的地方的：

1.代码写得不够优雅，逼死代码洁癖患者

2.编码译码文本时是利用ascii码值做键，编码译码BMP时是利用灰度值做键，这是一个能提升编码译码效率的巧妙想法，但是问题是不能对ascii码外的字符进行编码了

3.应该做一个类似Java中的stringbuffe的字符串缓冲类，这样可以减小内存开销、提高文件的压缩大小上限和速度，现在看代码里的for循环中用的string1+=string2，感觉很傻。。。