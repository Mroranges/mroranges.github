---
title: butterfly标签
abbrlink: 23825
date: 2021-10-07 19:24:30
description: 'butterfly内置标签及hexo-butterfly-tag-plugins-plus'
tags: 
    - butterfly
categories:
    - 学习记录
aside: false
---

更多信息请查看官网介绍: [butterfly Tabs](https:\\butterfly.js.org\posts\4aa8abbe\#Tabs)


{% note info simple %}
以下均在"node": v12.22.6,"hexo-theme-butterfly": 3.8.4,"hexo": "^5.0.0","hexo-butterfly-tag-plugins-plus": "^1.0.3"环境测试
{% endnote %}

## 标签插件安装
### 安装
在根目录下打开终端，运行以下命令
```bash
npm install hexo-butterfly-tag-plugins-plus --save
```
### _config.yml 文件配置
添加配置信息，以下为写法示例
在站点配置文件_config.yml 或者主题配置文件_config.butterfly.yml 中添加
```
# tag-plugins-plus
# see https://akilar.top/posts/615e2dec/
tag_plugins:
  enable: true # 开关
  priority: 5 #过滤器优先权
  issues: false #issues标签依赖注入开关
  CDN:
    anima: https://cdn.jsdelivr.net/gh/l-lin/font-awesome-animation/dist/font-awesome-animation.min.css #动画标签anima的依赖
    jquery: https://cdn.jsdelivr.net/npm/jquery@latest/dist/jquery.min.js #issues标签依赖
    issues: https://cdn.jsdelivr.net/npm/hexo-theme-volantis@latest/source/js/issues.min.js #issues标签依赖
    iconfont: //at.alicdn.com/t/font_2032782_8d5kxvn09md.js #参看https://akilar.top/posts/d2ebecef/
    carousel: https://cdn.jsdelivr.net/npm/hexo-butterfly-tag-plugins-plus@latest/lib/carousel-touch.min.js
```

### 配置参数解释
| 字段             | 备选值 / 类型 |                            解释                             |
| ---------------- | :------------:| :----------------------------------------------------------: |
|enable	| true/false	| 【必选】控制开关   |
|priority	| number	| 【可选】过滤器优先级，数值越小，执行越早，默认为 10，选填   |
|issues	| true/false	| 【可选】issues 标签控制开关，默认为 false   |
|CDN.anima	| URL	| 【可选】动画标签 anima 的依赖   |
|CDN.jquery	| URL	| 【可选】issues 标签依赖   |
|CDN.issues	| URL	| 【可选】issues 标签依赖   |
|CDN.iconfont	| URL	| 【可选】iconfont 标签 symbol 样式引入   |
|CDN.carousel	| URL	| 【可选】carousel 旋转相册标签鼠标拖动依赖   |


## 行内文本 span
{% tabs '行内文本 span' %}
<!-- tab 效果 -->
- 彩色文字
在一段话中方便插入各种颜色的标签，包括：{% span red, 红色 %}、{% span yellow, 黄色 %}、{% span green, 绿色 %}、{% span cyan, 青色 %}、{% span blue, 蓝色 %}、{% span gray, 灰色 %}。
- 超大号文字
文档「开始」页面中的标题部分就是超大号文字。
{% span center logo large, Volantis %}
{% span center small, A Wonderful Theme for Hexo %}
<!-- endtab -->
<!-- tab 源码 -->
```
- 彩色文字
在一段话中方便插入各种颜色的标签，包括：{% span red, 红色 %}、{% span yellow, 黄色 %}、{% span green, 绿色 %}、{% span cyan, 青色 %}、{% span blue, 蓝色 %}、{% span gray, 灰色 %}。
- 超大号文字
文档「开始」页面中的标题部分就是超大号文字。
{% span center logo large, Volantis %}
{% span center small, A Wonderful Theme for Hexo %}
```
<!-- endtab -->
<!-- tab 标签语法 -->
```
{% span 样式参数(参数以空格划分), 文本内容 %}
```
<!-- endtab -->
{% endtabs %}

## 段落文本 p
{% tabs '段落文本 p' %}
<!-- tab 效果 -->
- 彩色文字
在一段话中方便插入各种颜色的标签，包括：{% p red, 红色 %}、{% p yellow, 黄色 %}、{% p green, 绿色 %}、{% p cyan, 青色 %}、{% p blue, 蓝色 %}、{% p gray, 灰色 %}。
- 超大号文字
文档「开始」页面中的标题部分就是超大号文字。
{% p center logo large, Volantis %}
{% p center small, A Wonderful Theme for Hexo %}
<!-- endtab -->
<!-- tab 源码 -->
```
- 彩色文字
在一段话中方便插入各种颜色的标签，包括：{% p red, 红色 %}、{% p yellow, 黄色 %}、{% p green, 绿色 %}、{% p cyan, 青色 %}、{% p blue, 蓝色 %}、{% p gray, 灰色 %}。
- 超大号文字
文档「开始」页面中的标题部分就是超大号文字。
{% p center logo large, Volantis %}
{% p center small, A Wonderful Theme for Hexo %}
```
<!-- endtab -->
<!-- tab 配置参数 -->
1. 字体: logo, code
2. 颜色: red,yellow,green,cyan,blue,gray
3. 大小: small, h4, h3, h2, h1, large, huge, ultra
4. 对齐方向: left, center, right
<!-- endtab -->
<!-- tab 标签语法 -->
```
{% p 样式参数(参数以空格划分), 文本内容 %}
```
<!-- endtab -->
{% endtabs%}

## 上标标签 tip
{% tabs '上标标签 tip' %}
<!-- tab 效果 -->
{% tip %}默认情况{% endtip %}
{% tip success %}success{% endtip %}
{% tip error %}error{% endtip %}
{% tip warning %}warning{% endtip %}
{% tip bolt %}bolt{% endtip %}
{% tip ban %}ban{% endtip %}
{% tip home %}home{% endtip %}
{% tip sync %}sync{% endtip %}
{% tip cogs %}cogs{% endtip %}
{% tip key %}key{% endtip %}
{% tip bell %}bell{% endtip %}
{% tip fa-atom %}自定义font awesome图标{% endtip %}
<!-- endtab -->
<!-- tab 标签语法 -->
```markdown
{% tip [参数，可选] %}文本内容{% endtip %}
```
<!-- endtab -->
<!-- tab 配置参数 -->
1. 样式: success,error,warning,bolt,ban,home,sync,cogs,key,bell
2. 自定义图标: 支持fontawesome。
<!-- endtab -->
<!-- tab 源码 -->
```markdown
{% tip %}默认情况{% endtip %}
{% tip success %}success{% endtip %}
{% tip error %}error{% endtip %}
{% tip warning %}warning{% endtip %}
{% tip bolt %}bolt{% endtip %}
{% tip ban %}ban{% endtip %}
{% tip home %}home{% endtip %}
{% tip sync %}sync{% endtip %}
{% tip cogs %}cogs{% endtip %}
{% tip key %}key{% endtip %}
{% tip bell %}bell{% endtip %}
{% tip fa-atom %}自定义font awesome图标{% endtip %}
```
<!-- endtab -->
{% endtabs %}



## 动态标签 anima

{% tabs '动态标签 anima' %}

<!-- tab 效果 -->
*  On DOM load（当页面加载时显示动画）
{% tip warning faa-horizontal animated %}warning{% endtip %}
{% tip ban faa-flash animated %}ban{% endtip %}

* 调整动画速度
  {% tip warning faa-horizontal animated faa-fast %}warning{% endtip %}
  {% tip ban faa-flash animated faa-slow %}ban{% endtip %}

* On hover（当鼠标悬停时显示动画）
  {% tip warning faa-horizontal animated-hover %}warning{% endtip %}
  {% tip ban faa-flash animated-hover %}ban{% endtip %}

* On parent hover（当鼠标悬停在父级元素时显示动画）
  {% tip warning faa-parent animated-hover %}<p class="faa-horizontal">warning</p>{% endtip %}
  {% tip ban faa-parent animated-hover %}<p class="faa-flash">ban</p>{% endtip %}

<!-- endtab -->

<!-- tab 标签语法 -->

```markdown
{% tip [参数，可选] %}文本内容{% endtip %}
```
<!-- endtab -->

<!-- tab 参数 -->

更多详情请参看 font-awesome-animation 文档

1. 将所需的 CSS 类添加到图标（或 DOM 中的任何元素）。
2. 对于父级悬停样式，需要给目标元素添加指定 CSS 类，同时还要给目标元素的父级元素添加 CSS 类 faa-parent animated-hover。（详情见示例及示例源码）
You can regulate the speed of the animation by adding the CSS class or . faa-fastfaa-slow
3. 可以通过给目标元素添加 CSS 类 faa-fast 或 faa-slow 来控制动画快慢。


<!-- endtab -->

<!-- tab 源码 -->
```markdown
On DOM load（当页面加载时显示动画）
{% tip warning faa-horizontal animated %}warning{% endtip %}
{% tip ban faa-flash animated %}ban{% endtip %}

调整动画速度
{% tip warning faa-horizontal animated faa-fast %}warning{% endtip %}
{% tip ban faa-flash animated faa-slow %}ban{% endtip %}

On hover（当鼠标悬停时显示动画）
{% tip warning faa-horizontal animated-hover %}warning{% endtip %}
{% tip ban faa-flash animated-hover %}ban{% endtip %}

On parent hover（当鼠标悬停在父级元素时显示动画）
{% tip warning faa-parent animated-hover %}<p class="faa-horizontal">warning</p>{% endtip %}
{% tip ban faa-parent animated-hover %}<p class="faa-flash">ban</p>{% endtip %}
```
<!-- endtab -->
{% endtabs %}

## 复选列表 checkbox
{% tabs '复选列表 checkbox'  %}
<!-- tab 效果 -->
{% checkbox 纯文本测试 %}
{% checkbox checked, 支持简单的 [markdown](https://guides.github.com/features/mastering-markdown/) 语法 %}
{% checkbox red, 支持自定义颜色 %}
{% checkbox green checked, 绿色 + 默认选中 %}
{% checkbox yellow checked, 黄色 + 默认选中 %}
{% checkbox cyan checked, 青色 + 默认选中 %}
{% checkbox blue checked, 蓝色 + 默认选中 %}
{% checkbox plus green checked, 增加 %}
{% checkbox minus yellow checked, 减少 %}
{% checkbox times red checked, 叉 %}
<!-- endtab -->
<!-- tab 标签语法 -->
```markdown
{% checkbox 样式参数（可选）, 文本（支持简单md） %}
```
<!-- endtab -->
<!-- tab 参数 -->
```markdown
    颜色: red,yellow,green,cyan,blue,gray
    选中状态: checked
```
<!-- endtab -->
<!-- tab 源码 -->
```markdown
{% checkbox 纯文本测试 %}
{% checkbox checked, 支持简单的 [markdown](https://guides.github.com/features/mastering-markdown/) 语法 %}
{% checkbox red, 支持自定义颜色 %}
{% checkbox green checked, 绿色 + 默认选中 %}
{% checkbox yellow checked, 黄色 + 默认选中 %}
{% checkbox cyan checked, 青色 + 默认选中 %}
{% checkbox blue checked, 蓝色 + 默认选中 %}
{% checkbox plus green checked, 增加 %}
{% checkbox minus yellow checked, 减少 %}
{% checkbox times red checked, 叉 %}
```
<!-- endtab -->
{%  endtabs  %}

## 单选列表 radio
{% tabs '单选列表 radio'  %}
<!-- tab 效果 -->
{% radio 纯文本测试 %}
{% radio checked,支持简单的 [markdown](https://guides.github.com/features/mastering-markdown/) 语法 %}
{% radio red, 支持自定义颜色 %}
{% radio green, 绿色 %}
{% radio yellow, 黄色 %}
{% radio cyan, 青色 %}
{% radio blue, 蓝色 %}
<!-- endtab -->
<!-- tab 标签语法 -->
```markdown
{% radio 样式参数（可选）, 文本（支持简单md） %}
```
<!-- endtab -->
<!-- tab 参数 -->
1. 颜色: red,yellow,green,cyan,blue,gray
2. 选中状态: checked
<!-- endtab -->
<!-- tab 源码 -->
```markdown
{% radio 纯文本测试 %}
{% radio checked, 支持简单的 [markdown](https://guides.github.com/features/mastering-markdown/) 语法 %}
{% radio red, 支持自定义颜色 %}
{% radio green, 绿色 %}
{% radio yellow, 黄色 %}
{% radio cyan, 青色 %}
{% radio blue, 蓝色 %}
```
<!-- endtab -->
{% endtabs  %}

## 折叠框 folding
{% tabs '折叠框 folding' %}
<!-- tab 效果 -->
{% folding 查看图片测试 %}
![](https://cdn.jsdelivr.net/gh/volantis-x/cdn-wallpaper/abstract/41F215B9-261F-48B4-80B5-4E86E165259E.jpeg)
{% endfolding %}
{% folding cyan open, 查看默认打开的折叠框 %}
这是一个默认打开的折叠框。
{% endfolding %}
{% folding green, 查看代码测试 %}
假装这里有代码块（代码块没法嵌套代码块）
{% endfolding %}
{% folding yellow, 查看列表测试 %}
- haha
- hehe
{% endfolding %}
{% folding red, 查看嵌套测试 %}
{% folding blue, 查看嵌套测试2 %}
{% folding 查看嵌套测试3 %}
hahaha <span><img src='https://cdn.jsdelivr.net/gh/volantis-x/cdn-emoji/tieba/%E6%BB%91%E7%A8%BD.png' style='height:24px'></span>
{% endfolding %}
{% endfolding %}
{% endfolding %}
<!-- endtab -->
<!-- tab 标签语法 -->
```markdown
{% folding 参数（可选）, 标题 %}
![](https://cdn.jsdelivr.net/gh/volantis-x/cdn-wallpaper/abstract/41F215B9-261F-48B4-80B5-4E86E165259E.jpeg)
{% endfolding %}
```
<!-- endtab -->
<!-- tab 参数 -->
    1.颜色：blue, cyan, green, yellow, red
    2.状态：状态填写 open 代表默认打开。
<!-- endtab -->
<!-- tab 效果 -->
```markdown
{% folding 查看图片测试 %}
![](https://cdn.jsdelivr.net/gh/volantis-x/cdn-wallpaper/abstract/41F215B9-261F-48B4-80B5-4E86E165259E.jpeg)
{% endfolding %}
{% folding cyan open, 查看默认打开的折叠框 %}
这是一个默认打开的折叠框。
{% endfolding %}
{% folding green, 查看代码测试 %}
假装这里有代码块（代码块没法嵌套代码块）
{% endfolding %}
{% folding yellow, 查看列表测试 %}
- haha
- hehe
{% endfolding %}
{% folding red, 查看嵌套测试 %}
{% folding blue, 查看嵌套测试2 %}
{% folding 查看嵌套测试3 %}
hahaha <span><img src='https://cdn.jsdelivr.net/gh/volantis-x/cdn-emoji/tieba/%E6%BB%91%E7%A8%BD.png' style='height:24px'></span>
{% endfolding %}
{% endfolding %}
{% endfolding %}
```
<!-- endtab -->
{% endtabs %}


## 链接卡片 link
{% tabs '链接卡片' %}
<!-- tab 效果 -->
{% link 随缘先生的blog,https://mroranges.github.io, /img/avatar.jpg %}
<!-- endtab -->
<!-- tab 标签语法 -->
```
{% link 标题, 链接, 图片链接（可选） %}
```
<!-- endtab -->
<!-- tab 源码 -->
```
{% link 随缘先生的blog,https://mroranges.github.io, https://cdn.jsdelivr.net/gh/tzy13755126023/BLOG_SOURCE/blog_f/butterfly-tags/20201230_05_cover.jpg %}
```
<!-- endtab -->
{% endtabs %}

## 分页标签
{% tabs '分页标签' %}
<!-- tab 语法 -->
```markdown
{% tabs Unique name, [index] %}
<!-- tab [Tab caption] [@icon] -->
Any content (support inline tags too).
<!-- endtab -->
{% endtabs %}
```
<!-- endtab -->
<!-- tab 配置参数 -->
1. Unique name :
    选项卡块标签的唯一名称，不带逗号。
    将在 #id 中用作每个标签及其索引号的前缀。
    如果名称中包含空格，则对于生成 #id，所有空格将由破折号代替。
    仅当前帖子 / 页面的 URL 必须是唯一的！
2. [index]:
    活动选项卡的索引号。
    如果未指定，将选择第一个标签（1）。
    如果 index 为 - 1，则不会选择任何选项卡。
    可选参数。
3. [Tab caption]:
    当前选项卡的标题。
    如果未指定标题，则带有制表符索引后缀的唯一名称将用作制表符的标题。
    如果未指定标题，但指定了图标，则标题将为空。
    可选参数。
4. [@icon]:
    FontAwesome 图标名称（全名，看起来像 “fas fa-font”）
    可以指定带空格或不带空格；
    例如’Tab caption @icon’ 和 ‘Tab caption@icon’.
    可选参数。
    <!-- endtab -->
    <!-- tab 源码 -->
```markdown
{% tabs test1 %}
<!-- tab -->
**This is Tab 1.**
<!-- endtab -->

<!-- tab -->
**This is Tab 2.**
<!-- endtab -->

<!-- tab -->
**This is Tab 3.**
<!-- endtab -->
{% endtabs %}
```
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
<!-- tab 源码 -->
```
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
```
<!-- endtab -->
{% endtabs %}



## 按钮
{% tabs '按钮' %}
<!-- tab 效果 -->
{% btn 'https://butterfly.js.org/',Butterfly %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right %}
{% btn 'https://butterfly.js.org/',Butterfly,,outline %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,larger %}
<!-- endtab -->
<!-- tab 代码 -->
```
{% btn 'https://butterfly.js.org/',Butterfly %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right %}
{% btn 'https://butterfly.js.org/',Butterfly,,outline \%}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,larger %}
```
<!-- endtab -->
<!-- tab 语法 -->
``` butterfly-tabs
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
<!-- endtab -->
{% endtabs %}
