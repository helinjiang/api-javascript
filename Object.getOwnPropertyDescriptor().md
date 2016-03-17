`Object.getOwnPropertyDescriptor()` 方法返回指定对象上一个自有属性对应的属性描述符。

## 定义和用法

### 语法

`Object.getOwnPropertyDescriptor(obj, prop)`

| 参数 | 描述 |
| --- | --- |
| _obj_ | 指定的对象 |
| _prop_ | 一个属性名称，该属性的属性描述符将被返回 |

### 返回值

如果指定的属性存在于对象上，则返回其属性描述符（property descriptor），否则返回 `undefined`。

### 说明

该方法允许对一个属性的描述进行检索。在 Javascript 中，属性由一个字符串类型的“名字”（name）和一个“属性描述符”（property descriptor）对象构成。

一个属性描述符是一个记录，由下面属性当中的某些组成的： `configurable` 、 `enumerable` 、 `writable` 、 `value` 、 `set` 和 `get`。更多关于属性描述符类型以及他们属性的信息可以查看：[`Object.defineProperty()`](object-defineproperty.html)。

## 实例

``` javascript

    var o, d;

    o = {get foo() {
            return 17;
        }
    };
    d = Object.getOwnPropertyDescriptor(o, "foo");
    // d is { configurable: true, enumerable: true, get: /*访问器函数*/, set: undefined }

    o = {
        bar: 42
    };
    d = Object.getOwnPropertyDescriptor(o, "bar");
    // d is { configurable: true, enumerable: true, value: 42, writable: true }

    o = {};
    Object.defineProperty(o, "baz", {
        value: 8675309,
        writable: false,
        enumerable: false
    });
    d = Object.getOwnPropertyDescriptor(o, "baz");
    // d is { value: 8675309, writable: false, enumerable: false, configurable: false }

```

## 更多

*   [Object.getOwnPropertyDescriptor()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Object/getOwnPropertyDescriptor)