# 总结以往的面试经验，从哪里失败就在那里站起来！
<hr>

## TCP的三次握手四次挥手
答：
客户端open, server listen
客户端向服务器发送，syn=1,ack=0 ,seq=w请求， 客户端syn-sent
服务器返回，syn=1 ,seq =u,ack=w+1,请求   , 客户端，syn-sent
客户端向服务器返回收到的确认，syn=1,ack= u+1，  established

## post请求和get请求存放参数位置
答：
post请求和get请求存放参数位置是不同的：
post方式参数存放在请求数据包的消息体中。 get方式参数存放在请求数据包的请求行的URI字段中

## HashMap和HashSet的区别：
答：
定义：
HashMap： HashMap实现了Map接口，Map接口对键值对进行映射。Map中不允许重复的键。Map接口有两个基本的实现，HashMap和TreeMap。TreeMap保存了对象的排列次序，而HashMap则不能。HashMap允许键和值为null。HashMap是非synchronized的，但collection框架提供方法能保证HashMap synchronized，这样多个线程同时访问HashMap时，能保证只有一个线程更改Map。

HashSet： HashSet实现了Set接口，它不允许集合中有重复的值，当我们提到HashSet时，第一件事情就是在将对象存储在HashSet之前，要先确保对象重写equals()和hashCode()方法，这样才能比较对象的值是否相等，以确保set中没有储存相等的对象。如果我们没有重写这两个方法，将会使用这个方法的默认实现。
