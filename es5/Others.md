原文1：[浅谈 JS 对象添加 getter与 setter 的5种方法以及如何让对象属性不可配置或枚举](https://segmentfault.com/a/1190000003882976)

原文2：[http://pij.robinqu.me/JavaScript_Core/ECMAScript/es5.html](http://pij.robinqu.me/JavaScript_Core/ECMAScript/es5.html)

>#### 其他特性

* 放开了关键字不允许作为属性名的限制
* getter和setter函数
* 严格模式

对象里目前存在的属性描述符有两种主要形式：数据描述符和存取描述符。

1. 数据描述符是一个拥有可写或不可写值的属性。
2. 存取描述符是由一对 getter-setter 函数功能来描述的属性。
3. 描述符必须是两种形式之一；不能同时是两者。

数据描述符和存取描述符均具有以下可选键值：

```
configurable
    当且仅当这个属性描述符值为 true 时，该属性可能会改变，也可能会被从相应的对象删除。默认为 false。
enumerable 
    true 当且仅当该属性出现在相应的对象枚举属性中。默认为 false。
```

数据描述符同时具有以下可选键值：

```
value 
    与属性相关的值。可以是任何有效的 JavaScript 值（数值，对象，函数等）。默认为 undefined。
writable 
    true 当且仅当可能用 赋值运算符 改变与属性相关的值。默认为 false。
```

存取描述符同时具有以下可选键值：

```
get 
    一个给属性提供 getter 的方法，如果没有 getter 则为 undefined。方法将返回用作属性的值。默认为 undefined。
set
    一个给属性提供 setter 的方法，如果没有 setter 则为 undefined。该方法将收到作为唯一参数的新值分配给属性。
    默认为 undefined。
```

数据描述符包括两个属性 : `value` 属性以及 `writable` 属性，第一个属性用来声明当前欲修饰的属性的值，第二个属性用来声明当前对象是否可写即是否可以修改

存取描述符就包括 `get` 与 `set` 属性用来声明欲修饰的象属性的 `getter` 及 `setter`

属性描述符内部，数据描述符与存取描述符只能存在其中之一，但是不论使用哪个描述符都可以同时设置 `configurable` 属性以及`enumerable` 属性。
`configurable` 属性用来声明欲修饰的属性是否能够配置，仅有当其值为 `true` 时，被修饰的属性才有可能能够被删除，或者重新配置。
`enumerable` 属性用来声明欲修饰属性是否可以被枚举。

> 参考代码

```javascript
var obj = {};
Object.defineProperty(obj, "name", {
	enumerable: true,
	configurable: true,
	set: function(val) {
		log("set name to -> " + val);
	},
	get: function() {
		log("get name value");
	}
});
obj.name;//get name value
obj.name = 2;//set name to -> 2
delete obj.name;//true

var obj2 = {};
Object.defineProperties(obj2, {
	name: {
		value: "Harry",
		writable: false,
        enumerable: false
	},
	sex: {
		enumerable: true,
		configurable: true,
		set: function(val) {
			log("set sex");
		},
		get: function() {
			log("get sex");
		}
	}
});
obj2.name;//Harry
obj2.name = 2;//NOT CHANGE
delete obj2.name;//false
for(var i in obj2){console.log(i);}//sex
```