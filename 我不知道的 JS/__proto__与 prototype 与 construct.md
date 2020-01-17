##  \_\_ proto \__  、 prototype、 construct 的 关系

[参考链接](https://blog.csdn.net/cc18868876837/article/details/81211729)

两行代码

```javascript
function Foo (){...}
let f1 = new Foo() 
```

一个对象：f1

一个函数：Foo

三个属性：  \__ proto \__ 、 prototype 、 construct

名词： 原型对象，构造函数



 \__ proto \__ 、construct 属性是对象所独有的。

 prototype 属性是 函数所独有的，但是在 JS 中 **函数也是对象的一种**。所以函数也有 对象所拥有的属性。



#### \__proto__

> 从一个对象指向另一对象

作用： 访问一个对象的属性，如果不存在，如果该对象内部不存在这个属性，那么就会去她的 \__proto__ 属性所指向的对象（可以理解为父对象）里找，如果父对象也不存在，那么继续向上找，直到为空。以上这种通过  \__proto__ 属性来连接对象知道 null 的一条链 几位我们所谓的**原型链**



![原型链](/Users/YuanJie/Desktop/原型链.png)



上图左边画框的那部分就是原型链。



#### prototype

> 函数独有，从一个函数指向另个一对象。
>
> 任何函数创建的时候，其实都是回默认同时创建 该函数的 prototype 对象。

它的含义是： 函数的原型对象。也就是这函数（Foo）所创建的实例（f1）的原型对象。

作用是： 它的作用是包含可以由特定类型的所有实例共享的属性和方法，**也就是让该函数所实例化的对象们都可以找到共用的属性和方法。**





####  construct

> 从一个对象指向一个函数。

含义是： **指向该对象的构造函数**

作用是： 指向该对象的构造函数。

单从 constructor 这个属性来讲，只有 prototye 对象才有。而创建的实例通过 \__proto__ 属性继承了 prototype 对象的 construct 属性。

![原型链1](/Users/YuanJie/Desktop/原型链1.png)





最后，放一种总图:

![原型链2](/Users/YuanJie/Desktop/原型链2.png)