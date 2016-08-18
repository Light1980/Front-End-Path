---
title: 如何让Python2和Python3共存
date: 2015-12-31 20:28:22
categories:
    - Data Science
tags:
    - Python
---

尽管我Python2都还没有怎么用好，Python3已经变得越来越流行了。为此，我也得赶紧拾掇拾掇高高兴兴地跟上潮流。在已经有安装好Python2的Windos上安装Python，我们遇到的一个问题就是：如何做到让两个不同版本的Python共存于一个系统中，并且可以方便地切换？

<!-- more-->

过程是比较简单的，分别安装python2.7和python3.5，我自己选择装在了D盘。然后在环境变量中添加以下内容：

```
D:\Python35;D:\Python35\Scripts;D:\Python27;D:\Python27\Scripts
```

打开命令行发现，默认的Python版本应该是3.5。

进入python2的目录，将python.exe和pythonw.exe修改成:

```
python.exe -> python27.exe
pythonw.exe -> pythonw27.exe
```

到此就基本完成了。

以后在Python脚本中，根据版本需求在第一行添加任意一条语句即可：

``` 
#!D:\Python35\python.exe 或 #!D:\Python27\python27.exe

#!python3 或 #!python2

#!/usr/bin/env python3 或 #!/usr/bin/env python2
```

最后，有关pip的问题，python3安装时自带pip。所以在使用时将pip命令换成`pip2`，即是调用Python2的pip；换成`pip3`，即是调用python3的pip。

不过对于我这种非程序员来说，pip安装科学计算包显得很麻烦。我是一个嫌麻烦的人，所以自己的对策是用学生邮箱注册Enthought Canopy或者安装Anaconda、Python(x,y)等集成环境……

<hr>

<a href="http://creativecommons.org/licenses/by-sa/4.0/" rel="license"><img style="border-width: 0;" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" alt="Creative Commons License" /></a><br />
This work is licensed under a <a href="http://creativecommons.org/licenses/by-sa/4.0/" rel="license">Creative Commons Attribution-ShareAlike 4.0 International License</a>.