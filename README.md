## :sunny:hexo-blog-suiyuan

**博客基于`Hexo`框架搭建，用到`hexo-theme-butterfly`主题,并在此基础之上做了很多修改，修复了一些bug，增加了一些新的特性和功能**

**简单使用方法：**

 1. `star` 本项目仓库 ^ o ^
 2. 安装<a href="https://git-scm.com/downloads">Git</a>, 安装<a
    href="https://nodejs.org/en/">nodeJS</a>
 3. 你可以直接`fork`一份源码到你的仓库，`clone`到本地
 4. 在本地博客仓库运行`npm install`命令安装依赖包
 5. 修改配置信息，改成自己的信息
 6. 运行命令`hexo clean`（清除生成文件），`hexo g`（生成网页）， `hexo s`（本地预览），`hexo d`（部署）

<a href="https://yangchaoyi.vip/posts/520520/">教程：【源码开放】Hexo+Github 博客butterfly 和 matery 主题 搭建完全教程【整理】</a>

### :triangular_flag_on_post:	 鸣谢
Demo:  👍 [Butterfly](https://demo.jerryc.me/)  ||   🤞 [JerryC](https://jerryc.me/)

一款基於[hexo-theme-melody](https://github.com/Molunerfinn/hexo-theme-melody)修改的主題



:fire: **提醒**

最近有人反馈使用的时候出很多 `Bug`，在此来解释一下，因为本人并没有开发主题，只是在原主题上进行了魔改，方便了新手去搭建博客，因此起名没有包含`theme`，而是 `blog`。 关于本仓库源码，本人已测试过，并且收到一些伙伴的反馈，都是可以直接跑起来的。

因此，在根目录 `_config.yml` 文件里面 `theme`配置依旧是原主题名称（大概在 `98` 行）

```cpp
theme: Butterfly
```


## :partly_sunny:特性
`hexo-theme-butterfly `是基于 <a href="https://github.com/Molunerfinn">Molunerfinn</a> 的<a href="https://github.com/Molunerfinn/hexo-theme-melody"> hexo-theme-melody</a> 的基础上进行开发的。

:pencil:	作者: <a href="https://github.com/jerryc127/hexo-theme-butterfly">JerryC</a>

:memo:PS：<a href="https://github.com/shw2018/hexo-blog-fly">参考书写风格</a>

**原主题特性：**

- 简单漂亮，文章内容美观易读
- <a href="https://material.io/">Material Design</a> 设计
- 增加了广告插入，与文章模块同类型
- 夜间模式和浅色模式切换
- 简体和繁体的切换
- 支持本地搜索`local_search`
- 响应式设计，博客在桌面端、平板、手机等设备上均能很好的展现
- 首页轮播文章及每天动态切换 `Banner` 图片
- 时间轴式的归档页
- 文章摘要自动节选功能
- 集成图片大图查看模式
- 可自定义的数据的友情链接页面
- 支持文章置顶和文章打赏
- 百度和谷歌推送
- 支持 `MathJax` 和 `katex`
- `TOC` 目录
- 提供默认 `404` 页面
- 可设置复制文章内容时追加版权信息
- 可设置阅读文章时做密码验证
- 阅读模式和公告栏展示
- <a href="https://gitalk.github.io/">Gitalk</a>、<a href="https://imsun.github.io/gitment/">Gitment</a>、<a href="https://valine.js.org/">Valine</a> 和 <a href="https://disqus.com/">Disqus</a> 评论模块
- 集成了<a href="http://busuanzi.ibruce.info/">不蒜子统计</a>、谷歌分析（`Google Analytics`）、百度分析（`Baidu Analytics`）、腾讯分享（`Tencent Analytics`）和文章字数统计等功能
- 支持在首页的音乐播放和视频播放功能
- 更多内容请观赏博客演示：<a href="https://yangchaoyi.vip/">yangchaoyi.vip</a>

**增加的工作或特性(未打钩的是已做但还没更新到源码的):**

 - [x] 修改原主题样式，开启加载动画
 - [x]  增加媒体页面
 - [x] 增加聚宝盒页面
 - [x] 增加微语页面
 - [x] 增加清单页面
 - [x] 增加留言板页面
 - [x] 增加友链页面
 - [x] 增加关于页面
 - [x] 修改公告栏语句
 - [x] 增加今日诗词，`loop`
 - [x] 增加网页运行时间与不蒜子统计
 - [x] 更改原本未显示的`Github`图标
 - [x] 添加默认头像，保持旋转
 - [x] 更改默认字体，博客名称，首尾背景图
 - [x] 页面底部 `footer` 跳动的心
 - [x] 添加访客地图
 - [x] 添加Pixiv 日榜
 - [x] 添加日历
 - [x] 添加哔哩哔哩番剧页面插件
 - [x] 添加卡通人物（看板娘）
 - [x] 地址栏添加 `abbrlink`
 - [x] 添加 `Gallery` 相册图库
 - [x] 豆瓣插件（`movie`、`book`、`game`）
 - [x] 友链界面加入自定义文字
 - [x] 友链链接区块加入一行小字
 - [x] Valine添加博主标签及评论微信、QQ通知
 - [ ] 文章尾部投票打星系统
 - [x] 添加聚宝盒页面
 - [x] 添加首页导航
 - [x] 添加音乐 `music` 页面
 - [x] `Gitalk`、`Valine` 双评论系统切换
 - [ ] 随机文章跳转
 - [ ] 加入 `steam` 游戏库界面
 - [x] 新增友链样式美化（<a href="https://yangchaoyi.vip/link/">传送门</a>）
 - [x] 友链添加炫彩呼吸灯效果
 - [x] Valine添加 `bilibili` 表情包
 - [ ] `botui` 对话框式简介页面
 - [x] 增加 `mac`风格代码
 - [x] 更改主题背景风格
 - [ ] 发表说说页面
 - [ ] 持续更新...
## :pushpin:贡献
本仓库已经为您搭建好了博客框架，极大地简化了您构建博客的工作量和复杂度，每个人都可以下载并修改成自己喜欢样式！如果你有修改想法，`fork`本仓库，欢迎PR！

## :golf:排版

笔记内容按照 <a href="https://mazhuang.org/wiki/chinese-copywriting-guidelines/">中文文案排版指北</a>进行排版。

## :name_badge:License

<a href="http://www.apache.org/licenses/LICENSE-2.0">Apache License 2.0</a>
