title: 'javascript中变量和函数声明提前'
date: '2016-02-24'
categories:
	- '技术'
tags: 'javascript'
---

有道词典上这样解释hosit：

> hosit [hɔɪst]
> n. 起重机；升起，吊起
> vi. 升起；吊起
> vt.（用绳索，起重机等）使升起

在《JavaScript权威指南》中解释为“提前”。

<!-- more -->

## 变量声明提前

**代码一：打印没有定义的变量会报变量未定义错误**

```js
$(function()
{
    console.log(scope); // Uncaught ReferenceError: scope is not defined
});
```

**代码二：变量声明之前打印，值是undefined**

```js
$(function()
{
    console.log(scope); // undefined
    var scope = 'global';
    console.log(scope); // global
});
```

上面代码第一行打印的结果是`undefined`，第三行的结果是`global`。
为什么会出现这样的结果？这是因为**javascript解析器将作用域内的变量声明提前了**，但赋值还保留在原地，所以上面的代码对解析器来说是这样的：

```js
$(function()
{
    var scope;          // 声明被提到作用域的最开始处了
    console.log(scope); // undefined
    scope = 'global';   // 赋值操作还在原地
    console.log(scope); // global
});
```

根据javascript语法的定义，**已声明而未被赋值的变量会被自动赋值为undefined**，所以第一句打印出`undefined`，赋值后第二句打印出`global`。

## 函数声明提前

前面说的是变量声明提前，下面说函数声明提前。

函数声明提前分为两种：
1. 函数声明
2. 函数作为值赋给变量

**代码一：函数声明提前**

```js
isHosited(); // 我被提前了

function isHosited()
{
    console.log('我被提前了');
}
```

函数声明提前并不是只有函数声明被提前了，整个函数都被提前了，所以上述代码能够正确执行。对解释器来说上面的代码是这样的：

```js
function isHosited()
{
    console.log('我被提前了');
}

isHosited(); // 我被提前了
```

**代码二：函数作为值赋给变量**

```js
isHosited(); // Uncaught TypeError: isHosited is not a function

var isHosited = function()
{
    console.log('我被提前了?');
}
```

根据变量声明提前来看，上面代码对解析器来说是这样的：

```js
var isHosited;

isHosited(); // Uncaught TypeError: isHosited is not a function

isHosited = function()
{
    console.log('我被提前了?');
}
```

由于“变量提前”的默认值是`undefined`，所以报的错误是“isHosited is not a function（类型不匹配）”。

## 总结

1. 变量的声明被提前到作用域的顶部，默认值是‘undefined’，赋值保留在原地。
2. 函数声明整个被提前。
3. 函数作为值赋给变量时，只有变量声明被提前，函数没有被提前。
4. 声明变量时尽量把声明写在作用域的顶部，这是一个好习惯。

## 参考

[JavaScript 中对变量和函数声明的“提前（hoist）”](http://www.bootcss.com/article/variable-and-function-hoisting-in-javascript/)