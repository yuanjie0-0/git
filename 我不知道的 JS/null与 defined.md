## null 与 defined 的区别



#### null

null 表示 ‘没有对象’,即该处不应该有值，典型用法是：

1. 作为函数的参数，表示该函数的参数 不是 **对象**
2. 作为对象原型链的终点



#### undefined

undefined 表示 “缺少值”， 就是此处应该有一个值，但是还没有定义，典型的用法是：

1. 变量被声明了，但没有被赋值，就等于 undefined
2. 调用 函数，应该提供的参数没有提供，该参数 等于 undefined
3. 对象没有赋值的属性，该属性的值为 undefined
4. 函数没有返回值，默认返回 undefined



```javascript
var i;
i // 

function f(x){
  console.log(x)
}
// f() undefined

var 0 = new Object()
o.p // undefined

var x = f()
x // x undefined

```

**个人觉得还是根据语义来区分吧，null更多的表示引用语义而undefined更多的表示值语义，虽然在数值上接近**