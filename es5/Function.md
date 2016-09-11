原文：[http://pij.robinqu.me/JavaScript_Core/ECMAScript/es5.html](http://pij.robinqu.me/JavaScript_Core/ECMAScript/es5.html)
源代码：[https://github.com/RobinQu/Programing-In-Javascript/blob/master/chapters/JavaScript_Core/ECMAScript/es5.md](https://github.com/RobinQu/Programing-In-Javascript/blob/master/chapters/JavaScript_Core/ECMAScript/es5.md)

>#### Function.prototype.bind(thisTarget, arg1, ...argn)

为了指定当前函数的上下文对象和运行参数，该函数创建一个新的函数，保留给定的`this`对象和运行参数。

    bind和call以及apply一样，都是可以改变上下文的this指向的。不同的是，call和apply一样，直接引用在方法上，而bind绑定this后返回
    一个方法，但内部核心还是apply。