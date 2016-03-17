`Object.isExtensible()` 方法判断一个对象是否是可扩展的（是否可以在它上面添加新的属性）。

## 定义和用法

### 语法

`Object.isExtensible(obj)`

| 参数 | 描述 |
| --- | --- |
| _obj_ | 指定的对象 |

### 返回值

`true`：可扩展，`false`：不可扩展。

### 说明

默认情况下，对象是可扩展的：即可以为他们添加新的属性。`Object.preventExtensions()`，`Object.seal()` 或 `Object.freeze()` 方法都可以标记一个对象为不可扩展（non-extensible）

### 兼容性

在 ES5 中，如果参数不是一个对象类型，将抛出一个 `TypeError` 异常。在 ES6 中， non-object 参数将被视为一个不可扩展的普通对象，因此会返回 `false` 。

``` javascript

    Object.isExtensible(1);
    // TypeError: 1 is not an object (ES5 code)

    Object.isExtensible(1);
    // false                          (ES6 code)

```

## 实例

``` javascript

    // 新对象默认是可扩展的.
    var empty = {};
    console.log(Object.isExtensible(empty)); // true

    // ...可以变的不可扩展.
    Object.preventExtensions(empty);
    console.log(Object.isExtensible(empty)); // false

    // 密封对象是不可扩展的.
    var sealed = Object.seal({});
    console.log(Object.isExtensible(empty)); // false

    // 冻结对象也是不可扩展.
    var frozen = Object.freeze({});
    console.log(Object.isExtensible(empty)); // false

```

## 更多

*   [Object.isExtensible()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Object/isExtensible)