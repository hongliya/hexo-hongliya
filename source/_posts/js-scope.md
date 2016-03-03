title: 'javascript执行环境'
date: '2016-02-25'
categories:
	- '技术'
tags: 'javascript'
---

## 模拟执行环境

javascript每调用一个函数就会创建一个新的执行环境，创建执行环境分为两个阶段：

1. 建立阶段
  * 建立作用于链
  * 建立变量、函数、参数
  * 确定this
2. 赋值阶段
  * 赋值

<!-- more -->

接下来模拟这段代码：

```js
var foo = function(i)
{
    var a = 'hello';
    var b = function B() { };
    function c() { };
};

foo(22);
```

**第一阶段（建立）**

```js
fooExecutionContext =              // 执行环境
{
    scopeChain: { ... },           // 建立作用域链
    variableObject:                // 建立变量
    {
        arguments:
        {
            0: 22,
            length: 1
        },
        i: 22,
        c: pointer to function c(),
        a: undefined,
        b: undefined
    },
    this: { ... }                  // 确定this
}
```

**第二阶段（赋值）**

```js
fooExecutionContext =              // 执行环境
{
    scopeChain: { ... },           // 建立作用域链
    variableObject:                // 建立变量
    {
        arguments:
        {
            0: 22,
            length: 1
        },
        i: 22,
        c: pointer to function c(),
        a: 'hello',
        b: pointer to function B()
    },
    this: { ... }                  // 确定this
}
```

这也解释了javascript中变量和函数声明提升的问题。

## 参考

[Javascript 中的執行環境與堆疊](https://segmentfault.com/a/1190000004491834)