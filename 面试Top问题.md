# 在这里总结一下我在面试中最常被问到的一些面试问题，

## Top1. TCP 的三次握手四次挥手

<div style="text-align:center"><img width="300px" height="300px" src="img/TCP三次握手.png" style="text-align:center;margin:auto" alt="img">
</div>

```
答：
客户端 open, server listen
客户端向服务器发送，syn=1,ack=0 ,seq=w 请求， 客户端 syn-sent
服务器返回，syn=1 ,seq =u,ack=w+1,请求 , 客户端，syn-sent
客户端向服务器返回收到的确认，syn=1,ack= u+1， established —— [参考链接](https://www.pianshen.com/article/6422926311/)
```

## Top2. post 请求和 get 请求存放参数位置

```
答：
post 请求和 get 请求存放参数位置是不同的：
post 方式参数存放在请求数据包的消息体中。 get 方式参数存放在请求数据包的请求行的 URI 字段中
```

## Top3. HashMap 和 HashSet 的区别：

```
答：
定义：
HashMap： HashMap 实现了 Map 接口，Map 接口对键值对进行映射。Map 中不允许重复的键。Map 接口有两个基本的实现，HashMap 和 TreeMap。TreeMap 保存了对象的排列次序，而 HashMap 则不能。HashMap 允许键和值为 null。HashMap 是非 synchronized 的，但 collection 框架提供方法能保证 HashMap synchronized，这样多个线程同时访问 HashMap 时，能保证只有一个线程更改 Map。

HashSet： HashSet 实现了 Set 接口，它不允许集合中有重复的值，当我们提到 HashSet 时，第一件事情就是在将对象存储在 HashSet 之前，要先确保对象重写 equals()和 hashCode()方法，这样才能比较对象的值是否相等，以确保 set 中没有储存相等的对象。如果我们没有重写这两个方法，将会使用这个方法的默认实现。
```

## Top4. 从输入 URL 到页面发生了什么？

```
答：域名解析，发送请求，解析 HTML 文档，CSS 解析，布局阶段，绘制阶段。
```

## Top5. 什么是闭包，如何使用它，为什么要使用它？

```
答：闭包是指有权访问另一个函数作用域中变量的函数，

创建闭包的最常见的方式就是

在一个函数内创建另一个函数，通过另一个函数访问这个函数的局部变量,利用闭包可以突破作用链域，将函数内部的变量和方法传递到外部。

简单的说：在一个函数里面嵌套另一个函数，被嵌套的那个函数的作用域是一个闭包。
闭包的特性：

1.函数内再嵌套函数
2.内部函数可以引用外层的参数和变量
3.参数和变量不会被垃圾回收机制回收

闭包的好处

作用：创建私有变量，减少全局变量，防止变量名污染。可以操作外部作用域的变量，变量不会被浏览器回收，保存变量的值。
[参考](https://zhuanlan.zhihu.com/p/54853560)

```

## Top6. 指出下列代码的区别：

```
function Person(){}
var person = Person();
var person = new Person();

A: 第一行是定义了一个函数 Person()；第二行代码是执行函数 Person() 并将其返回值复制给变量 person，如果 Person() 是一个构造器函数的话，新的对象将不会被创建，并且 this 将被绑定到全局对象上；第三行代码是用构造函数 Person() 构造一个实例对象 person。
```

## Top7. .call 和 .apply 的区别是什么？

```
答：关于 javascript 中 apply()和 call()方法的区别
```

## Top8. == 和 === 有什么不同？

```
A: ==（相等运算法），===（严格相等运算符） JavaScript 对象的比较是引用的比较，非值的比较，对象和其本身相等，和其他任何对象不相等。 === 首先计算其操作数的值，然后比较，比较过程无任何类型转换。 == 如果两个操作数不是同一类型的，则相等运算符进行一些类型转换进行比较。 == 这里截取 JavaScript 相等表格上的的两张图片让大家更为直观的感受下。
```

## Top9. 说一下 BFC

## 了解 WebSokcet 协议具体是如何实现吗？

```
答:
```

[参考](https://juejin.cn/post/6844904001880719373)

## Top10. vue 核心面试题：组件中的 data 为什么是一个函数？

[参考](https://blog.csdn.net/qq_42072086/article/details/108060494)

## Promise 有几种状态？

1. pending
   1.1 初始的状态, 可改变.
   1.2 ⼀个 promise 在 resolve 或者 reject 前都处于这个状态。
   1.3 可以通过 resolve fulfilled 状态;
   1.4 可以通过 reject rejected 状态;

2. fulfilled
   2.1 最终态, 不可变.
   2.2 ⼀个 promise 被 resolve 后会变成这个状态.
   2.3 必须拥有⼀个 value 值

3. rejected
   3.1 最终态, 不可变.
   3.2 ⼀个 promise 被 reject 后会变成这个状态
   3.3 必须拥有⼀个 reason

Tips: 总结⼀下, 就是 promise 的状态流转是这样的

pending resolve(value) fulfilled
pending reject(reason) rejected

## ES 相关问题

[参考](https://juejin.cn/post/6844904067764846600)
