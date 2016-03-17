`Object.prototype.constructor` 属性返回一个指向创建了该对象原型的函数引用。

## 定义和用法

### 描述

需要注意的是，该属性的值是那个函数本身，而不是一个包含函数名称的字符串。对于原始值（如1，true 或 "test"），该属性为只读。

所有对象都会从它的原型上继承一个 constructor 属性：

```javascript

    var o = new Object // 或者 o = {}
    console.log(o.constructor == Object); // true

    var a = new Array // 或者 a = []
    console.log(a.constructor == Array); // true

    var n = new Number(3)
    console.log(n.constructor == Number); // true

```

即使一些DOM对象并不是你用构造函数生成的，但你仍然可以将它们与对应的构造函数进行比较。比如：

```javascript

    console.log(document.constructor == HTMLDocument); // true
    console.log(document.head.constructor == HTMLHeadElement); // true

```

## 实例

### 例子 1：打印出一个对象的构造函数

下例首先创建了一个构造原型（即构造函数）Tree 和该原型的一个对象 theTree。接着打印出了对象 theTree 的 constructor 属性。

```javascript

    function Tree(name) {
        this.name = name;
    }

    var theTree = new Tree("Redwood");
    console.log("theTree.constructor is " + theTree.constructor)

    // 输出
    // theTree.constructor is function Tree(name) {
    //     this.name = name;
    // }

```

### 例子 2：改变这个对象的constructor属性的值

下面的例子展示了如何修改基本类型对象的 `constructor` 属性的值。只有 `true`, `1` 和 `"test"` 的不受影响，因为创建他们的是只读的原生构造函数（native constructors）。这个例子也说明了依赖一个对象的 `constructor` 属性并不安全。

```javascript

    function Type() {};

    var types = [
        new Array, [],
        new Boolean,
        true, // remains unchanged
        new Date,
        new Error,
        new Function,
        function() {},
        Math,
        new Number,
        1, // remains unchanged
        new Object, {},
        new RegExp,
        /(?:)/,
        new String,
        "test" // remains unchanged
    ];

    for (var i = 0; i < types.length; i++) {
        types[i].constructor = Type;
        types[i] = [types[i].constructor, types[i] instanceof Type, types[i].toString()];
    };

    console.log(types.join("\n"));

    // 输出
    // function Type() {},false,
    // function Type() {},false,
    // function Type() {},false,false
    // function Boolean() { [native code] },false,true
    // function Type() {},false,Sat Nov 21 2015 21:32:15 GMT+0800 (中国标准时间)
    // function Type() {},false,Error
    // function Type() {},false,function anonymous() {}
    // function Type() {},false,function () {}
    // function Type() {},false,[object Math]
    // function Type() {},false,0
    // function Number() { [native code] },false,1
    // function Type() {},false,[object Object]
    // function Type() {},false,[object Object]
    // function Type() {},false,/(?:)/
    // function Type() {},false,/(?:)/
    // function Type() {},false,
    // function String() { [native code] },false,test

```

## 更多

*   [Object.prototype.constructor](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Object/prototype)