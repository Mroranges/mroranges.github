---
title: 部署hexo踩过的坑
date: 2021-11-01 22:38:20
description: 我在部署过程踩过的一些坑
tags: 
    - hexo
categories:
    - hexo
---

## hexo 部署遇到的问题

### TypeError

```
FATAL Something's wrong. Maybe you can find the solution here: https://hexo.io/docs/troubleshooting.html
TypeError [ERR_INVALID_ARG_TYPE]: The "mode" argument must be integer. Received an instance of Object
    at copyFile (fs.js:1890:10)
    at tryCatcher (C:\Users\Administrator\blog\node_modules\bluebird\js\release\util.js:16:23)
    at ret (eval at makeNodePromisifiedEval (C:\Users\Administrator\blog\node_modules\bluebird\js\release\promisify.js:184:12), <anonymous>:13:39)
    at C:\Users\Administrator\blog\node_modules\hexo-deployer-git\node_modules\hexo-fs\lib\fs.js:144:39
    at tryCatcher 
```

### 解决办法

直接到官网下载最新稳定版：https://nodejs.org/en/download/

然后重新执行 `hexo clean && hexo deploy` 打包命令就好了。



### spawn failed：

    先是出现错误：
    error：spawn failed...
    然后经过一些博客的操作会出现以下问题：
    fatal: cannot lock ref 'HEAD': unable to resolve reference HEAD: Invalid argument error: src refspec
    或者：
    error: src refspec HEAD does not match any.等等

总结一下：
问题大多是因为git进行push或者hexo d的时候改变了一些.deploy_git文件下的内容。

### 解决办法：

    删除.deploy_git文件夹;
    输入git config --global core.autocrlf false
    然后，依次执行：
    hexo clean
    hexo g
    hexo d



### hexo-douban遇到的问题

使用豆瓣插件 hexo clean后，我是等了一段时间才好的

```
Cannot GET /books/
```



### git问题

 1、报错OpenSSL SSL_read: Connection was reset, errno 10054

解决：git config --global http.sslVerify "false"

2、查看github 是否连接上

​		ssh -T git@github.com

3、Failed to connect to github.com port 443:connection timed out

​	git config --global --unset http.proxy

​	git config --global --unset https.proxy



### The file will have its original line endings in your working directory

首先出现这个问题主要原因是：我们从别人github地址上通过git clone下载下来，而又想git push到我们自己的github上，那么就会出现上面提示的错误信息

 git rm -r --cached .
 git config core.autocrlf false

 git add .

. 代表当前目录





## PICGO+Github搭建图床

```
StatusCodeError: 422 - {"message":"Invalid request.\n\n\"sha\" wasn't supplied.","documentation_url":"https://docs.github.com/rest/reference/repos#create-or-update-file-contents"}
```

显示以上错误，开启时间戳重命名解决了该问题

[部分问题文档](https://github.com/Molunerfinn/PicGo/blob/dev/FAQ.md)

### PICGO使用CDN加快图片的访问速度

自定义域名

*https://cdn.jsdelivr.net/gh/GitHub用户名/仓库名*



### GitHub的raw.githubusercontent.com无法链接

C:\Windows\System32\drivers\etc

修改host文件 添加

199.232.28.133 raw.githubusercontent.com

 
