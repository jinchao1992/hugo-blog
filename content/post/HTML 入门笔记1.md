---
title: "HTML 入门笔记1"
date: 2019-08-18T16:41:46+08:00
draft: false
tags:
- HTML
keywords:
- HTML 入门笔记
---

HTML（英语：HyperText Markup Language）超文本编辑语言。由**万维网联盟（W3C）**负责维护，于1990年诞生，作者是：Time Berners-Lee（蒂姆·伯纳斯-李）, 也可称为”李爵士“。是整个网页的基础，是学好前端必备的一大知识模块，学好 `HTML` 非常重要，并且我们要学会使用***语义化**的标签来书写 `HTML` 标签。

<!--more-->

## HTML 简介

1. HTML 的版本

   - HTML 4.01

   - XHTML
   - HTML5
   - HTML5.1

2. 规范
   - 由 W3C 负责文档编写

3. 声明规范
   - `<DOCTYPE html>` html5 声明规范，目前采用最广的声明规范
   - 其他参照 [https://www.w3.org/QA/2002/04/valid-dtd-list.html](https://www.w3.org/QA/2002/04/valid-dtd-list.html)

`HTML` 起手代码

```html
<!DOCTYPE html> <!--文档类型-->
<html lang="zh-CN"> <!--设置html解析语言-->
<head>
  <meta charset="UTF-8"> <!--设置字符编码-->
  <meta name="viewport" content="width=device-width,inital-scale=1.0"> <!--移动端适配代码-->
  <meta http-equiv="X-UA-Compatible" content="ie=edge"> <!--IE 浏览器使用最新版本-->
  <title>我的第一个网页</title> <!--网页名称-->
</head>
<body>
</body>
</html>
```

### HTML 标签

- `<header></header>、<nav></nav>` 双标签；
- `<img>` 单标签， 单标签可以不加`/` 结束，也可以加，最新标准可以不加；

**注意：标签不区分，但是，习惯上还是小写；标签属性名称可以是单引号也可是双引号，如：`<div title='我是div'></div>`，如没有特殊字符的话可以不用加引号。**

#### 常用章节标签(注意：这些标签都是双标签)

- `h1~h6` 标题标签，表示一级标题到六级标题；
- `<section>` 章节标签，表示一个包含在HTML文档中独立部分，如我们写文章的每一章节都用 `section` 表示，并把一些标题元素，段落元素包含进去;
- `<article>` 表示文档、页面、应用或网站中的独立结构，比如我们写的一篇文章可以用 `<article></article>` 来包裹，特点是可复用，独立存在；
- `<p>` 段落标签，表示一段文字；
- `<header>` 头部标签，表示一个独立的头部内容标签，头部内容主要放 `logo` 导航等；
- `<footer> ` 尾部标签，表示一篇文章的结尾，或者根元素的结尾，内容主要有：版权信息、网站备案信息等；
- `<main>`  主体内容标签，所有主体内容的父标签；
- `<aside>` 旁支内容标签，可以单独拆离网页的元素，与其他元素并没有任何关联，不会影响其他内容展示，如：网页侧边栏广告等;

代码示例：

```html
<header>头部内容</header>
<main>
  <h2>文章标题</h2>
  <h3>副标题</h3>
  <article>
    <section>
      <h2>1. 第一章节</h2>
      <h3>1.1 初始HTML</h3>
      <p>HTML很重要，非常重要</p>
    </section>
    <section>
      <h2>2. 第二章节</h2>
      <h3>2.1 初始HTML</h3>
      <p>HTML很重要，非常重要</p>
    </section>
  </article>
</main>
<aside>文章来源：xxx</aside>
<footer>
&copy;版权声明：归xxx所有
</footer>
```

#### HTML 内容标签

- `<ol> + <li>` 有序列表；
- `<ul> + <li>` 无序列表；
- `<dl> + <dt> + <dd>` 描述列表；
- `<pre>` 可以解析空白字符（换行、空格、tab）；
- `<hr>` 分割符，单标签； 语义上的分割，只要在语义上是分割用此元素表示，如果仅仅是样式上的需要使用 CSS 来表示；
- `<br>` 换行符，单标签；
- `<a>` 超链接，通过此链接链接整个互联网；
- `<em>` 着重元素，标记出用户需要着重阅读的内容；
- `<strong>` 表示重要的 十分重要的，是语义上的加重；
- `<code>` 展示计算机代码，可以更 `<pre>` 搭配使用；
-  `<quote>` 表示一个引用元素，默认是内联元素；
- `<blockquote> ` 块级引用元素；

#### HTML 全局属性

所谓全局属性，就是所有的标签都有的属性。

- `class`  给一个标签添加一个 `class` 属性，方便书写 `css` , 划分一类元素；
- `id` 属性表示此元素是唯一的，可以在 `JS` 中直接获取，不建议布局时给元素添加 `id`;
- `contenteditable` 规定元素是否可被用户编辑。如果给元素加上此属性后，那么不管是不是 `input` 元素，则标签都会类似于文本一样可以用来编辑内容；
- `hiddle` 让元素不可见；
- `style` 书写行间样式，行间写的样式比内联和外联的权重都大；
- `title` 给元素添加标题，用法：如果一个元素的内容过长可以增加省略号，可以把 `title` 放上所有的内容，只有鼠标滑过元素才会显示；
- `tabindex` 可以设置用键盘`tab`键，用来选中元素;
  - tabindex=负值` 通常是 `tabindex="-1"` , 表示元素是可聚焦的，但是不能通过键盘导航来访问该元素，也就是`Tab` 键；
  - `tabindex="0"` , 表示元素是可聚焦的，并且可以通过键盘导航来聚焦到该元素，它的相对顺序是当前处于的 `DOM` 解构来决定的。
  - `tabindex=正值` 表示元素可聚焦，可以通过键盘导航来聚焦到该元素；它的相对顺序按照 `tabindex` 的数值**递增而滞后聚焦**。 如果多个元素拥有相同的 `tabindex` , 它们的相对顺序按照它们在当前 `DOM` 中的先后顺序决定。
