---
title: JavaScript由谁来运行？
cover: https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/cbc4c7e8321140f999a037be1a8e45f2~tplv-k3u1fbpfcp-zoom-crop-mark:1512:1512:1512:851.awebp?
---
## 关于浏览器内核
>  我们经常会说：不同的浏览器有不同的内核组成
首先我们需要提到第一名词是浏览器内核
常见的浏览器内核有：

1.  Gecko：早期被Netscape和Mozilla Firefox浏览器浏览器使用；
1.  Trident：微软开发，被IE4~IE11浏览器使用，但是Edge浏览器已经转向Blink；
1.  Webkit：苹果基于KHTML开发、开源的，用于Safari，Google Chrome之前也在使用；
1.  Blink：是Webkit的一个分支，Google开发，目前应用于Google Chrome、Edge、Opera等；

## 浏览器引擎

> 事实上，我们经常说的浏览器内核指的是浏览器的排版引擎：
> 排版引擎 layout engine ），也称为 浏览器引擎 browser engine ）、 页面渲染引擎 rendering engine ）或 样版引擎 。

  **那么，JavaScript代码由谁来执行呢？**
  
  我们知道浏览器引擎（排版引擎、页面渲染引擎）解析html+css，渲染页面，JavaScript可以在浏览器和Node环境下运行。

## JavaScript引擎
**为什么需要JavaScript引擎呢？**

我们知道，高级的编程语言都是需要转成最终的机器指令来执行的；

事实上我们编写的JavaScript无论你交给浏览器或者Node执行，最后都是需要被CPU执行的；

但是CPU只认识自己的指令集，实际上是机器语言，才能被CPU所执行；

所以我们需要JavaScript引擎帮助我们将JavaScript代码翻译成CPU指令来执行；

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/ac73ae66dc5b47718073f70725cbad82~tplv-k3u1fbpfcp-zoom-1.image)

**比较常见的JavaScript引擎有哪些呢？**

1. **SpiderMonkey**：第一款JavaScript引擎，由Brendan Eich开发（也就是JavaScript作者）；
2. **Chakra**：微软开发，用于IE浏览器；
3.  **JavaScriptCore**：WebKit中的JavaScript引擎，Apple公司开发；
4.   **V8**：Google开发的强大JavaScript引擎，也帮助Chrome从众多浏览器中脱颖而出；
## 浏览器内核和JS引擎的关系
**这里我们先以WebKit为例，WebKit事实上主要由两部分组成的：**

WebCore **：** 负责HTML解析、布局、渲染等等相关的工作；

JavaScriptCore **：** 解析、执行JavaScript代码；

![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/cd685c4eda8f44f7bfc2e562844dc67a~tplv-k3u1fbpfcp-watermark.image?)
## 移动端App里的JS引擎
早期，iOS端app内嵌网页，用到是组件：UI WebView

![image.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/7fd64b8a6e4746bea4746d744fb9223c~tplv-k3u1fbpfcp-watermark.image?)
现在使用到的WKWeb View

官方介绍为显示交互式Web内容（如应用内浏览器）的对象，其实就是一个组件容器，包含的内容也就是WebCore和JavaScript Core。
![image.png](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/be7e1358fced4d09aa4bc34688853274~tplv-k3u1fbpfcp-watermark.image?)
## 小程序里的JS引擎

**小程序中也是这样的划分：**

在小程序中编写的JavaScript代码就是被JSCore执行的,核心思想也就是渲染层和逻辑层，来连接网页应用和Native应用。

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/bbb38188f3ab42c4b573ef82730ff8b0~tplv-k3u1fbpfcp-zoom-1.image)
