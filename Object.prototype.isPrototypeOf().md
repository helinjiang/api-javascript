`Object.prototype.isPrototypeOf()` 方法用来测试一个对象是否存在于另一个对象的原型链上。

## 定义和用法

### 语法

`prototype.isPrototypeOf(object)`

| 参数 | 描述 |
| --- | --- |
| _prototype_ | 检查该对象是否在参数 `object` 的原型链上 |
| _object_ | 在该对象的原型链上搜寻 |

### 返回值

`true`：自身属性， `false`：不是自身属性。

### 说明

`Object.prototype.isPrototypeOf()` 方法允许你检查一个对象是否存在于另一个对象的原型链上。

> `Object.prototype.isPrototypeOf()` 和 `instanceof` 操作符是不同的。在表达式 `object instanceof AFunction` 中，检测的是 `AFunction.prototype` 是否在 `object` 的原型链中，而不是检测 `AFunction` 自身。

## 实例

``` javascript

    function Fee() {
        // . . .
    }

    function Fi() {
        // . . .
    }
    Fi.prototype = new Fee();

    function Fo() {
        // . . .
    }
    Fo.prototype = new Fi();

    function Fum() {
        // . . .
    }
    Fum.prototype = new Fo();

    // 下面创建一个 Fum 实例,检测 Fi.prototype 是否存在于该实例的原型链上.
    var fum = new Fum();
    console.log(Fi.prototype.isPrototypeOf(fum)); // true
    console.log(fum instanceof Fi); // true

```

## 更多

*   [Object.prototype.isPrototypeOf()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Object/isPrototypeOf)