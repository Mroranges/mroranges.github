---
title: markdown语法
date: 2021-10-01 20:07:39
description: markdown语法
aside: true
tags:
  - markdown
categories:
  - markdown
---



## 标题

{% tabs '标题' %}
<!-- tab 样式预览 -->
{% note info %}最多支持六级标题{%endnote%}

# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题
<!-- endtab -->
<!-- tab 示例源码 -->
```markdown
# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题
```
<!-- endtab -->
{% endtabs %}



## 任务列表

{% tabs '任务列表' %}
<!-- tab 样式预览 -->
- [ ] 任务一 未做任务
- [x] 任务二 已做任务 
<!-- endtab -->
<!-- tab 示例源码 -->
```markdown
- [ ] 任务一 未做任务
- [x] 任务二 已做任务
```
<!-- endtab -->
{% endtabs %}



## 缩进、换行、空行、对齐方式
{% tabs '缩进、换行、空行、对齐方式' %}
<!-- tab 缩进 -->
【1】 &emsp;或&#8195; //全角
【2】 &ensp;或&#8194; //半角
【3】 &nbsp;或&#160;  //半角之半角

示例源码
```markdown
【1】 &emsp;或&#8195; //全角
【2】 &ensp;或&#8194; //半角
【3】 &nbsp;或&#160;  //半角之半角
```
<!-- endtab -->
<!-- tab 换行 -->
由于markdown编辑器的不同,可能在一行字后面，直接换行回车，也能实现换行，但是在Visual Studio Code上，想要换行必须得在一行字后面空两个格子才行。
<!-- endtab -->
<!-- tab 空行 -->
在编辑的时候有多少个空行(只要这一行只有回车或者space没有其他的字符就算空行)，在渲染之后，只隔着一行。
<!-- endtab -->
<!-- tab 对齐方式 -->

<center>行中心对齐</center>
<p align="left">行左对齐</p>
<p align="right">行右对齐</p>

示例源码
```markdown
<center>行中心对齐</center>
<p align="left">行左对齐</p>
<p align="right">行右对齐</p>
```
<!-- endtab -->
{% endtabs %}

## 斜体、粗体、删除线、下划线、背景高亮
{% tabs '斜体、粗体、删除线、下划线、背景高亮' %}
<!-- tab 样式预览 -->
*斜体*或_斜体_
**粗体**
***加粗斜体***
~~删除线~~
++下划线++
<!-- endtab -->
<!-- tab 示例源码 -->
```markdown
*斜体*或_斜体_
**粗体**
***加粗斜体***
~~删除线~~
++下划线++
```
<!-- endtab -->
{% endtabs %}

## 超链接、页内链接、自动链接、注脚
{% tabs '超链接、页内链接、自动链接、注脚' %}
<!-- tab 超链接 -->

* 行内式超链接
[butterfly 标签](https://mroranges.github.io/posts/23825/ "test")
```markdown
示例源码:
[butterfly 标签](https://mroranges.github.io/posts/23825/ "test")
markdown语法:
[显示名称](链接 title)
[]里写链接文字，()里写链接地址, ()中的""中可以为链接指定title属性，title属性可加可不加。title属性的效果是鼠标悬停在链接上会出现指定的 title文字，链接地址与title前有一个空格。
```

* 参考式超链接
	参考式超链接一般用在学术论文上面，或者另一种情况，如果某一个链接在文章中多处使用，那么使用引用 的方式创建链接将非常好，它可以让你对链接进行统一的管理。

	{% note warning simple %}
	
	hexo不支持此种语法格式！
	
	{% endnote %}
	
	* 语法
	```markdown
	我经常去的几个网站[Google][1]、[Baidu][2]。
	
	[1]:http://www.google.com
	[2]:http://www.baidu.com
	```
	
* 注脚

  语法：
  
  ```markdown
    使用 Markdown[^1]可以效率的书写文档, 直接转换成 HTML[^2]。
    [^1]:Markdown是一种纯文本标记语言
    [^2]:HyperText Markup Language 超文本标记语言
  ```
  

<!-- endtab -->
{% endtabs %}



## 无序列表、有序列表、定义型列表



## 表格

```markdown
| 表头             |                             表头                             |
| ---------------- | :----------------------------------------------------------: |
| title            |                       【必需】页面标题                       |
```

