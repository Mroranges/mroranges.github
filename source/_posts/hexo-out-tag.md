---
title: butterfly内置标签外挂语法
abbrlink: 23825
date: 2021-10-07 19:24:30
tags: 
    - butterfly
categories:
    - 学习记录
aside: false
---

## Butterfly标签外挂

## 分页标签
使用注释来给标签分页，若要在标签中插入和标签有关的内容，需要转义
{% tabs '分页标签' %}
<!-- tab 语法 -->
{\% tabs '标签名' \%}
<\!-- tab 语法 -->
**tab 名字為第一個 Tab**
<\!-- endtab -->
<\!-- tab @fab fa-apple-pay -->
**只有图标，沒有Tab 名字**
<\!-- endtab -->
<\!-- tab 炸弹@fas fa-bomb -->
**名字+icon**
<\!-- endtab -->
{\% endtabs \%}
<!-- endtab -->
<!-- tab @fab fa-apple-pay -->
**只有图标,沒有Tab 名字**
<!-- endtab -->
<!-- tab 官方文档 -->
<a href="https:\\butterfly.js.org\posts\4aa8abbe\#Tabs">官方文档</a>
<!-- endtab -->
{% endtabs %}


## note引用
{% tabs '分页标签' %}
<!-- tab 效果 -->
{% note simple %}
默认 提示块标签
{% endnote %}
{% note default simple %}
default 提示块标签
{% endnote %}
{% note primary simple %}
primary 提示块标签
{% endnote %}
{% note success simple %}
success 提示块标签
{% endnote %}
{% note info simple %}
info 提示块标签
{% endnote %}
{% note warning simple %}
warning 提示块标签
{% endnote %}
{% note danger simple %}
danger 提示块标签
{% endnote %}
<!-- endtab -->
<!-- tab 代码 -->
{\% note simple \%}
默认 提示块标签
{\% endnote \%}
{\% note default simple \%}
default 提示块标签
{\% endnote %}
{\% note primary simple \%}
primary 提示块标签
{\% endnote \%}
{\% note success simple \%}
success 提示块标签
{\% endnote \%}
{\% note info simple \%}
info 提示块标签
{\% endnote \%}
{\% note warning simple \%}
warning 提示块标签
{\% endnote \%}
{\% note danger simple \%}
danger 提示块标签
{\% endnote \%}
<!-- endtab -->
{% endtabs %}

### 按钮
{% tabs 'button' %}
<!-- tab 效果 -->
{% btn 'https://butterfly.js.org/',Butterfly %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right %}
{% btn 'https://butterfly.js.org/',Butterfly,,outline %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,larger %}
<!-- endtab -->
<!-- tab 代码 -->
{\% btn 'https://butterfly.js.org/',Butterfly \%}
{\% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right \%}
{\% btn 'https://butterfly.js.org/',Butterfly,,outline \%}
{\% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline \%}
{\% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,larger \%}
<!-- endtab -->
{% endtabs %}

``` markdown
{% btn [url],[text],[icon],[color] [style] [layout] [position] [size] %}

[url]         : 链接
[text]        : 按钮文字
[icon]        : [可选] 图标
[color]       : [可选] 按钮背景顔色(默认style时）
                      按钮字体和边框顔色(outline时)
                      default/blue/pink/red/purple/orange/green
[style]       : [可选] 按钮样式 默认实心
                      outline/留空
[layout]      : [可选] 按钮佈局 默认为line
                      block/留空
[position]    : [可选] 按钮位置 前提是设置了layout为block 默认为左边
                      center/right/留空
[size]        : [可选] 按钮大小
                      larger/留空
```