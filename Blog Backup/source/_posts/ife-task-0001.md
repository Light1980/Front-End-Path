---
title: ife task-0001 总结
tags:
  - CSS
  - HTML
  - JavaScript
categories:
  - Front-end
date: 2015-04-23 23:42:40
---

说实话，从没有写过什么技术性的文章，今天也算是出生以来开天辟地第一遭了（笑）~但我这么新嫩的程序员，又哪有什么技术干货可供人一观呢？目前自己所做的，不过是在温暖与安全的内海港湾中汲汲吸收着前人知识，宛如两三岁岁牙牙学语的孩童，还没有说明白话的能力。所以，在这篇总结里，我就不打算写甚么与技术细节相关的东西了，只稍许谈谈自己这些天写代码时得来的浅薄心得吧。

<!-- more -->

## 布局

对于一个块元素A，如何兼顾它在整体页面上的布局效果和内部的布局效果？我个人摸索出来的办法是，为这个块元素A再添加一个紧贴其边框的块元素B，让其成为B的子元素。如此一来，我们可以将整体布局与内部布局的工作<span style="color: #008000;">**分离**</span>开来。对块元素A进行操作，让其专门对自身内部布局负责；对块元素B进行操作，让其专门对A在整体上的布局位置负责；如此一来，我们的工作可能就会省心不少。

但这样做的危险或在于，在块元素A内部又嵌套多种元素时，若我们对这些元素继续采取分离内外布局的做法，可能就会大大增加整个嵌套规则的复杂度，最终把自己给绕晕了头。对此，我们可能的解决策略有：
> **1.**在命名id或者class时，尽量要选择能明确表达其功能的词语。> 
> 
> **2.**在没有必要的时候，不随便使用这样的布局方法。> 
> 
> **3.**待补充……
尽管有增加嵌套层数，导致复杂度增加的危险，它对于目前的我来说依然还是一种很有用的方法；特别是在我主要使用position的定位方法进行布局的时候。参考[demo](http://xuanchao1980.com/task0001/task0001-final/about.html)

&nbsp;

##  双飞翼改

在学习布局的时候，[双飞翼模型](http://www.imooc.com/wenda/detail/254035)的布局很有意思，但读起来总觉得很复杂。我根据自己的理解，又参考了DIYgod的[代码](https://www.anotherhome.net/1969)，实现了一个类似的模型，在效果上几乎等同于双飞翼（因为我自己确实还没发现区别），但代码量上简化了不少（再次感慨，负外边距和浮动真是神奇啊）；如果有兴趣，可以移步[demo](http://xuanchao1980.com/task0001/双飞翼改.html)。

&nbsp;

## 结语

前端开发，很有趣也很辛苦的行当，如果你对WEB或者可视化感兴趣，又或是想要在更互联网的未来（谁能知道下一个十年，Web将发展到怎样境地呢？）中安然过活，都不妨来接触一下它。明天开始进入JavaSript的学习，Html与CSS的复习进阶也要展开，而期末考却正好挤在五月初，挑战在前，祝自己前路顺利。对了对了，在最后，我再次再次向百度，向EFE团队表达感激之情！感谢！

附带：百度Web前端技术学院项目[地址](https://github.com/Light1980/ife)

&nbsp;

Light1980 —— For a better me.