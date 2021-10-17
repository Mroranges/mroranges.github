---
title: hexo使用及遇到的问题
date: 2021-10-01 16:01:08
description: 只显示description
tags:
  - hexo
categories:
  - hexo
toc: true
abbrlink: 44095
---


##  Front-matter
> Front-matter 用于指定个别文件的变量，是文件最上方以 `---` 分隔的区域

### 部分参数一览

| 字段             |                             解释                             |
| ---------------- | :----------------------------------------------------------: |
| title            |                       【必需】页面标题                       |
| date             |                     【必需】页面创建日期                     |
| type             |         【必需】标签、分类和友情链接三个页面需要配置         |
| updated          |                     【可选】页面更新日期                     |
| description      |                       【可选】页面描述                       |
| keywords         |                      【可选】页面关键字                      |
| comments         |             【可选】显示页面评论模块(默认 true)              |
| top_img          |                     【可选】页面顶部图片                     |
| mathjax          | 【可选】显示mathjax(当设置mathjax的per_page: false时，才需要配置，默认 false) |
| katex            | 【可选】显示katex(当设置katex的per_page: false时，才需要配置，默认 false) |
| aside            |                【可选】显示侧边栏 (默认 true)                |
| aplayer          | 【可选】在需要的页面加载aplayer的js和css,请参考文章下面的音乐 配置 |
| highlight_shrink | 【可选】配置代码框是否展开(true/false)(默认为设置中highlight_shrink的配置) --> |
| toc              |               【可选】文章目录           |


## hexo游游戏库页面插件（转至<a href= "https://butterfly.hclonely.com/posts/672d4d3b/">HCLonely</a>）
### 注意
{% note warning simple %}
注意，本插件会和hexo s命令冲突，请使用hexo se或hexo server代替hexo s命令！
{% endnote %}
### 安装
```bash
$ npm install hexo-steam-games --save
```
### 更新
```bash
$ npm install hexo-steam-games --update --save
```
### 配置
将下面的配置加入到根目录的_config.yml文件中
```yml
steam:
  enable: true #是否启用
  steamId: '*****' #steam 64位Id
  path: #番剧页面路径，默认steamgames/index.html
  title: Steam游戏库 # 该页面的标题
  quote: '+1+1+1+1+1' # 写在页面开头的一段话,支持html语法
  tab: recent # all或recent, all: 所有游戏, recent: 最近游玩的游戏
  length: 1000 # 要显示游戏的数量，游戏太多的话可以限制一下
  imgUrl: '*****' # 图片链接，在quote下面放一张图片，图片链接到Steam个人资料，可留空
  proxy: # 如果无法访问steam社区的话请使用代理
    host: # 代理ip或域名
    port: # 代理端口
```
### 使用
{% tabs 'steam插件使用' %}
<!-- tab 更新steam游戏库数据 -->
```bash
在hexo generate或hexo deploy之前使用hexo steam -u命令更新steam游戏库数据！
```
<!-- endtab -->
<!-- tab 删除游戏库数据指令 -->
```bash
hexo steam -d
```
<!-- endtab -->
{% endtabs %}

### 手动获取steam游戏数据
{% note info simple %}
如果hexo steam -u命令一直获取游戏库数据失败，可以用以下方法手动获取游戏库数据
{% endnote %}
浏览器打开https://steamcommunity.com/profiles/{steamId}/games?tab={tab}, {steamId}和{tab}分别替换为上面配置中提到的steamId和tab
网页加载完成后，打开浏览器控制台(按F12)，输入以下代码并回车：
```
let script = jQuery('script[language="javascript"]');
var games = [];
for (let i = 0; i < script.length; i++) {
  if (script.eq(i).html().includes("rgGames")) {
    let rgGames = script.eq(i).html().match(/var.*?rgGames.*?=.*?(\[[\w\W]*?\}\}\]);/);
    if (rgGames) {
      games = JSON.parse(rgGames[1]);
      break;
    }
  }
}
document.write(JSON.stringify(games))
```
将生成的内容复制到博客根目录/node_modules/hexo-steam-games/data/games.json文件内，如果没有对应的文件或目录，请自行创建

## 搜索系统
{% tabs '搜索系统' %}
<!-- tab  Algolia -->
{% note info simple %}
记得运行 hexo clean
{% endnote %}  
1. 你需要安装 [hexo-algolia](hhttps://github.com/oncletom/hexo-algolia) 或 [hexo-algoliasearch](https://github.com/LouisBarranqueiro/hexo-algoliasearch). 根据它们的説明文档去做相应的配置。
2. 修改 主题配置文件
```yaml
algolia_search:
  enable: true
  hits:
    per_page: 6

  labels:
    input_placeholder: Search for Posts
    hits_empty: "We didn't find any results for the search: ${query}" # if there are no result
    hits_stats: '${hits} results found in ${time} ms'

```
<!-- endtab -->

<!-- tab  本地搜索 -->
{% note info simple %}
记得运行 hexo clean
{% endnote %}
1. 你需要安装 hexo-generator-search. 根据它的文档去做相应配置。注意格式只支持 xml。
2. 修改主题配置文件
```yaml
# Local search
local_search:
  enable: true
  labels:
    input_placeholder: Search for Posts
    hits_empty: "We didn't find any results for the search: ${query}" # if there are no result

```
<!-- endtab -->
{% endtabs %}


##  添加哔哩哔哩追番页面
参考文档：[hexo-bilibili-bangumi](https://github.com/HCLonely/hexo-bilibili-bangumi)
{% tabs '添加哔哩哔哩追番页面' %}
<!-- tab 安装 -->
```bash
$ npm install hexo-bilibili-bangumi --save
```
<!-- endtab -->
<!-- tab 配置 -->
```markdown
bangumi: # 追番设置
  enable: true
  path:
  vmid:
  title: '追番列表'
  quote: '生命不息，追番不止！'
  show: 1
  loading:
  metaColor:
  color:
  webp:
  progress:
  extra_options:
    key: value
cinema: # 追剧设置
  enable: true
  path:
  vmid:
  title: '追番列表'
  quote: '生命不息，追番不止！'
  show: 1
  loading:
  metaColor:
  color:
  webp:
  progress:
  extra_options:
    key: value
```
<!-- endtab -->
<!-- tab 参数 -->
| 參數  |	解释 |
| ---------------- | :----------------------------------------------------------: |
| enable | 是否启用 |  
| path |   页面路径，默认bangumis/index.html, cinemas/index.html |  
| vmid |   哔哩哔哩的 vmid(uid),如何获取？ |  
| title |   该页面的标题 |  
| quote |   写在页面开头的一段话，支持 html 语法，可留空。 |  
| show |  初始显示页面：0: 想看, 1: 在看, 2: 看过，默认为1  |  
| loading |   图片加载完成前的 loading 图片  |  
| metaColor |  meta 部分(简介上方)字体颜色 |  
| color |  简介字体颜色 |  
| webp |  番剧封面使用webp格式(此格式在safari浏览器下不显示，但是图片大小可以缩小 100 倍左右), 默认true |  
| progress |  获取番剧数据时是否显示进度条，默认true |  
| extra_options |  此配置会扩展到Hexopage变量中 |  
<!-- endtab -->
<!-- tab 使用 -->
1. hexo generate或hexo deploy之前使用hexo bangumi -u命令更新追番数据，使用hexo cinema -u命令更新追剧数据！
2. 删除数据命令:hexo bangumi -d/hexo cinema -d
<!-- endtab -->
{% endtabs %}

### 手动添加番剧/追剧数据
因为某些番剧在哔哩哔哩上没有，但是又想在hexo中展示，怎么办呢？现在支持手动添加番剧数据了！
在 sources/_data/ 目录下新建文件，命名为 extra_bangumis.json(追番数据)或extra_cinemas.json(追剧数据) ，并添加以如下内容

```markdown
{
  "watchedExtra": [
    {
      "title": "缘之空",
      "type": "番剧",
      "area": "日本",
      "cover": "https://cdn.jsdelivr.net/gh/mmdjiji/bangumis@main/Yosuga-no-Sora/cover.jpg",
      "totalCount": "全12话",
      "id": 0,
      "follow": "不可用",
      "view": "不可用",
      "danmaku": "不可用",
      "coin": "不可用",
      "score": "不可用",
      "des": "远离都市的田园小镇，奥木染。春日野悠带着妹妹穹，来到了这座城镇。坐落在这里的是，儿时暑假经常造访的充满回忆的已故祖父的家。双亲因意外事故而丧生，变得无依无靠..."
    }
  ]
}
```
title 是番剧的标题，cover 是封面图链接， des 是简介，上述字段均根据需要修改。

另外除了 watchedExtra 数组，还可以在后面添加新的数组，可用数组名如下:
| 參數  |	解释 |
| ---------------- | :----------------------------------------------------------: |
| 可用数组名 	含义 | 
| wantWatchExtra | 	想看| 
| watchingExtra | 	在看| 
| watchedExtra | 	看过| 

需要注意，在两个数组之间需要用 , 分隔。

## 豆瓣插件
参考文档: [hexo-butterfly-douban](https://github.com/jerryc127/butterfly-plugins/tree/main/hexo-butterfly-douban)
{% tabs '豆瓣插件' %}
<!-- tab 安装 -->
```bash
$ npm install hexo-butterfly-douban --save
```
<!-- endtab -->
<!-- tab 配置 -->
{% note info simple %}
將下面的配置寫入站點的配置文件 _config.yml 裏(不是主題的配置文件).
{% endnote %}
```yaml
douban:
  user: mythsman
  builtin: false
  book:
    title: 'This is my book title'
    quote: 'This is my book quote'
    meta: true
    comments: true
    top_img: https://cccccc.png
    aside: true
    path: books
    limit:
  movie:
    title: 'This is my movie title'
    quote: 'This is my movie quote'
    meta: true
    comments: true
    top_img: https://cccccc.png
    aside: true
    path: movies
    limit:
  game:
    title: 'This is my game title'
    quote: 'This is my game quote'
    meta: true
    comments: true
    top_img: https://cccccc.png
    aside: true
    path: games
    limit:
  timeout: 10000 
```
<!-- endtab -->
<!-- tab 参数 -->
| 參數  |	解释 |
| ---------------- | :----------------------------------------------------------: |
| user 	| 你的豆瓣ID.打開豆瓣，登入賬户，然後在右上角點擊 "個人主頁" ，這時候地址欄的URL大概是這樣："https://www.douban.com/people/xxxxxx/" ，其中的"xxxxxx"就是你的個人ID了 | 
| builtin | 	是否將生成頁面的功能嵌入hexo s和hexo g中，默認是false,另一可選項為true(1.x.x版本新增配置項) | 
| title | 	該頁面的標題 | 
| quote | 	寫在頁面開頭的一段話,支持 html 語法. | 
| timeout  | 	【可選】爬取數據的超時時間，默認是 10000ms ,如果在使用時發現報了超時的錯(ETIMEOUT)可以把這個數據設置的大一點 | 
| meta 	| 【可選】插入 <meta name="referrer" content="no-referrer"> 到頁面，可解決部分瀏覽器無法顯示豆瓣圖片的問題（會導致一些插件出錯，例如 不蒜子計數器。） | 
| comments | 	【可選】是否顯示評論 | 
| top_img | 	【可選】是否顯示頂部圖 | 
| aside 	| 【可選】是否顯示側邊欄 | 
| path 	| 【可選】生成的網址 | 
| movie | 頁面默認為 //yourblog/movies | 
| book | 頁面默認為 //yourblog/books | 
| game | 頁面默認為 ``//yourblog/games` | 
| limit 	| 【可選】限制爬取的頁數 | 

如果只想顯示某一個頁面(比如movie)，那就把其他的配置項註釋掉即可。
<!-- endtab -->
<!-- tab 使用 -->
{% note simple %}
1. hexo-butterfly-douban 会主动生成页面，所以不需要自己创建。
2. 如遇到无法抓取问题，显示 INFO 0 movies have been loaded in xxx ms, because you are offline or your network is bad. 请过段时间再试试。
{% endnote %}
```markdown
hexo g
hexo douban
```
<!-- endtab -->
<!-- tab 更新 -->
1. 修改 package.json 內 hexo-butterfly-douban 的版本號至最新
2. 重新安裝最新版本
```markdown
npm install hexo-butterfly-douban --save
```
<!-- endtab -->
{% endtabs %}



## hexo使用过程中遇到的问题

### hexo 使用高版本后发现文章页，目录点击无反应
#### 参考文章
{% link butterfly主题目录不能跳转问题解决方法,https://blog.csdn.net/W211953332/article/details/113934598, https://profile.csdnimg.cn/E/3/2/3_w211953332 %}

### err: Template render error: (unknown path)
在写文章时发现什么都没改，结果报err: Template render error: (unknown path)
```markdown
err: Template render error: (unknown path)     unexpected end of file
原因，hexo hexo不兼容{{}}标签问题 ,在文章里面有一个\{\% endtabs \%\}未写导致这个错误
```
