---
layout: post
title: "Mysql install"
tagline: ""
description: ""
category: 
tags: [linux, mysql]
last_updated: 
---

mysql下载地址

https://downloads.mysql.com/archives/community/ 

### 安装

```shell
rpm -e mysql-libs-5.1.73-8.el6_8.x86_64 --nodeps
rpm -ivh MySQL-devel-5.6.35-1.el6.x86_64.rpm
rpm -ivh MySQL-server-5.6.35-1.el6.x86_64.rpm
rpm -ivh MySQL-client-5.6.35-1.el6.x86_64.rpm
```

密码文件

```shell
cat ~/.mysql_secret
```

修改密码

```shell
mysqladmin -u root --password='snLsjqzvZ4OKbajj' password '123456'
```

数据文件位置

/var/lib/mysql



配置文件目录

/usr/share/mysql              
             

配置文件

```shell
cp /usr/share/mysql/my-default.cnf /etc/my.cnf
```

```shell
service mysql start
```

修改root密码

```shell
use mysql;
select host,user,password from user;
GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' IDENTIFIED BY '123456' WITH GRANT OPTION;
FLUSH PRIVILEGES;
select user,host,password from user; 
```

开机启动

```shell
chkconfig mysql on
```



