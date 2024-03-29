---
title: "HTTP入门"
date: 2019-08-11T14:24:02+08:00
draft: false
tags:
- HTTP
keywords:
- HTTP入门
---

<!--more-->

### 互联网的基石

------

#### www 的历史

`WWW` 全称 `World Wide Web` 翻译成中文则是 全世界范围网络。

如下图所示，简单的介绍下 www 的来历：

![](https://user-gold-cdn.xitu.io/2019/7/13/16be98d6cd6b590b?w=839&h=568&f=png&s=82012)
`URL` 解释

`https://www.baidu.com/s?wd=hello#5`

- `https` 协议
- `www.baidu.com` 网址
  - `.com .cn .net...` 顶级域名(一级)
  - `baidu.com` 二级域名
  - `www.baidu.com` 三级域名

### 请求与相应

------

#### 请求与响应介绍：

![](https://user-gold-cdn.xitu.io/2019/7/13/16be98e1accacff2?w=1362&h=471&f=png&s=108472)

通过命令的方式请求与返回

![](https://user-gold-cdn.xitu.io/2019/7/13/16be99296942f7f4?w=761&h=517&f=png&s=533230)

![](https://user-gold-cdn.xitu.io/2019/7/13/16be992d215c99cc?w=729&h=513&f=png&s=566120)

#### Chrome 如何查看请求内容

1. 打开 Network(f12, 鼠标右键审查元素) 如下图:

![](https://user-gold-cdn.xitu.io/2019/7/13/16be98ee9ef14ea7?w=1433&h=322&f=png&s=67183)

2. 地址栏输入网址
3. 在 Network 点击 Request Headers 并点击 **view sorce**， 如图：

![](https://user-gold-cdn.xitu.io/2019/7/13/16be98f86b5abd60?w=1438&h=537&f=png&s=200310)

4. 可以看到我们所请求的内容了，如下图：

![](https://user-gold-cdn.xitu.io/2019/7/13/16be98fc22bfa40b?w=1406&h=551&f=png&s=199369)
![](https://user-gold-cdn.xitu.io/2019/7/13/16be99018305137a?w=1035&h=543&f=png&s=171247)

#### Chrome 查看响应内容

1. 打开Network 与 请求一样
2. 地址栏输入网址
3. 选中一个响应的内容，查看 Response Headers ,点击 **view source** 如下图：

![](https://user-gold-cdn.xitu.io/2019/7/13/16be9908d7bdbe7e?w=904&h=333&f=png&s=71903)

#### 响应状态码

- 1xx 不经常用，了解即可
- 2xx 成功 
  - 200 请求成功
- 3xx 重定向
- 4xx 客户端错误
  - 404 找不到资源
- 5xx 服务器错误
  - 500 通用错误信息

只是工作中用到的比较常用的，需要了解更多的参考：

[维基百科 状态码解析](<https://zh.wikipedia.org/wiki/HTTP%E7%8A%B6%E6%80%81%E7%A0%81>)

[菜鸟教程](<https://www.runoob.com/http/http-status-codes.html>)

#### curl 的用法

`curl -s -v -H "请求头" -- "网址"`

- -s 不显示进度
- -v 显示请求响应
- -H 请求头

`curl -X POST -d '参数' -s -v -H '请求头' -- "网址"`

- -X 后跟着 请求方式
- -d 后跟着 参数

