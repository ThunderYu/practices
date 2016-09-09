原文：[http://pij.robinqu.me/JavaScript_Core/ECMAScript/es5.html](http://pij.robinqu.me/JavaScript_Core/ECMAScript/es5.html)
源代码：[https://github.com/RobinQu/Programing-In-Javascript/blob/master/chapters/JavaScript_Core/ECMAScript/es5.md](https://github.com/RobinQu/Programing-In-Javascript/blob/master/chapters/JavaScript_Core/ECMAScript/es5.md)

>#### Array.isArray(a)

判断a是否为为真正的Array。

>#### Array.prototype.indexOf(e, i)

使用“严格等”来判断元素e在数组中的索引号。一个可选的搜索起点i。

>#### Array.prototype.lastIndexOf(e, i)

获取元素e在数组中最后出现的位置。起始位置i为可选。

>#### Array.prototype.every(t, c)

测试数组中的每个元素都满足测试t。之后介绍的所有数组遍历方法，都支持一个可选的上下文对象c，可以灵活设置回调函数的执行上下文。传递给数组的测试函数、遍历函数通常有如下签名：

    function(item, index, array) {}

>#### Array.prototype.some(t, c)

测试数组中是否有元素满足测试t。

>#### Array.prototype.forEach(f, c)

使用函数f遍历每个数组的元素

>#### Array.prototype.map(f, c)

使用函数f修改每个数组的每个元素。按顺序收集f的每个返回值，并返回这个新组成的数组。

>#### Array.prototype.filter(f, c)

收集通过函数测试f的数组元素。

>#### Array.prototype.reduce(r, v)

从左向右，使用函数r聚集数组的每个元素。可以可选的指定一个初始值v。

>#### Array.prototype.reduceRight(r, v)

`Array.prototype.reduce`的从右向左的版本。