---
title: butterfly标签
abbrlink: 23825
date: 2021-10-07 19:24:30
description: 'hexo-butterfly-tag-plugins-plus安装及butterfly内置标签部分使用方法及说明'
tags: 
    - butterfly
categories:
    - 学习记录
aside: true
sticky: 1
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

## 时间轴 timeline
{% tabs '时间轴 timeline' %}
<!-- tab 效果 -->
{% timeline %}

{% timenode 2020-07-24 %}

天气不错，适合出去约妹

{% endtimenode %}

{% timenode 2020-05-15 %}

下雨了，适合在房间

{% endtimenode %}

{% timenode 2020-04-20 %}

有空一起拉屎

{% endtimenode %}

{% endtimeline %}
<!-- endtab -->
<!-- tab 标签语法 -->
```markdown
{% timeline 时间线标题（可选） %}
{% timenode 时间节点（标题） %}
正文内容
{% endtimenode %}
{% timenode 时间节点（标题） %}
正文内容
{% endtimenode %}
{% endtimeline %}
```
<!-- endtab -->
<!-- tab 源码 -->
```markdownd
{% timeline %}

{% timenode 2020-07-24 %}

天气不错，适合出去约妹

{% endtimenode %}

{% timenode 2020-05-15 %}

下雨了，适合在房间

{% endtimenode %}

{% timenode 2020-04-20 %}

有空一起拉屎

{% endtimenode %}

{% endtimeline %}
```
<!-- endtab -->
{% endtabs %}

## 按钮 btns
{% tabs '按钮 btns' %}
<!-- tab 效果 -->
1. 一组含有头像的链接：
{% btns circle grid5 %}
{% cell GitHub, https://github.com/, https://cdn.jsdelivr.net/gh/cpddo/p_img@450ea647ca67bd386416a689f3eb1bc6a508b3b9/2021/01/23/f7ac7b26db76ada1704f6af09bedacbe.webp %}
{% cell 哔哩哔哩, https://www.bilibili.com/, https://cdn.jsdelivr.net/gh/cpddo/p_img@e642ee265c8ae2bbd0994716aa12b3adbe07f2c4/2021/01/23/2ceca69a212d3b9988bbd2c41edc636c.webp %}
{% cell Pixiv, https://www.pixiv.net/, https://cdn.jsdelivr.net/gh/cpddo/p_img@5c4fc20944c706aa452c31d1bddbdcc672e8c6ab/2021/01/23/7658d06315d32bcf0c954b3d8e8879e0.webp %}
{% cell YouTube, https://www.youtube.com/, https://cdn.jsdelivr.net/gh/cpddo/p_img@ff4781678ea6227f5824e3c8bfd5cc27441db4da/2021/01/23/f4e292c780275465c9150eb3cb0785a4.webp %}
{% cell 今日热榜, https://tophub.today/, https://cdn.jsdelivr.net/gh/cpddo/p_img@11fff6ed270722d709eb0ac88ce47f468c21d2ba/2021/01/23/cd22cd9d34d7d7bd58114d7d7a195822.webp %}
{% endbtns %}
2. 或者含有图标的按钮：
{% btns rounded grid5 %}
{% cell 下载源码, /, fas fa-download %}
{% cell 查看文档, /, fas fa-book-open %}
{% endbtns %}
3. 圆形图标 + 标题 + 描述 + 图片 + 网格5列 + 居中
{% btns circle center grid5 %}
<a href='https://apps.apple.com/cn/app/heart-mate-pro-hrm-utility/id1463348922?ls=1'>
  <i class='fab fa-apple'></i>
  <b>心率管家</b>
  {% p red, 专业版 %}
  <img src='https://cdn.jsdelivr.net/gh/xaoxuu/cdn-assets/qrcode/heartmate_pro.png'>
</a>
<a href='https://apps.apple.com/cn/app/heart-mate-lite-hrm-utility/id1475747930?ls=1'>
  <i class='fab fa-apple'></i>
  <b>心率管家</b>
  {% p green, 免费版 %}
  <img src='https://cdn.jsdelivr.net/gh/xaoxuu/cdn-assets/qrcode/heartmate_lite.png'>
</a>
{% endbtns %}
<!-- endtab -->
<!-- tab 标签语法 -->
```
{% btns 样式参数 %}
{% cell 标题, 链接, 图片或者图标 %}
{% cell 标题, 链接, 图片或者图标 %}
{% endbtns %}
```
<!-- endtab -->
<!-- tab 参数配置 -->

1. 圆角样式：rounded, circle
2. 增加文字样式：可以在容器内增加 <b>标题</b> 和 <p>描述文字</p>
3. 布局方式：默认为自动宽度，适合视野内只有一两个的情况。

| 参数	| 含义 |
| ----- | :-------: |
| wide |	宽一点的按钮 |
| fill |	填充布局，自动铺满至少一行，多了会换行 |
| center |	居中，按钮之间是固定间距 |
| around |	居中分散 |
| grid2 |	等宽最多2列，屏幕变窄会适当减少列数 |
| grid3 |	等宽最多3列，屏幕变窄会适当减少列数 |
| grid4  |	等宽最多4列，屏幕变窄会适当减少列数 |
| grid5 |	等宽最多5列，屏幕变窄会适当减少列数 |
<!-- endtab -->
<!-- tab 源码 -->
1. 一组含有头像的链接：
```markdown
{% btns circle grid5 %}
{% cell GitHub, https://github.com/, https://cdn.jsdelivr.net/gh/cpddo/p_img@450ea647ca67bd386416a689f3eb1bc6a508b3b9/2021/01/23/f7ac7b26db76ada1704f6af09bedacbe.webp %}
{% cell 哔哩哔哩, https://www.bilibili.com/, https://cdn.jsdelivr.net/gh/cpddo/p_img@e642ee265c8ae2bbd0994716aa12b3adbe07f2c4/2021/01/23/2ceca69a212d3b9988bbd2c41edc636c.webp %}
{% cell Pixiv, https://www.pixiv.net/, https://cdn.jsdelivr.net/gh/cpddo/p_img@5c4fc20944c706aa452c31d1bddbdcc672e8c6ab/2021/01/23/7658d06315d32bcf0c954b3d8e8879e0.webp %}
{% cell YouTube, https://www.youtube.com/, https://cdn.jsdelivr.net/gh/cpddo/p_img@ff4781678ea6227f5824e3c8bfd5cc27441db4da/2021/01/23/f4e292c780275465c9150eb3cb0785a4.webp %}
{% cell 今日热榜, https://tophub.today/, https://cdn.jsdelivr.net/gh/cpddo/p_img@11fff6ed270722d709eb0ac88ce47f468c21d2ba/2021/01/23/cd22cd9d34d7d7bd58114d7d7a195822.webp %}
{% endbtns %}
```
2. 或者含有图标的按钮：
```markdown
{% btns rounded grid5 %}
{% cell 下载源码, /, fas fa-download %}
{% cell 查看文档, /, fas fa-book-open %}
{% endbtns %}
```
3. 圆形图标 + 标题 + 描述 + 图片 + 网格5列 + 居中
```markdown
{% btns circle center grid5 %}
<a href='https://apps.apple.com/cn/app/heart-mate-pro-hrm-utility/id1463348922?ls=1'>
  <i class='fab fa-apple'></i>
  <b>心率管家</b>
  {% p red, 专业版 %}
  <img src='https://cdn.jsdelivr.net/gh/xaoxuu/cdn-assets/qrcode/heartmate_pro.png'>
</a>
<a href='https://apps.apple.com/cn/app/heart-mate-lite-hrm-utility/id1475747930?ls=1'>
  <i class='fab fa-apple'></i>
  <b>心率管家</b>
  {% p green, 免费版 %}
  <img src='https://cdn.jsdelivr.net/gh/xaoxuu/cdn-assets/qrcode/heartmate_lite.png'>
</a>
{% endbtns %}
```
<!-- endtab -->

{% endtabs %}

## 行内图片 inlineimage
{% tabs '行内图片 inlineimage' %}
<!-- tab 效果 -->
这是 {% inlineimage https://cdn.jsdelivr.net/gh/volantis-x/cdn-emoji/aru-l/0000.gif %} 一段话。

这又是 {% inlineimage https://cdn.jsdelivr.net/gh/volantis-x/cdn-emoji/aru-l/5150.gif, height=40px %} 一段话。
<!-- endtab -->
<!-- tab 标签语法 -->
```markdown
{% inlineimage 图片链接, height=高度（可选） %}
```
<!-- endtab -->
<!-- tab 参数 -->
高度：height=20px
<!-- endtab -->
<!-- tab 源码 -->
```markdownd
这是 {% inlineimage https://cdn.jsdelivr.net/gh/volantis-x/cdn-emoji/aru-l/0000.gif %} 一段话。

这又是 {% inlineimage https://cdn.jsdelivr.net/gh/volantis-x/cdn-emoji/aru-l/5150.gif, height=40px %} 一段话。
```
<!-- endtab -->
{% endtabs %}

## 单张图片 image
{% tabs '单张图片 image' %}
<!-- tab 效果 -->
1. 添加描述
{% image https://cdn.jsdelivr.net/gh/volantis-x/cdn-wallpaper-minimalist/2020/025.jpg, alt=愿你成为自己的太阳，无需凭借谁的光芒。 %}
2. 指定宽度：
{% image https://cdn.jsdelivr.net/gh/volantis-x/cdn-wallpaper-minimalist/2020/025.jpg, width=400px %}
3. 指定宽度并添加描述：
{% image https://cdn.jsdelivr.net/gh/volantis-x/cdn-wallpaper-minimalist/2020/025.jpg, width=400px, alt=愿你成为自己的太阳，无需凭借谁的光芒。 %}
4. 设置占位背景色：
{% image https://cdn.jsdelivr.net/gh/volantis-x/cdn-wallpaper-minimalist/2020/025.jpg, width=400px, bg=#1D0C04, alt=优化不同宽度浏览的观感 %}
<!-- endtab -->
<!-- tab 标签语法 -->
```markdown
{% image 链接, width=宽度（可选）, height=高度（可选）, alt=描述（可选）, bg=占位颜色（可选） %}
```
1. 图片宽度高度：width=300px, height=32px
2. 图片描述：alt=图片描述（butterfly需要在主题配置文件中开启图片描述）
3. 占位背景色：bg=#f2f2f2
<!-- endtab -->
<!-- tab 源码 -->
1. 添加描述
```markdown
{% image https://cdn.jsdelivr.net/gh/volantis-x/cdn-wallpaper-minimalist/2020/025.jpg, alt=愿你成为自己的太阳，无需凭借谁的光芒。 %}
```
2. 指定宽度：
```markdown
{% image https://cdn.jsdelivr.net/gh/volantis-x/cdn-wallpaper-minimalist/2020/025.jpg, width=400px %}
```
3. 指定宽度并添加描述：
```markdown
{% image https://cdn.jsdelivr.net/gh/volantis-x/cdn-wallpaper-minimalist/2020/025.jpg, width=400px, alt=愿你成为自己的太阳，无需凭借谁的光芒。 %}
```
4. 设置占位背景色：
```makrdown
{% image https://cdn.jsdelivr.net/gh/volantis-x/cdn-wallpaper-minimalist/2020/025.jpg, width=400px, bg=#1D0C04, alt=优化不同宽度浏览的观感 %}
```
<!-- endtab -->
{% endtabs %}

## 音频 audio
{% tabs '音频 audio' %}
<!-- tab 效果 -->
{% audio https://github.com/volantis-x/volantis-docs/releases/download/assets/Lumia1020.mp3 %}
<!-- endtab -->
<!-- tab 标签语法 -->
```markdown
{% audio 音频链接 %}
```
<!-- endtab -->
<!-- tab 源码 -->
```markdown
{% audio https://github.com/volantis-x/volantis-docs/releases/download/assets/Lumia1020.mp3 %}
```
<!-- endtab -->
{% endtabs %}

## 视频 video
{% tabs '视频 video' %}
<!-- tab 效果 -->
1. 100% 宽度
{% video https://1251316161.vod2.myqcloud.com/007a649dvodcq1251316161/2d10a99a5285890815076699337/jDSbeLEbAvgA.mp4 %}
2. 50% 宽度
{% videos, 2 %}
{% video https://1251316161.vod2.myqcloud.com/007a649dvodcq1251316161/c271d9f55285890808619247572/cvQ5JmaxQeIA.mp4 %}
{% video https://1251316161.vod2.myqcloud.com/007a649dvodcq1251316161/8373c2325285890808618842182/0G2tZMSgFlIA.mp4 %}
{% video https://bos.nj.bpc.baidu.com/tieba-smallvideo-transcode-crf/10517287_a019c0a4655b865403740b7b9d1f0622_0.mp4 %}
{% video https://1251316161.vod2.myqcloud.com/007a649dvodcq1251316161/62034a6a5285890805262027097/2ZZqs2WH2HUA.mp4 %}
{% endvideos %}
3. 25% 宽度
{% videos, 4 %}
{% video https://1251316161.vod2.myqcloud.com/007a649dvodcq1251316161/dbb2338d5285890805087414392/iPOPAzDcziQA.mp4 %}
{% video https://1251316161.vod2.myqcloud.com/007a649dvodcq1251316161/dbaff9015285890805087410150/hFeFC3ppTLsA.mp4 %}
{% video https://1251316161.vod2.myqcloud.com/007a649dvodcq1251316161/b6ccab4b5285890805073207494/crb6Lmf26tQA.mp4 %}
{% video https://sf1-ttcdn-tos.pstatp.com/obj/tos-cn-v-0004/aeacaeb49b1a4bf483d93356091fad60 %}
{% video https://1251316161.vod2.myqcloud.com/007a649dvodcq1251316161/3c5d29755285890805529884127/jgf48juQ7PoA.mp4 %}
{% video https://1251316161.vod2.myqcloud.com/007a649dvodcq1251316161/63f968535285890808730645862/Gg7ng1DpoJwA.mp4 %}
{% video https://1251316161.vod2.myqcloud.com/007a649dvodcq1251316161/562fa8ea5285890808730073912/cAJgQKS0gL8A.mp4 %}
{% video https://1251316161.vod2.myqcloud.com/007a649dvodcq1251316161/5d54d76e5285890808730396152/z0aYxeAto3QA.mp4 %}
{% endvideos %}
<!-- endtab -->
<!-- tab 标签语法 -->
```markdown
{% video 视频链接 %}
```
<!-- endtab -->
<!-- tab 参数配置 -->
1. 对其方向：left, center, right
2. 列数：逗号后面直接写列数，支持 1 ～ 4 列。
<!-- endtab -->
<!-- tab 源码 -->
1. 100% 宽度
```markdown
{% video https://1251316161.vod2.myqcloud.com/007a649dvodcq1251316161/2d10a99a5285890815076699337/jDSbeLEbAvgA.mp4 %}
```
2. 50% 宽度
```markdown
{% videos, 2 %}
{% video https://1251316161.vod2.myqcloud.com/007a649dvodcq1251316161/c271d9f55285890808619247572/cvQ5JmaxQeIA.mp4 %}
{% video https://1251316161.vod2.myqcloud.com/007a649dvodcq1251316161/8373c2325285890808618842182/0G2tZMSgFlIA.mp4 %}
{% video https://bos.nj.bpc.baidu.com/tieba-smallvideo-transcode-crf/10517287_a019c0a4655b865403740b7b9d1f0622_0.mp4 %}
{% video https://1251316161.vod2.myqcloud.com/007a649dvodcq1251316161/62034a6a5285890805262027097/2ZZqs2WH2HUA.mp4 %}
{% endvideos %}
```
3. 25% 宽度
```markdown
{% videos, 4 %}
{% video https://1251316161.vod2.myqcloud.com/007a649dvodcq1251316161/dbb2338d5285890805087414392/iPOPAzDcziQA.mp4 %}
{% video https://1251316161.vod2.myqcloud.com/007a649dvodcq1251316161/dbaff9015285890805087410150/hFeFC3ppTLsA.mp4 %}
{% video https://1251316161.vod2.myqcloud.com/007a649dvodcq1251316161/b6ccab4b5285890805073207494/crb6Lmf26tQA.mp4 %}
{% video https://sf1-ttcdn-tos.pstatp.com/obj/tos-cn-v-0004/aeacaeb49b1a4bf483d93356091fad60 %}
{% video https://1251316161.vod2.myqcloud.com/007a649dvodcq1251316161/3c5d29755285890805529884127/jgf48juQ7PoA.mp4 %}
{% video https://1251316161.vod2.myqcloud.com/007a649dvodcq1251316161/63f968535285890808730645862/Gg7ng1DpoJwA.mp4 %}
{% video https://1251316161.vod2.myqcloud.com/007a649dvodcq1251316161/562fa8ea5285890808730073912/cAJgQKS0gL8A.mp4 %}
{% video https://1251316161.vod2.myqcloud.com/007a649dvodcq1251316161/5d54d76e5285890808730396152/z0aYxeAto3QA.mp4 %}
{% endvideos %}
```
<!-- endtab -->
{% endtabs %}


## 相册 gallery
{% tabs '相册 gallery' %}
<!-- tab 效果 -->
1.gallerygroup 相册图库
<div class="gallery-group-main">
{% galleryGroup '壁纸' '收藏的一些壁纸' '/Gallery/wallpaper' https://i.loli.net/2019/11/10/T7Mu8Aod3egmC4Q.png %}
{% galleryGroup '漫威' '关于漫威的图片' '/Gallery/marvel' https://i.loli.net/2019/12/25/8t97aVlp4hgyBGu.jpg %}
{% galleryGroup 'OH MY GIRL' '关于OH MY GIRL的图片' '/Gallery/ohmygirl' https://i.loli.net/2019/12/25/hOqbQ3BIwa6KWpo.jpg %}
</div>


2.gallery 相册 
{% gallery %}
![](https://i.loli.net/2019/12/25/Fze9jchtnyJXMHN.jpg)
![](https://i.loli.net/2019/12/25/ryLVePaqkYm4TEK.jpg)
![](https://i.loli.net/2019/12/25/gEy5Zc1Ai6VuO4N.jpg)
![](https://i.loli.net/2019/12/25/d6QHbytlSYO4FBG.jpg)
![](https://i.loli.net/2019/12/25/6nepIJ1xTgufatZ.jpg)
![](https://i.loli.net/2019/12/25/E7Jvr4eIPwUNmzq.jpg)
![](https://i.loli.net/2019/12/25/mh19anwBSWIkGlH.jpg)
![](https://i.loli.net/2019/12/25/2tu9JC8ewpBFagv.jpg)
{% endgallery %}

<!-- endtab -->
<!-- tab 标签语法 -->
1. gallerygroup 相册图库
```markdown
<div class="gallery-group-main">
{% galleryGroup name description link img-url %}
{% galleryGroup name description link img-url %}
{% galleryGroup name description link img-url %}
</div>
```

2. gallery 相册
{% gallery %}
markdown 圖片格式
{% endgallery %}

<!-- endtab -->
<!-- tab 参数 -->
- gallerygroup 相册图库
| 参数名 	| 释义 | 
|------|:-------:|
| name | 	图库名字 | 
| description | 	图库描述 | 
| link | 	链接到对应相册的地址 | 
| img-url | 	图库封面 | 


- gallery 相册
区别于旧版的Gallery相册,新的Gallery相册会自动根据图片长度进行排版，书写也更加方便，与markdown格式一样。可根据需要插入到相应的md。无需再自己配置长宽。建议在粘贴时故意使用长短、大小、横竖不一的图片，会有更好的效果。（尺寸完全相同的图片只会平铺输出，效果很糟糕）

<!-- endtab -->
{% endtabs %}