---
date: 2016-06-05 12:05
status: public
title: Jupyter Notebook Guide
---

Update:
2016-05-29：<del>还在挣扎还在挣扎，这个坑挖好了，一周填。</del>
2016-06-05：施工完毕。

---

Jupyter Notebook简明使用指南。

> Shout out to Ms. Flower

<!-- more -->

素材来源：

+ [Quannnnnnnnnnnnt-econ.net](http://quant-econ.net)

+ [Jupyterrrrrrrrrrrrrrrrr Official Document](http://jupyter.readthedocs.io/en/latest/content-quickstart.html)


## 什么是Jupyter Notebook

+ 基于浏览器的Python IDE。

+ 生成富文本报告（包含源码，运行结果，图片，HTML文本，etc.）的工具。

+ 方便的Python项目分享平台（懒人抄笔记专用哪）。

+ R user羡慕嫉妒恨的东西之一（不过最近貌似是翻身做主人了）

这些大概都是废话，我们进入正题……

## 安装

首先，下载安装[Anaconda](https://www.continuum.io/downloads)，一个流弊的科学计算平台。

> Q：为什么用Anaconda？
> A：懒。
> Q：其实我已经有了Ipython Notebook，只是想迁移到Jupyter.
> A：参照[Migrating from IPython Notebook](https://jupyter.readthedocs.io/en/latest/migrating.html)

下载时有Python2.7和Python3.5两种安装版可以选，但其实无所谓，Anaconda中可以创建虚拟环境使得多个Python版本并存。

> Q：我已经安装过Python或者Enthought Canopy之类的东东了，咋办？
> A：一了百了，全卸载了。
> Q：劳资不！
> A：使用`pip install jupyter`或`pip3 install jupyter`安装Jupyter Notebook。 

## 运行

Anaconda安装完成后自带Python、Jupyter Notebook以及Spyder IDE等。

所以直接打开命令提示符工具，输入：

``` bash
jupyter notebook
```

这将在本地8888端口运行起一个Jupyter Notebook服务并自动打开浏览器。

> http://localhost:8888/

Jupyter Notebook允许**同时创建多个服务端**，端口号依序排列。

如果想**自定义端口**，可以执行如下命令：

``` bash
jupyter notebook --port [port number]
```

如果想**无浏览器启动**：

``` bash
jupyter notebook --no-browser
```

**启动选项**查看命令：

``` bash
jupyter notebook --help
```

## 你的第一个Notebook，也是我的

### 创建与命名
进入主界面(dashboard)，默认目录是Jupyter Notebook服务起始运行的目录，所以文件之多很可能会把眼睛亮瞎。故而可以参照我另一篇[永久更改Ipython Notebook或Jupyter Notebook的默认目录]()进行修改。

点击右上角`New`按钮，选择`Python3`，创建一本新的Notebook。

![websitememory](/uploads/jupyterNotebookGuide-01.gif)

回到主界面，我们会看到这本新创建的Notebook已经显示在了工作目录中，并且在最右会有一个绿色的`running`字样。这表示这本Notebook已经连接到了一个[ipython kernel](http://ipython.org/ipython-doc/dev/overview.html#ipythonzmq)中，可以执行我们输入的代码并返还结果。即使关闭了Notebook本身所在的浏览器页面，Jupyter依然会在后台保持与kernel的连接（所以我们的运行结果不会丢失）。如果想停止连接，主界面勾选Notebook后并执行`shutdown`选项即可。

### Notebook界面

一本Notebook的界面大致由3个部分组成：

+ Menu bar
    有关Notebook的各种功能选项。

+ Toolbar
    攥写Notebook时使用的快捷工具栏。

+ Code cell
    工作区，我们将在这里写Note。
    
我们重点来看看Code cell。

它有4种类型：

1. Code cells 
    代码区块，我们写代码的地方。输入代码，输出运行结果。

2. Markdown cells 
    文本区块，支持markdown写作，代码高亮，任意HTML代码插入，LaTex语法。输入为之前提到的各类标记语言，输出为渲染后的富文本。

3. Raw cells
    原始区块，Jupyter不会对这个区域的输入做任何处理，输入即输出。

4. Heading cells
    用标题为文档注释结构，Jupyter现在已经不再使用了。直接在markdown cell中使用`#`字符进行结构处理就可以。

Code cell的快捷键操作
+ `Shift-Enter`: 执行代码并跳转到下一个区块
    执行当前区块的代码，返还结果并跳到下一个区块。如果当前区块已经是最后一个了，则创建一个新区块。这个操作等同于Menu bar中的Cell | Run操作。

2. `Ctrl-Enter`: 执行代码并保持原状
    执行当前区块的代码，返还结果。但代码内的鼠标指针位置不会变动，执行结束进入Edit mode后的指针位置和运行前一致。这样方便我们进行一些实验性的快速代码修改。

3. `Alt-Enter`: 执行代码并插入一个区块
    执行当前区块的代码，返还结果。在当前区块和下一个区块间创建一个新区块。这个操作等同于执行`Shift-Enter`, `Ctrl-m a`（在当前区块之上创建一个新区块）

4. `Esc` and `Enter`: Command mode与Edit mode切换
    接下来就会讲。
    
## 编辑模式

Jupyter有两种编辑模式（不禁让我想到了Vim^^^^^^................）：

+ Edit mode
    当区块(cell)边框变成绿色时，说明我们进入了Edit mode。此时我们可以正常输入各类文本代码。

+ Command mode
    当区块边框为灰色时，我们就进入了Command mode。这意味着我们可以在整体上对不同的区块进行各类编辑（调整位置，增加与删除等等），并且还可以使用各式快捷键。
    
模式切换其实蛮方便的，`Esc`进入Command mode，选中某个区块后`Enter`进入Edit mode。

Command mode下具体的一些常用快捷键（快捷键还蛮多，可以在Notebook中Menu bar  Help | Keyboard Shortcuts里查询）：

1. Basic navigation: enter, shift-enter, up/k, down/j
2. Saving the notebook: s
3. Change Cell types: y, m, 1-6, t
4. Cell creation: a, b
5. Cell editing: x, c, v, d, z
6. Kernel operations: i, 0
7. Cell deleting: dd

## 代码补全与查询

Jupyter支持`tab`键代码自动补全，不过我自己测试下来还是比较2的，有总比没有好吧是这个道理……

如果想查询某些函数的具体帮助信息，可以使用`?`关键字。

``` python
import numpy as np

np.rank?
```
执行代码后Jupyter会弹出一个内置网页，显示这个函数的具体信息。

## 区块魔法(Cell Magic)

嗯，Magic，一听就很流弊的样子。这指的是一些Jupyter预置的类命令行风格函数，可以对Notebook某些功能进行修改。它有两种类型：

+ line-magic

+ cell-magic

比如切换Matplotlib的GUI，在代码区块中输入这行line-magic：

``` python
%matplotlib inline
# 将在浏览器中直接渲染图片
```

想了解更多神秘的木星祖传魔法，可以在[Magic functions](http://ipython.org/ipython-doc/dev/interactive/tutorial.html#magics-explained)浏览。

## 工作流

官方文档的[某段话](http://jupyter-notebook.readthedocs.io/en/latest/notebook.html#basic-workflow)简明扼要地讲了讲Jupyter工作流，我就懒得翻译了。