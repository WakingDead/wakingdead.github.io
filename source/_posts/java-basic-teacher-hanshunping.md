---
title: 零基础JAVA课程笔记
date: 2022-04-24 10:25:03
tags:
    -- JAVA
    -- 技术
categories: 
  - JAVA
---

# 第1章 内容介绍
---
## 本套Java课程内容

课程阶段

+ 第一阶段：建立编程思想

+ 第二阶段：提升编程能力

+ 第三阶段：分析需求，代码实现能力

# 第2章 JAVA 概述
---
什么是程序？
计算机执行某些操作或解决某个问题而编写的一系列有序指令的集合

举例：计算机怎么完成1 + 1, 并把答案显示在电脑上
1. 写一个程序（文件） 
    int Res = 1 + 1
    System.out.printIn("结果" = res)

2. 把程序交给计算机执行
    首先执行第一条语句，得到Res = 2
    然后执行第二条语句，输出"结果" = 2

完整程序Hello_test.java，完成1+1并输出
写一个程序
``` java
public class Test {
    public static void main(String[] args){
        int res = 1 + 1
        //显示

        System.out.printIn("结果=" + res);
    }
}
```
输出
> 找到该程序的文件夹所在地，在最上面的目录栏目，输入cmd，然后在终端中先编译该文件（需要先把JDK配置好），然后输入javac Hello_test.java，对文件进行边缘，然后输入java Hello_test, 就能够正确输出结果了

## 2.2 JAVA历史（非重点，略过）
## 2.1 JAVA特点
1. Java语言是面向对象的（oop）
2. JAVA语言是健壮的。JAVA的强类机制、异常处理、垃圾的自动收集等是JAVA程序健壮性的重要保证
3. Java语言是跨平台性的。
    一个编译好的.class文件可以在多个系统下运行
    编写一个.java程序，编译之后得到.class文件，该文件可以在不同的操作系统上运行而不用重新编译（相当于出国，自带翻译）


4. Java语言是解释型的
    解释性语言：javascript,php,java 编译型语言：c/c++
    区别是：
    解释性语言：编译后的代码，不能直接被机器执行，需要解释器来执行
    编译性语言，编译后的代码（已经是二进制了），可以直接被机器执行，c/c++

    具体而言，编译过后得到的class文件需要一个解释器来执行class文件

Java的开发工具
+ editplus、notepad++
+ Sublime Text 下载地址：https://www.sublimetext.com/3
+ IDEA
+ eclipse

+ 工具选择
    前期用文本编辑器，到大家对java有一定了解之后，我们再使用IDEA和Eclipse开发工具
## 2.3 JAVA运行机制以及运行过程

### 2.3.1 Java语言的特点，跨平台性
 > Test.Java程序 →(这个过程叫编译, 命令是javac) Test.class →(这个过程叫运行，命令是java) 通过JVM在不同的操作系统上运行
 > 因为有了JVM，同一个Java程序在三个不同的操作系统中都可以执行。这样就实现了Java程序的跨平台性
 > JVM包含在JDK里面

### 2.3.2 Java核心机制 —— Java虚拟机(JVM java virtual machine)
> 基本介绍
1. JVM是一个虚拟的计算机，具有指令集并使用不同的存储区域。负责执行指令，管理数据、内存、寄存器，**包含在JDK中**。
2. 对于不同的平台，有不同的虚拟机。（跨平台性的实现）
3. Java虚拟机机制屏蔽了底层运行平台的差别，实现了“一次编译，到处运行”
    见图2.3.1
<image  src = "H:\computer_science_study\personal_website\github\wakingdead.github.io\source\images\java-basic-teacher-hanshunping-2.3.1.png">

### 2.3.2 什么是JDK？什么是JRE
**JDK基本介绍**
+ JDK的全称是（JAVA Development Kit, **JAVA开发工具包**）
  + **JDK = JRE + java的开发工具**[java, javac, javadoc, javap等]
+ JDK是提供给开发人员使用的，其中包含了Java的开发工具，也包括了JRE。所以安装了JDK，就不用再单独安装JRE了

**JRE基本介绍**
+ JRE（Java Runtime Environment， **Java运行环境**）
  + JRE = JVM + java的核心类库[类]
+ 包括Java虚拟机（JVM java Virtual Machine）和Java程序员所需的核心类库
+ 如果想要运行一个开发好的Java程序，计算机中只需要安装JRE即可
> 即程序的开发者需要完整的JDK，但是程序的使用者只需下载JRE即可

**小结 JDK、JRE和JVM的包含关系**
1. JDK = JRE + 开发工具集（例如Javac, java编译工具等）
2. JRE = JVM + JavaSE标准类库(java核心类库)
3. JDK = JVM + Java SE标准类库 + 开发工具集
4. 如果只想运行开发好的.class文件 只需要JRE


## 2.4 JAVA开发环境搭建
### 2.4.1 配置环境变量path
为什么要配置path？ 为了打开DOS命令行，在任意目录下敲入javac/java 都可以执行
看一个现象→在dos命令行[快捷键 win + r]中敲入javac，出现错误提示
> 错误原因：当前执行的程序在当前目录下如果不存在，win10系统会在系统中已有的一个名为path的环境变量指定的目录中查找，如果仍然未找到，会出现以上的错误提示。
> 所以进入到 jdk安装路径\bin目录下，输入cmd，执行javac，会看到javac参数提示信息。
配置环境变量path的步骤
1. 我的电脑--属性--高级系统设置--环境变量
2. 增加JAVA_HOME环境变量，指向jdk的安装目录（本电脑的是H:\computer_science_study\java\jdk，以后换新的电脑直接 d:\program\hspjdk8）
3. 编辑path环境变量，增加%JAVA_HOME%\bin
4. 打开DOS命令行，任意目录下敲入javac/java。如果出现javac的参数信息，配置成功
   javac - version
   java - version

备注：苹果的下载不一样，但是现在我没买苹果，以后有钱再看吧

配置环境变量时，Administrator的用户变量和系统变量的区别？
> 前者只对当前用户生效，换了用户之后就不生效了，后者系统下所有用户都生效

## 2.5 DOS常用指令
+ 善用上下光标调用命令，特别是重复的

## 2.6 JAVA快速入门

### 2.6.1 快速入门实例
+ 需求说明
  要求开发一个Hello.java 程序，可以输出"hello, world"

+ 开发步骤
    1. 将Java代码编写到扩展名为Hello.java的文件中。[代码说明]
    2. 通过javac命令对java文件进行编译，生成.class文件。
    3. 通过java命令对生成的class文件进行运行（运行的时候不要运行java Hello.class, 运行java Hello即可。这是规定，同时在运行的时候java Hello就是运行的Hello这个类，如果是java Hello.class, 运行的则是Hello.class这个类，查找不到）

+ 运行原理示意图
  + 查看java-basic-teacher-hanshunping-2.3.1

练习2.6.1：开发一个Hello2.java 程序，可以输出"老王 is studying Java"


> Sublime Text 鼠标+滑轮可以调整大小
> Sublime Text的文件的编码（文件有中文的时候）要调整成GBK，file → save with encoding → chinese，记得重新保存
> 可以在控制台顶部白框，右键属性，查看当前代码页的编码

### 2.6.2 java执行流程分析

**编写.java文件（源文件）→ javac（程序是javac.exe, 运行的时候直接写javac） 编译 → .class文件（字节码文件） → java 运行（对应的程序是java.exe, 这个运行的本质是把.class文件装载到虚拟机里面去执行）→ 结果**

什么是编译？

javac Hello.java

1. 有了java源文件，通过编译器将其编译成JVM可以识别的字节码文件（.class）
2. 在该源文件目录下，通过javac编译工具对Hello.java文件进行编译
3. 如果程序没有错误，没有任何提示，在当前目录下会出现一个Hello.class文件，该文件为字节码文件，也是可以执行的java的程序
   2022.5.6 看到了P17的02：23
   