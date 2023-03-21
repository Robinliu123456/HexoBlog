---
title: null，undefined 的区别 ？
cover: https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/c6790cb5f8b54a348c72a5ad0d269734~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp?
---
 null      表示一个对象是“没有值”的值，也就是值为“空”；
 undefined     表示一个变量声明了没有初始化(赋值)；
 undefined不是一个有效的JSON，而null是；
 undefined的类型(typeof)是undefined；
 null的类型(typeof)是object；
 
 Javascript将未赋值的变量默认值设为undefined；
 Javascript从来不会将变量设为null。它是用来让程序员表明某个用var声明的变量时没有值的。
 typeof undefined
    //"undefined"
    undefined :是一个表示"无"的原始值或者说表示"缺少值"，就是此处应该有一个值，但是还没有定义。当尝试读取时会返回 undefined；
    例如变量被声明了，但没有赋值时，就等于undefined
 typeof null
    //"object"
    null : 是一个对象(空对象, 没有任何属性和方法)；
    例如作为函数的参数，表示该函数的参数不是对象；
 注意：
    在验证null时，一定要使用　=== ，因为 == 无法分别 null 和　undefined
    null == undefined // true
    null === undefined // false
 再来一个例子：
    null
    Q：有张三这个人么？
    A：有！
    Q：张三有房子么？
    A：没有！
 
    undefined
    Q：有张三这个人么？
    A：有！
    Q: 张三有多少岁？
    A: 不知道（没有被告诉）