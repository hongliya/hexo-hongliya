title: 'css边框探索'
date: '2015-07-24'
categories:
	- '技术'
tags: 'css'
---

对border的理解一直是会用的状态，原理不清楚，准备探索下。

平时经常写的边框样式：

```css
.border
{
	width: 100px;
	height: 100px;
	border: 2px solid red;
}
```

效果是这样的：

![image](/assets/postimg/border1.png)

因为颜色一样所以不容易看到边框的形状，现在给每条边设置成不同的颜色

```css
.border
{
	width: 100px;
	height: 100px;
	border-top: 5px solid red;
	border-right: 5px solid yellow;
	border-bottom: 5px solid blue;
	border-left: 5px solid green;
}
```

可以看到效果是这样的：

![image](/assets/postimg/border2.png)

放大后：

![image](/assets/postimg/border3.png)

放大后可以清楚的看出每条边的边框都是梯形的，当我们把元素的长和宽都缩小到0时，梯形边框会变成三角形，于是就有了如下的效果：

```css
.border
{
	width: 0;
	height: 0;
	border-top: 5px solid red;
	border-right: 5px solid yellow;
	border-bottom: 5px solid blue;
	border-left: 5px solid green;
}
```

![image](/assets/postimg/border4.png)

这为我们绘制三角形提供了一个思路，把其他三边的边框设置成透明（transparent）即可得到一个三角形，如下：

```css
.border
{
	width: 0;
	height: 0;
	border-width: 50px;
	border-style: solid;
	border-color: red transparent transparent transparent;
}
```

效果：

![image](/assets/postimg/triangleUp.png)

关于各种三角形，后面有时间再总结。