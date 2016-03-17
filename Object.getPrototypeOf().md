`Object.getPrototypeOf()` 方法返回指定对象的原型（也就是该对象内部属性[[Prototype]]的值）。

## 定义和用法

### 语法

`Object.getPrototypeOf(obj)`

| 参数 | 描述 |
| --- | --- |
| _obj_ | 指定的对象 |

### 返回值

指定对象的原型。

### 兼容性

在 ES5 中，如果参数不是一个对象类型，将抛出一个 `TypeError` 异常。在 ES6 中， non-object 参数被强制转换为 object 。

```javascript

    Object.getPrototypeOf("foo");
    // TypeError: "foo" is not an object (ES5 code)

    Object.getPrototypeOf("foo");
    // String.prototype                  (ES6 code)

```

## 实例

```javascript

    var proto = {};
    var obj = Object.create(proto);
    Object.getPrototypeOf(obj) === proto; // true

```

## 更多

*   [Object.getPrototypeOf()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Object/getPrototypeOf)