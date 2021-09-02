# 总结以往的面试经验，从哪里失败就在那里站起来！

<hr>
顺带学习一下GitDoc的使用规则
[参考链接](https://docs.github.com/cn/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

在这里总结一下我在面试中最常被问到的一些面试问题，

## Top1. TCP 的三次握手四次挥手

答：
客户端 open, server listen
客户端向服务器发送，syn=1,ack=0 ,seq=w 请求， 客户端 syn-sent
服务器返回，syn=1 ,seq =u,ack=w+1,请求 , 客户端，syn-sent
客户端向服务器返回收到的确认，syn=1,ack= u+1， established
[参考链接](https://www.pianshen.com/article/6422926311/)

## 2. post 请求和 get 请求存放参数位置

答：
post 请求和 get 请求存放参数位置是不同的：
post 方式参数存放在请求数据包的消息体中。 get 方式参数存放在请求数据包的请求行的 URI 字段中

## 3. HashMap 和 HashSet 的区别：

答：
定义：
HashMap： HashMap 实现了 Map 接口，Map 接口对键值对进行映射。Map 中不允许重复的键。Map 接口有两个基本的实现，HashMap 和 TreeMap。TreeMap 保存了对象的排列次序，而 HashMap 则不能。HashMap 允许键和值为 null。HashMap 是非 synchronized 的，但 collection 框架提供方法能保证 HashMap synchronized，这样多个线程同时访问 HashMap 时，能保证只有一个线程更改 Map。

HashSet： HashSet 实现了 Set 接口，它不允许集合中有重复的值，当我们提到 HashSet 时，第一件事情就是在将对象存储在 HashSet 之前，要先确保对象重写 equals()和 hashCode()方法，这样才能比较对象的值是否相等，以确保 set 中没有储存相等的对象。如果我们没有重写这两个方法，将会使用这个方法的默认实现。
