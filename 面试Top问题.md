# 在这里总结一下我在面试中最常被问到的一些面试问题，

## Top1. TCP 的三次握手四次挥手

答：
客户端 open, server listen
客户端向服务器发送，syn=1,ack=0 ,seq=w 请求， 客户端 syn-sent
服务器返回，syn=1 ,seq =u,ack=w+1,请求 , 客户端，syn-sent
客户端向服务器返回收到的确认，syn=1,ack= u+1， established ——[参考链接](https://www.pianshen.com/article/6422926311/)
<br><br>

<div style="margin:auto;text-align:center;">![image](img/TCP三次握手.png)</div>

## 2. post 请求和 get 请求存放参数位置

答：
post 请求和 get 请求存放参数位置是不同的：
post 方式参数存放在请求数据包的消息体中。 get 方式参数存放在请求数据包的请求行的 URI 字段中

## 3. HashMap 和 HashSet 的区别：

答：
定义：
HashMap： HashMap 实现了 Map 接口，Map 接口对键值对进行映射。Map 中不允许重复的键。Map 接口有两个基本的实现，HashMap 和 TreeMap。TreeMap 保存了对象的排列次序，而 HashMap 则不能。HashMap 允许键和值为 null。HashMap 是非 synchronized 的，但 collection 框架提供方法能保证 HashMap synchronized，这样多个线程同时访问 HashMap 时，能保证只有一个线程更改 Map。

HashSet： HashSet 实现了 Set 接口，它不允许集合中有重复的值，当我们提到 HashSet 时，第一件事情就是在将对象存储在 HashSet 之前，要先确保对象重写 equals()和 hashCode()方法，这样才能比较对象的值是否相等，以确保 set 中没有储存相等的对象。如果我们没有重写这两个方法，将会使用这个方法的默认实现。

## 4. 从输入 URL 到页面发生了什么？

答：域名解析，发送请求，解析 HTML 文档，CSS 解析，布局阶段，绘制阶段。

## 5. 什么是闭包，如何使用它，为什么要使用它？

答

## 6. 指出下列代码的区别：

function Person(){}
var person = Person();
var person = new Person();

A: 第一行是定义了一个函数 Person()；第二行代码是执行函数 Person() 并将其返回值复制给变量 person，如果 Person() 是一个构造器函数的话，新的对象将不会被创建，并且 this 将被绑定到全局对象上；第三行代码是用构造函数 Person() 构造一个实例对象 person。

## 7. .call 和 .apply 的区别是什么？

答：关于 javascript 中 apply()和 call()方法的区别

## 8. == 和 === 有什么不同？

A: ==（相等运算法），===（严格相等运算符） JavaScript 对象的比较是引用的比较，非值的比较，对象和其本身相等，和其他任何对象不相等。 === 首先计算其操作数的值，然后比较，比较过程无任何类型转换。 == 如果两个操作数不是同一类型的，则相等运算符进行一些类型转换进行比较。 == 这里截取 JavaScript 相等表格上的的两张图片让大家更为直观的感受下。

## 9. 说一下 BFC
