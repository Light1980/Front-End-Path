---
title: '永久更改Ipython Notebook或Jupyter Notebook的默认目录'
date: 2016-05-12 16:44
categories:
    - Data Science
tags:
    - Python
---

方案来自[Stackoverflow](http://stackoverflow.com/questions/15680463/change-ipython-working-directory)zhangxaochen，这里记录存档。

<!-- more -->

## Ipython Notebook

打开命令行：

```bash
ipython profile create
```

这个命令会初始化一份配置文件`ipython_notebook_config.py`，打开后找到如下一行：

`# c.NotebookManager.notebook_dir = 'D:\\love\cat'`

如果没有，请找到这一行：

`# c.NotebookApp.notebook_dir = 'Z:\\luv\cat'`

去掉最开始的注释和空格，修改路径为自己想要的。

## Jupyter Notebook

打开命令行：

```bash
jupyter notebook --generate-config
```

同样会生成一份配置文件`jupyter\jupyter_notebook_config.py`，打开后找到下面这一行：

`# c.NotebookApp.notebook_dir = u'D:\\love\you`

去掉最开始的注释和空格，修改路径为自己想要的。