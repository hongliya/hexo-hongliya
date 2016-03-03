title: 'javascript函数定义'
date: '2016-02-27'
categories:
	- '技术'
tags: 'javascript'
---

## 函数是什么？

《JavaScript权威指南》第六版中这样定义函数：

> 函数是这样一段JavaScript代码，它只定义一次，但可能被执行或调用任意次。

## 函数定义

下面这两种函数都是使用function关键字来定义。

1. 函数声明。
2. 函数表达式。

<!-- more -->

### 函数声明

定义方式：函数声明

```js
    function foo()
    {
        console.log('定义方式：函数声明');
    }
```

函数声明方式定义函数值得注意的是：

1. 函数名称是必须的部分。
2. 由于javascript变量和函数声明提前的机制，函数声明方式定义的函数在所在作用域里都是可用的。

### 函数定义表达式

定义方式：函数表达式，无名字，又叫匿名函数

```js
    var func = function()
    {
        console.log('定义方式：函数表达式，无名字，又叫匿名函数')
    };
```

定义方式：函数表达式，有名字，又叫命名函数表达式

```js
    var func = function bar()
    {
        console.log(bar);            // 函数本身
        console.log(typeof bar);     // function
        console.log('定义方式：函数表达式，有名字，又叫命名函数表达式')
    };
```

函数表达式也可以作为参数传递给其他函数：

```js
    data.sort(function(a, b) { return a - b; });
```

函数表达式有时候定以后立即调用：

```js
    var square = (function(x) { return x*x; })(10);
```

对于函数表达式来说，值得注意的是：

1. 函数名字是可选的。
2. 如果存在函数名字，该名字只存在于函数体中，相当于该函数体中的一个局部变量，指代该函数对象本身，这在递归时很有用。
3. 通常而言，以表达式方式定义函数时都不需要函数名字，这会让代码更紧凑。
4. 函数表达式特别适合用来定义只会用到一次的函数。
5. 以函数表达式定义的函数在定义之前无法调用（hoist机制）。

## 参考

《JavaScript权威指南》
[细说 Javascript 函数篇（一） : 函数声明和函数表达式](https://segmentfault.com/a/1190000000482011)
[深入理解JavaScript系列（2）：揭秘命名函数表达式](http://www.cnblogs.com/TomXu/archive/2011/12/29/2290308.html)