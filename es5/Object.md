原文：[http://pij.robinqu.me/JavaScript_Core/ECMAScript/es5.html](http://pij.robinqu.me/JavaScript_Core/ECMAScript/es5.html)
源代码：[https://github.com/RobinQu/Programing-In-Javascript/blob/master/chapters/JavaScript_Core/ECMAScript/es5.md](https://github.com/RobinQu/Programing-In-Javascript/blob/master/chapters/JavaScript_Core/ECMAScript/es5.md)

>#### Object.getPrototypeOf(o)

获取给定对象的 `prototype` 对象。等价于以前的 `o.__proto__`。

>#### Object.getOwnPropertyDescriptor(o,p)

获取对象描述。和 `Object.defineProperty` 的相关方法。

>#### Object.getOwnPropertyNames(o)

获取自有属性名列表。结果列表将不包含原型链上的属性。

>#### Object.create(o,p)

以给定对象 `o` 为 `prototype` 创建新的对象并返回。如果对象描述 `p` 存在，就使用其定义刚创建的对象（类似调用 `Object.defineProperties(obj,p)`）。

>#### Object.defineProperty(o,p,attrs)

根据规则 `attrs` 定义对象 `o` 上，属性名为 `p` 的属性。

>#### Object.defineProperties(o,props)

根据对象描述 `props` 来定义对象 `o`，通常 `props` 包含多个属性的定义。

>#### Object.seal(o)

一个对象在默认状态下，

1. extensible：可以添加新的属性
2. configurable：可以修改已有属性的特性

`Object.seal` 会改变这两个特性，既不能扩展属性，也不能修改已有属性的特性。

>#### Object.freeze(o)

将对象的每个自有属性(own property)做如下操作：

* 属性的 `writable` 特性置为 `false`
* 属性的 `configurable` 特性置为 `false`

同时，该对象将不可扩展。可见，该方法比 `Object.seal` 更加严格的限制了对一个对象的未来改动。

>#### Object.preventExtensions(o)

将对象置为不可扩展。

>#### Object.isSealed(o)

判断一个对象是否 `sealed`：

* 对象的每个自有属性：如果属性的 `configurable` 特性为 `true`，则返回 `false`
* 如果对象为 `extensible` 的，那么返回 `false`
* 不满足以上两个条件，则返回 `true`

>#### Object.isFrozen(o)

* 对每个自有属性，如果该属性的 `configurable` 或 `writable` 特性为 `true`，则返回`false`
* 如果对象为 `extensible` 的，那么返回 `false`
* 不满足以上两个条件，则返回 `true`

>#### Object.isExtensible(o)

判断一个对象是否可扩展。

>#### Object.keys(o)

返回一个由给定对象的所有可枚举自身属性的属性名组成的数组，数组中属性名的排列顺序和使用 `for-in` 循环遍历该对象时返回的顺序一致（两者的主要区别是 `for-in` 还会遍历出一个对象从其原型链上继承到的可枚举属性）。

>#### Object.prototype.isPrototypeOf(v)

检查对象是否是位于给定对象 `v` 的原型链上。

>#### Object.prototype.propertyIsEnumerable(p)

检查一个对象上的属性 `p` 是否可枚举。