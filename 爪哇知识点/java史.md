# 前言

主要内容：

- Java语言特点
- Java的源文件(`.java`)和字节码文件(`.class`)
- Java的应用程序和小程序的主类
- Java虚拟机
- Java程序的种类和结构
- Java应用程序和小程序的差异

Java语言是一种简单易用 、完全面向对象、与平台无关、安全可靠、主要面向Internet的开发工具

# 诞生与发展

Java的前身是[Sun Microsystems](https://baike.baidu.com/item/Sun Microsystems/6064586)公司——升阳公司（sun）于2009年被Oracle(甲骨文)收购，开发的用于一种用于智能化家电的名为Oak（橡树）的语言，它的基础是c/c++

Java的名字来源于太平洋上盛产咖啡的爪哇岛（java)

# Java语言特点

Java is a simple,object-oriented, distributed, interpreted, robust, secure, architecture-neutral, portable, high-performance, multi-threaded, dynamic language.

Java 是一种简单的、面向对象的、分布式的、解释型的、可靠的、安全的、平台无关性的、可移植的、高性能的、多线程的、动态的语言。

重点解释几个点

### 面向对象

这里就是java与c的区别，一切以对象为中心支持：1.封装 2.继承 3.多态

- 封装

  何为封装，就是让user接触到最为简单直接的使用。官方意思是，利用抽象数据类型将数据和基于数据的操作封装在一起数据被保护在抽象数据类型的内部，系统的其他部分只有通过封装在数据外面被授权的工作，才能与这个抽象数据类型交互

  （其实就是一辆汽车，作为使用者只需要知道基本的油门刹车离合挂挡等操作，而至于汽车的发动机如何驱动，齿轮之间如何咬合，这些都被封装为一体，作为使用者不需要知道）

- 继承

  继承是指一个对象直接使用另一个对象的属性和方法。Java给用户提供了一些列的类，子类可以继承父类的属性和方法

- 多态

  多态是指一个程序中同名的多个不同方法共存的情况，即一个对外接口，多个内在实现的方法

### 平台无关性

这个不难理解，平台无关性就是一种语言在计算机上的运行不受平台的约束，一次编译，到处执行也就是说，用 Java 创建的可执行二进制程序(.class)，能够不加改变的运行于多个平台

PS: 平台无关性分为两种，源代码级和目标代码级

C/C++具有一定程度的平台无关性，即应用程序换个平台重新编译就可以运行于不同的平台

java语言是靠java虚拟机(jvm)在目标代码级实现平台无关性

### 网络编程

Java语言通过它所提供的类库可以处理`TCP/IP`协议，用户可以通过URL地址在网络上访问其他对象。Java的小程序(`Applet`)可以嵌入在HTML文档中然后发布到因特网，然后可以在支持Java的浏览器中运行

# 版本技术

##  1.Java SE

java的标准版，也是用量最大，最广泛的版本

## 2.Java ME

java的精简版

## 3.Java EE

java平台的企业版，以企业为环境开发的应用程序的解决方案



| 目前主流的Java环境         |
| --------------------------------------
| JDK系列（Sun）命令行  
| Java WorkShop（Sun）                   |
| Visual CAFÉ (Symantec)                 |
| JBuilder (Borland)                     |
| Visual  J++ (MicroSoft)                |
| Java  Studio (Sun)                     |
| Jdeveloper (Oracle)                    |
| Visual  Age  for  Java (IBM)           |
| Code Warrior Professional (Metrowerks) |

# Java虚拟机

大部分计算机语言都先进行编译或者解释之后才能在计算机上运行，例如C/C++属于编译型语言，而Python属于解释型语言。但是Java程序(.java)比较特殊，它是先经过编译的过程，然后通过解释器在计算机上运行。经过编译器之后java文件会被转成平台无关的机器码（这也是java具有平台无关性的原因之一），java中称之为字节码(byte-codes)后缀名为`.class`。然后通过java解释器运行字节码

字节码是虚拟机(JVM)的指令组，与CPU上的微指令码很相似

​         ![image-20220312212353129](https://s2.loli.net/2022/03/12/fYFSnXeWE4K7JmA.png)



字节码(.class)的好处就是跨平台运行，即Java的字节码可以编写一次到处运行，只要所在平台上有JVM,因此可以将java的字节码看场JVM上运行的机器码，所以假想的，JVM即以java字节码为指令组的软CPU，即运行字节码的假想计算机

# 程序种类和结构

Java语言可以编写两种类型的程序，Application(应用程序)和Applet(小程序)，这两种程序的开发原理是相同的，但是在运行环境和计算结构上却有着显著的不同

应用 程序是从命令行运行的程序，它可以在Java平台上独立运行，通常称之为Java应用程序，在命令行调用独立的解释器软件即可运行出结果

小程序是嵌入在HTML中的Java程序，需要搭配浏览器运行，因此称之为小程序。当运行一个小程序时，同时还需要为它编写一个HTML文件，然后在`WWW`浏览器中运行这个HTML文件，就可以激活浏览器中内置Java解释器

但是，无论是应用程序还是小程序都必须要有一个主类，主类是程序运行的起始点（这里和C/C++中的`main`函数类似），应用程序的主类是包含`main()`方法的类，但是应用程序的主类并不一定要求是`public`类；小程序的主类必须是一个继承自系统类`JApplet`或`Applet`的子类，且该类必须是`public`类

# Hello World

以上就是Java的历史和概述，下面让我们来杯印尼岛上的咖啡吧

```java
public class helloworld{
    public static void main(String[] args){
       System.out.print("Hello World");

    }
}
```

写博客真累，腰酸背疼 ，我睡觉了😮‍💨

