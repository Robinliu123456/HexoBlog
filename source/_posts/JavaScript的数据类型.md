---
title: JavaScript的数据类型
cover: https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/c6790cb5f8b54a348c72a5ad0d269734~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp?
---

# 数据类型
## Object And Primitive

![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/6e7f93537da244319880df10399d5060~tplv-k3u1fbpfcp-watermark.image?)

## 七种原始数据类型
number,string,boolean,undefined,null,symbol（ES2015） and BigInt（ES2020）

![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/87b18a57ad8c4ac5830c848df92783e3~tplv-k3u1fbpfcp-watermark.image?)

JavaScript拥有动态类型，不需要手动的定义数据类型
## let const and var
在ES6中引入了let和const

const变量中的值不能更改，例如某人的出生年月日，它创建了一个我们无法重新分配的变量，immutable variable

```js
let age = 31；
const birthday = 1999;
```
在ES6之前，var是定义变量的方法

let是块作用域的，var是函数作用域的

