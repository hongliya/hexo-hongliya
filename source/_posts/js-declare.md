title: 'javascript中变量的声明'
date: '2016-02-23'
categories:
	- '技术'
tags: 'javascript'
---

## javascript中的变量声明

javascript使用var关键字来声明变量。

```js
    var i;                      // 声明一个变量i，初始值是undefined
    var sum;                    // 声明一个变量sum，初始值是undefined
    var i, sum;                 // 声明多个变量，i和sum的初始值都是undefined
    var message = 'hello';      // 声明一个变量并赋值，message的初始值是hello
    for (var i = 0; i < 5; i++) // 在for循环中声明变量
    {
        console.log(i);
    }
```
上名声明变量的几种形式，在代码中经常用到，值得注意的是：在声明一个变量的时候如果没有指定初始值，那么它的初始值就是undefined。

<!-- more -->

## javascript变量声明不用指定数据类型

javascript是弱类型语言，跟强类型语言不同，在声明变量时不用指定变量的数据类型，变量可以是任意类型。

```js
    var a = 1; // 这里a的值是一个数字
    a = 'ten'; // 这里将一个字符串赋值给a，这样是完全合法的
```

## 重复的声明

> 使用var语句重复声明变量是合法且无害的。如果重复声明带有初始化器，那么这就和一条简单的赋值语句没什么两样。

《javascript权威指南》中是这样解释重复的声明的，但我不知道重复声明带初始化的变量时，会不会重新分配一块内存？

## 参考

《javascript权威指南第六版》