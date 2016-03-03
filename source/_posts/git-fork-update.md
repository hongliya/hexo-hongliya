title: 'Fork过来的代码如何与源代码保持同步更新'
date: '2015-05-04'
categories:
	- '技术'
tags: 'git'
---

最近参与到公司的开源项目，学会了Pull Requests，但不知道如何把Fork过来的代码与源代码保持同步更新，即源代码变化后，我这边还是保持不变的。

然后用了一个很笨的方法，把fork的项目删了之后，再fork一份过来，但这种方法实在太麻烦了，今天找了各种资料后终于解决了这个问题，步骤如下：

<!-- more -->

我是使用命令搞定的

1.进入本地的项目目录，我的目录名称是 Flagwind.UI

```
cd Flagwind.UI/
```

2.增加源分支地址到你项目远程分支列表中，先得将原来的仓库指定为upstream

```
git remote add upstream https://github.com/被fork的仓库.git
```
执行此命令后可用`git remote -v`命令查看结果

```
origin	https://hongliya@github.com/hongliya/Flagwind.UI.git (fetch)
origin	https://hongliya@github.com/hongliya/Flagwind.UI.git (push)
upstream	https://github.com/Flagwind/Flagwind.UI.git (fetch)
```

3.fetch源分支的新版本到本地

```
git fetch upstream
```

4.合并两个版本的代码

```
git merge upstream/master
```
完成第4步后，源代码的最新版就同步到本地了，接下来就可以同步到自己的github上去了

### 参考

[GitHub——如何更新已经fork的代码](http://www.cnblogs.com/zyumeng/p/3442263.html)

[git - 简易指南](http://www.bootcss.com/p/git-guide/)