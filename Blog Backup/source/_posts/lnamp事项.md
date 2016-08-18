---
categories:
  - Front-end
date: 2016-08-05 16:09
status: public
taags:
  - wordpress
title: lnamp事项
---

关于一键安装包，目录，启动，lnamp,wdcp所用端口的说明

搜集自[wdlinux](http://wdlinux.cn/)论坛咯。

<!--more-->

## 端口说明
默认情况下wdcp的后台是使用到8080端口，可修改

lamp环境里
httpd是用到80端口

lnmp环境里
nginx是用到80端口

## 在lnamp环境里
httpd是用到88端口（不可修改）
nginxd是用到80端口

希望不要再有人问为什么在lnamp环境里,httpd变成了88端口

## 相关的启动命令
service wdapache start|stop|restart    wdcp后台 启动|停止|重起
service nginxd start|stop|restart        nginx服务 启动|停止|重起
service httpd start|stop|restart          httpd服务 启动|停止|重起
service pureftpd start|stop|restart     ftp服务 启动|停止|重起
service mysqld start|stop|restart        mysql服务 启动|停止|重起


## wdcp后台服务环境安装目录（wdcp2后才有，1.X没有）
/www/wdlinux/wdapache wdcp后台用的apache
/www/wdlinux/wdphp wdcp后台用的php

## 相关软件安装目录
/www/wdlinux/nginx   nginx安装目录
/www/wdlinux/apache apache安装目录
/www/wdlinux/pureftpd pureftpd安装目录
/www/wdlinux/Zend zend安装目录

## 默认mysql数据库文件及日志目录
/www/wdlinux/mysql/var

## 虚拟主机配置文件
/www/wdlinux/nginx/conf/vhost
/www/wdlinux/apache/conf/vhost

## 相关配置文件
/www/wdlinux/etc/my.cnf
/www/wdlinux/etc/php.ini
/www/wdlinux/nginx/conf/nginx.conf
/www/wdlinux/php/etc/php-fpm.conf
/www/wdlinux/apache/conf/httpd.conf
/www/wdlinux/apache/conf/httpd-wdl.conf
/www/wdlinux/etc/pure-ftpd.conf
/www/wdlinux/etc/pureftpd-mysql.conf

## 默认web日志目录
/www/wdlinux/nginx/logs
/www/wdlinux/apache/logs
也可以在后台设置默认是
/www/web_logs


## 默认备份文件目录(后台可设置)
/www/backup

## 默认回收站目录(后台可设置)
/www/trash

## phpmyadmin
v3版的phpmyadmin连接和访问，做了比较大的调整
不再使用直接在后台的访问方式，而是要使用前端WEB地址来访问
默认的访问地址如 http://ip/pma_xxx
基于安全考虑，xxx为随机生成的字串，在安装时自动生成
文件存放在默认目录/www/web/default下
如/www/web/default/pma_d51f5b16
要确保默认首页能访问并且是指向到/www/web/default目录

也可以使用或自定义其它名字，如phpmydb
则在后台的phpmyadmin栏目里设置为phpmydb就可以

还可以使用一个URL地址，如
http://mydomain.com/phpmyadmin
则在后台的phpmyadmin栏目里设置为上面这个地址即可

如果上述的URL地址打不开或是502，请检查/www/web/default目录下有没相应的目录文件