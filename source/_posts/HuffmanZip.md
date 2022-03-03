---
title: HuffmanZip
date: 2021-08-05 18:37:00
tags:
- 数据结构
- c++
- 学校作业
- 项目
comments: true
toc: true
categories:
- [练手项目]
excerpt: HuffmanZip是一款基于Huffman算法的文本、位图压缩与解压软件，同时还支持对ascii文本的即时Huffman编码与译码。
---

## 简介

HuffmanZip是一款基于Huffman算法的文本、位图压缩与解压软件，同时还支持对ascii文本的即时Huffman编码与译码。

项目地址：https://github.com/Bmaili/HuffmanZip



## 相关图片

![](http://bmalimarkdown.oss-cn-beijing.aliyuncs.com/img/gJfYDK.png)
![](http://bmalimarkdown.oss-cn-beijing.aliyuncs.com/img/gJfUED.png)
![](http://bmalimarkdown.oss-cn-beijing.aliyuncs.com/img/gJfaUe.png)
![](http://bmalimarkdown.oss-cn-beijing.aliyuncs.com/img/gJfJu6.png)



## 用户需求分析

经过我们对许多用户的采访调研，以及对目前市面上比较流行的压缩软件（如bandzip、WinRAR、2345好压）的下载分析，发现用户比较倾向的压缩工具的特点有：使用方便、用户界面友好、在压缩率以及压缩速度方面表现出色，因此需求十分巨大。功能上，需要实现哈夫曼编码译码的基本功能，如课题调研中所述的基本和拓展性功能。性能上，应当考虑更多的更快捷的建树、查找、压缩、解压操作，保证程序的运行速度。此外，还要进行界面的美化，以保证用户的使用体验。



## 说明

1. 大二上学期的数据结构课设。

2. 利用数据结构中的二叉树的哈夫曼树对字符进行编码译码、位图进行压缩和解压并生成对应的文本格式，并采用UI设计，对压缩软件中的文件导入、随机输入、复制编码、字符查询、文件的压缩解压等功能进行模拟。

3. 主要功能有二：

  - 能即时地对输入的文本进行Huffman编码、解码，显示各字符的编码结果，利于使用者对Huffman的直观理解、学习。

  - 利用Huffman编码对文本或位图文件进行数据压缩，同时将压缩信息也写入压缩文件内，故用户也可使用该软件解压之。



## 运行环境
- 开发平台：Desktop QT 5.9.9 MinGW 32bit

- 开发语言：C\C++

- 编译时项目路径不能含中文，编译后可使用Enigma Virtual Box之类的软件打包封装。

- .exe可执行文件 于64位win10测试后通过。

- 可使用提供的文本、图片样例进行测试。



## 总结

选择对BMP位图进行压缩一是因为题目要求，二是因为它的理论压缩比比较可观，压缩“效果好”。

现在来看这个软件还是有许多值得改进的地方的：

1. 代码写得不够优雅，逼死代码洁癖患者

2. 编码译码文本时是利用ascii码值做键，编码译码BMP时是利用灰度值做键，这是一个能提升编码译码效率的巧妙想法，但是问题是不能对ascii码外的字符进行编码了

3. 应该做一个类似Java中的stringbuffe的字符串缓冲类，这样可以减小内存开销、提高文件的压缩大小上限和速度，现在看代码里的for循环中用的string1+=string2，感觉很傻。。。
