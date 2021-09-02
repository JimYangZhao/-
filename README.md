# 总结以往的面试经验，从哪里失败就在那里站起来！

<hr>

## TCP 的三次握手四次挥手

答：
客户端 open, server listen
客户端向服务器发送，syn=1,ack=0 ,seq=w 请求， 客户端 syn-sent
服务器返回，syn=1 ,seq =u,ack=w+1,请求 , 客户端，syn-sent
客户端向服务器返回收到的确认，syn=1,ack= u+1， established

## post 请求和 get 请求存放参数位置

答：
post 请求和 get 请求存放参数位置是不同的：
post 方式参数存放在请求数据包的消息体中。 get 方式参数存放在请求数据包的请求行的 URI 字段中

## HashMap 和 HashSet 的区别：

答：
定义：
HashMap： HashMap 实现了 Map 接口，Map 接口对键值对进行映射。Map 中不允许重复的键。Map 接口有两个基本的实现，HashMap 和 TreeMap。TreeMap 保存了对象的排列次序，而 HashMap 则不能。HashMap 允许键和值为 null。HashMap 是非 synchronized 的，但 collection 框架提供方法能保证 HashMap synchronized，这样多个线程同时访问 HashMap 时，能保证只有一个线程更改 Map。

HashSet： HashSet 实现了 Set 接口，它不允许集合中有重复的值，当我们提到 HashSet 时，第一件事情就是在将对象存储在 HashSet 之前，要先确保对象重写 equals()和 hashCode()方法，这样才能比较对象的值是否相等，以确保 set 中没有储存相等的对象。如果我们没有重写这两个方法，将会使用这个方法的默认实现。

### 滴滴 第一轮

## 简单介绍自己

答：
根据自己的以往经历，不要默背简历内容，主要讲讲技术经历，靠近 JD 需求的项目经历，所用过的计算机语言，在项目中主要负责的地方都有哪里，做过多长时间，前一份工作具体辞职的原因，等等，不要太长尽量保持在 5-8 分钟

## ES6 有哪些更新

答：

## 你为什么会选择 Vue 作为主要开发工具，它的好处在哪里？

面试官答：
要从架构和封装的角度去分析这个工具的优点，还有你使用它的原因。

## 解释下原型继承的原理。

A:原型继承的基础是原型链查找。 原型链查找基本概念：

每一个函数 F 都有一个原型对象（prototype）F.prototype
每一个函数都可以通过 new 关键字化身成为一个类构造函数，new F 会产生一个对象 O
在调用对象的某个属性或者方法，比如 http://O.xxx 的时候，会首先查找对象自身是否有这个方法或者属性，如果没找到就会去对象的构造函数的原型对象中查找（注意有两个定语），也就是查找 O 的构造函数 F 的原型对象 http://F.prototype.xxx
F.prototype 也是一个对象，查找 http://F.prototype.xxx 的时候会重复第 3 步的过程
参考：

深入理解 javascript 原型继承
JavaScript 原型继承工作原理
Prototypal Inheritance in JavaScript

## Apply, call 等语法的应用

答：

## Webpack 里的 loader 用法

答：

## TS 老师想考，但我 JS 水平较弱没考我，感谢

## 了解 React Hook，还有生命周期吗？都有哪些应用

这里我谈到了 State 和 Effect 的 Hook，生命周期还需要再去复习一下

## Vue 的生命周期，以及 Vuex 的应用场景

Vue 的生命周期从 before Create 开始到 deactivated。
Vuex 是一个专为 Vue.js 应用程序开发的状态管理模式。它采用集中式存储管理应用的所有组件的状态，并以相应的规则保证状态以一种可预测的方式发生变化。
Vuex 可以帮助我们管理共享状态，并附带了更多的概念和框架。这需要对短期和长期效益进行权衡。这时候就需要用到 Vuex

### 写代码

## JS：用一段 JS 代码写一个继承

答：
1、原型链
2、借用构造函数
3、组合继承（组合使用原型链和借用构造函数）
4、原型式继承
5、寄生式继承
6、寄生组合式继承（组合使用组合继承和寄生式继承）
参考：https://www.huaweicloud.com/articles/a4e74114bd901aa952606d5d1ce48a58.html

## CSS：写一段左中右格式的 html 代码，有几种方式让左侧和右侧的宽度限制一个固定的宽度，中间的自适应屏幕尺寸

答：

<div class="d-flex justify-space-between">
    <div style="width:xx;"></div>
    <div></div>
    <div style="width:xx;"></div>
</div>
类似于这样的写法，我当时写了3种，应该还有很多种

## CSS：横竖向居中有几种方式？

答：

### 其他面试

问题：从输入 URL 到页面发生了什么？
答：域名解析，发送请求，解析 HTML 文档，CSS 解析，布局阶段，绘制阶段。

## 什么是闭包，如何使用它，为什么要使用它？

答

## 指出下列代码的区别：

function Person(){}
var person = Person();
var person = new Person();

A: 第一行是定义了一个函数 Person()；第二行代码是执行函数 Person() 并将其返回值复制给变量 person，如果 Person() 是一个构造器函数的话，新的对象将不会被创建，并且 this 将被绑定到全局对象上；第三行代码是用构造函数 Person() 构造一个实例对象 person。

## .call 和 .apply 的区别是什么？

答：关于 javascript 中 apply()和 call()方法的区别

## == 和 === 有什么不同？

A: ==（相等运算法），===（严格相等运算符） JavaScript 对象的比较是引用的比较，非值的比较，对象和其本身相等，和其他任何对象不相等。 === 首先计算其操作数的值，然后比较，比较过程无任何类型转换。 == 如果两个操作数不是同一类型的，则相等运算符进行一些类型转换进行比较。 == 这里截取 JavaScript 相等表格上的的两张图片让大家更为直观的感受下。

## 说一下 BFC
