`Object.freeze()` 方法可以冻结一个对象，返回被冻结之后的对象。

## 定义和用法

### 语法

`Object.freeze(obj)`

| 参数 | 描述 |
| --- | --- |
| _obj_ | 将要被冻结的对象 |

### 返回值

被冻结之后的对象。

### 说明

冻结对象是指那些不能添加新的属性，不能修改已有属性的值，不能删除已有属性，以及不能修改已有属性的可枚举性、可配置性、可写性的对象。也就是说，这个对象永远是不可变的。

*   冻结对象的所有自身属性都不可能以任何方式被修改。任何尝试修改该对象的操作都会失败，可能是静默失败，也可能会抛出 `TypeError` 异常（严格模式）。
*   数据属性的值不可更改，访问器属性（有getter和setter）也同样（但由于是函数调用，给人的错觉是还是可以修改这个属性）。
*   如果一个属性的值是个对象，则这个对象中的属性是可以修改的，除非它也是个冻结对象。

## 实例

### 例子 1

```javascript

    var obj = {
        prop: function() {},
        foo: "bar"
    };

    // 可以添加新的属性,已有的属性可以被修改或删除
    obj.foo = "baz";
    obj.lumpy = "woof";
    delete obj.prop;

    var o = Object.freeze(obj);

    console.log(Object.isFrozen(obj)); // true

    // 现在任何修改操作都会失败
    obj.foo = "quux"; // 静默失败
    obj.quaxxor = "the friendly duck"; // 静默失败,并没有成功添加上新的属性

    // ...在严格模式中会抛出TypeError异常
    function fail() {
        "use strict";
        obj.foo = "sparky"; // 抛出TypeError异常
        delete obj.quaxxor; // 抛出TypeError异常
        obj.sparky = "arf"; // 抛出TypeError异常
    }

    fail();

    // 使用Object.defineProperty方法同样会抛出TypeError异常
    Object.defineProperty(obj, "ohai", {
        value: 17
    }); // 抛出TypeError异常

    Object.defineProperty(obj, "foo", {
        value: "eit"
    }); // 抛出TypeError异常

```

### 例子 2：关于浅冻结

下面的例子演示了一个冻结对象中的非冻结对象是可以被修改的（浅冻结）。

```javascript

    var obj = {
        internal: {}
    };

    Object.freeze(obj);
    obj.internal.a = "aValue";

    obj.internal.a; // "aValue"

    // 想让一个对象变的完全冻结,冻结所有对象中的对象,我们可以使用下面的函数.

    function deepFreeze(o) {
        var prop, propKey;
        Object.freeze(o); // 首先冻结第一层对象.
        for (propKey in o) {
            prop = o[propKey];
            if (!o.hasOwnProperty(propKey) || !(typeof prop === "object") || Object.isFrozen(prop)) {
                // 跳过原型链上的属性和已冻结的对象.
                continue;
            }

            deepFreeze(prop); //递归调用.
        }
    }

    var obj2 = {
        internal: {}
    };

    deepFreeze(obj2);
    obj2.internal.a = "anotherValue";
    obj2.internal.a; // undefined

```

## 更多

*   [Object.freeze()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Object/freeze)