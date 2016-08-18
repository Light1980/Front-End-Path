---
categories:
  - Front-end
date: 2016-07-30 16:29
status: public
taags:
  - wordpress
title: WordPress问题杂谈
---

Common knowledge is written by unknown，很多时候真正解决问题的是谁已经无法找到了。所以我就不再去引用解决方案出处，Everyone is a contributer，让知识传承下去就是对原始作者最好的纪念。

当然，我绝不保证我的二手乃至三手四手知识是毫无问题的，一定存在错误，只是刚好能解决我所遇到的情况而已。热烈欢迎指正~

<!--more-->

## 我的环境

服务器：Vultr VPS/Ubuntu 14.04 LTS x86
装修：自豪地采用[LNMP一键安装包1.2](http://lnmp.org)
环境： Ubuntu 14.04 LTS/PHP 5.6/MySQL 5.5/1.8.1
  
服务器：美团云/CentOS 6.5 x86
装修：无情地采用[wdCP一键安装包V3](http://wdlinux.cn/)
环境：/CentOS 6.5 x64

## WordPress上传权限问题

**问题概述**：

安装插件需要FTP权限/上传不了主题……

**解决方案**：

给你的wordpress目录加上权限。

```
chmod -R 755 /home/domain

chown -R www:www /home/domain
```

## 固定链接在nginx上引起的404问题

**问题概述**：
安装主题后发现只有首页打得开，其他页面都打不开了变成404/修改固定链接后发现文章都是404……
解决方案：

在网站的nginx配置文件中补充一段重写代码：

```
// 注意你需要把以下代码放在server{}中
location / {  
        index  index.php index.html index.htm;  // 这个在lnmp的虚拟主机配置中已经有了
  
        if (-f $request_filename/index.html){  
               rewrite (.*) $1/index.html break;  
        }  
        if (-f $request_filename/index.php){  
               rewrite (.*) $1/index.php;  
         }  
        if (!-f $request_filename){  
               rewrite (.*) /index.php;  
         }  
         }  
         rewrite /wp-admin$ $scheme://$host$uri/ permanent;
```

修改完毕重启nginx。

## 网站访问缓慢问题

**问题概述**：

1. 引用了大量谷歌资源。
2. 博客中图片太多。

**解决方案**：
1. 安装**Google font fix**插件，自动替换谷歌CDN。

2. 使用七牛给图片做CDN，然后使用WP Super Cache/WP Rocket等插件引用回来。

## SMTP和Nginx 502

**问题概述**：

我的环境中使用Google的smtp会出现502错误，QQ无法通过密码检查。

**解决方案**：

使用了hotmail的smtp服务，Google问题尚未解决。

常见smtp：

Gmail

+ SMTP Host: smtp.gmail.com
+ Type of Encryption: SSL
+ SMTP Port: 465

Yahoo

+ SMTP Host: smtp.mail.yahoo.com
+ Type of Encryption: SSL
+ SMTP Port: 465

Hotmail

+ SMTP Host: smtp.live.com
+ Type of Encryption: TLS
+ SMTP Port: 587

Outlook

+ SMTP服务器：smtp-mail.outlook.com
+ 加密类型：TLS
+ 端口：25

## Nginx 504超时问题

在`nginx.conf`的http层加入：

```
fastcgi_connect_timeout 300s;

fastcgi_send_timeout 300s;

fastcgi_read_timeout 300s;

fastcgi_buffer_size 128k;

fastcgi_buffers 8 128k;#8 128

fastcgi_busy_buffers_size 256k;

fastcgi_temp_file_write_size 256k;

fastcgi_intercept_errors on;
```

重启Nginx(`service nginxd restart`)

在`php-fpm.conf`中修改`max_children`和`request_terminate_timeout`，视服务器状况而定。

据说（N手资料）一个php-cgi进程占用内存在10M-20M，所以1G内存设置30-40个子进程会不错。

而`request_terminate_timeout`修改到900就差不多了，服务器配置好的可以使用0。

最后重启php-fpm(/etc/init.d/php-fpm restart)

## 上传文件大小超过了`upload_max_filesize`。

SSH到主机，Vim打开php.ini文件，找到`upload_max_filesize`项目，修改成合适的值。

重启Nginx和php-fpm。

## 使用IP访问虚拟主机

这只是在**wdCP**下的解决方案。

新建站点——域名填写`default`——目录指向你的虚拟主机。

完成。

但最后发现其实没啥用，该备案的时候还得关闭域名解析。然后IP访问网站会出问题，各种404.