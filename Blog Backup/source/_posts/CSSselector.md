---
title: CSS选择器优先级基础
date: 2015-1-12 22:28:22
categories:
    - Front-end
tags:
    - CSS
---

这篇文章在去年学网易的前端课时就在酝酿了。现在终于写完，和初稿比较，已经是面目全非。

<!-- more -->

## 新的征途

关于选择器优先级，网上说法很多，但都讲得过于简单或过于绕口。所以我觉得还是值得总结一二的。

我目前的理解如下：

+ 元素内容将优先匹配所属元素的CSS定义。如果没有，则向上匹配父元素的CSS定义。
+ 如果遇到所属元素样式定义冲突，便按照选择器优先级进行排序，匹配对应样式。
+ 当优先级相同时，则后出现的样式生效。

## 第一点

关于第一点，打开[JSbin](http://jsbin.com/)，写个简单的HTML代码：
``` css
<p class = "a"><span id = "b"><em>xixi</em></span></p>
```

设置下CSS样式：
``` css
    .a {
    color:blue;}
    
    #b {
    color:blue;}
    
    em {
    color:red;}
```
运行看看效果。我们会发现xixi其实是红色，无论是使用优先级较高的类选择器或ID选择器，都不会对em元素内的文本生效。这因为文本会优先匹配自己所属em元素的相应样式声明。只有当em元素没有对应的样式声明时，CSS才会向上查找父元素声明。如果一直都木有找到，它会使用body元素默认的样式。

所以在此时，无论给div父元素中的文本样式如何提高优先级，它都不会对em子元素生效。

## 第二条

接着关于第二点，CSS选择器优先级排序，一张表格解决：

<table><caption>From Udemy Course: Mastering CSS</caption><tbody><tr><th>CSS Slectors</th><th>Points</th></tr><tr><td>!important</td><td>10000</td></tr><tr><td>Inline Style</td><td>1000</td></tr><tr><td>ID</td><td>100</td></tr><tr><td>Class/Pseudo Class</td><td>10</td></tr><tr><td>Elements</td><td>1</td></tr><tr><td>Global(*)</td><td>0</td></tr></tbody></table>

计算多个选择器的优先级时，直接加起来就可以了。一般来说，我们尽量选择Class选择器控制样式，避免使用比它优先级更高的选择器。这样做让我们能更容易地修改样式，也增强了样式的复用性。

## 第三步

最后一点就很简单了，优先级相同时看选择器在样式表中的位置，靠后的生效。

<hr>

<a href="http://creativecommons.org/licenses/by-sa/4.0/" rel="license"><img style="border-width: 0;" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" alt="Creative Commons License" /></a><br />
This work is licensed under a <a href="http://creativecommons.org/licenses/by-sa/4.0/" rel="license">Creative Commons Attribution-ShareAlike 4.0 International License</a>.