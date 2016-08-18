---
title: 网易云音乐加载失败了
date: 2016-05-09 15:24
categories:
    - Bug of Life
---

某天我打开电脑，发现桌面版网易云音乐什么歌都播放不了，提示“加载失败”。

<!-- more -->

## 问题分析

但我的网确实木有问题。

百度上找了找各类回帖，最终发现一个比较靠谱的答复：“发现和我的VPN工具有关。”

顿时联想到了自己用ss翻墙时偶尔遇到的dns缓存问题，所以抱着试试的心情打开了网页版云音乐。

“抱歉，网页加载失败。”

到这里我的内心就毫无波动了，甚至有一点想笑。

## 方案
`win + x` 打开**命令提示符（管理员）**

输入：

``` bash
ipconfig/flushdns
```

重新启动电脑，一切正常了。