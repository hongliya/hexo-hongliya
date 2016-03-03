title: 'mac配置apache'
date: '2014-10-08'
categories:
	- '技术'
tags: 'mac,apache'
---

**启动apache**

```shell
sudo apachectl start
```

**重启apache**

```shell
sudo apachectl restart
```
<!-- more -->

**打开Apache的配置文件**

```shell
sudo vi /etc/apache2/httpd.conf
```

**查看Apache的错误日志**

```shell
sudo vi /pravite/var/log/apache2/error_log
```

**配置web目录**

修改两个地方
1. DocumentRoot “你要设置的web目录”
2. &lt;Directory “你要设置的web目录”&gt;

![image](/assets/postimg/apache.jpg)