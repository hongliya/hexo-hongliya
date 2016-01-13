title: '如何干净的卸载Sublime'
date:  '2015-04-13'
categories:
	- '技术'
tags: 'sublime'
---

## 卸载Sublime编辑器

Sublime Text 2 和 Sublime Text 3 的安装和卸载方式是一样的，这里记录的是Mac系统下Sublime的卸载方法。

Mac下的 Sublime Text 插件安装位置

1.通过命令打开

```
// ~ 表示个人工作目录
~/Library/Application Support/Sublime Text 2/Packages
```

2.通过Sublime Text 2 --> Preferences --> Browse Packages 方式打开

### 1. 卸载 Sublime

如果想完全卸载Sublime，只删除 Sublime Text.app 或用 cleanMyMac2 卸载是卸不干净的，因为只卸载了app，插件还是保留了的，这时可以找到上面的插件安装目录，把Sublime Text 2 目录整个删除了，就可以完全卸载干净了。

### 2. 重装 Sublime

如果是出了bug，只是想先卸载然后重新安装，也就是获取一个全新的没有插件的Sublime，这个就没那么麻烦，可以直接找到插件目录，把整个目录删除，重启Sublime，就可以得到一个全新的，没有任何插件的Sublime了。

## 参考

[sublime text2卸载和重新安装](http://www.cnblogs.com/ayseeing/p/3637753.html)