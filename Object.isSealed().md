`Object.isSealed()` 方法判断一个对象是否是密封的（sealed）。

## 定义和用法

### 语法

`Object.isSealed(obj)`

| 参数 | 描述 |
| --- | --- |
| _obj_ | 指定的对象 |

### 返回值

`true`：密封的，`false`：非密封的。

### 说明

密封对象是指那些不可扩展的，且所有自身属性都不可配置的（non-configurable）对象。

【区分可扩展、密封、冻结等概念】

### 兼容性

在 ES5 中，如果参数不是一个对象类型，将抛出一个 `TypeError` 异常。在 ES6 中， non-object 参数将被视为一个密封的普通对象，因此会返回 `true` 。

```javascript
    Object.isSealed(1);
    // TypeError: 1 is not an object (ES5 code)

    Object.isSealed(1);
    // true                          (ES6 code)
```

## 实例

```javascript
    // 新建的对象默认不是密封的.
    var empty = {};
    console.log(Object.isSealed(empty)); // false

    // 如果你把一个空对象变的不可扩展,则它同时也会变成个密封对象.
    Object.preventExtensions(empty);
    console.log(Object.isSealed(empty)); // true

    // 但如果这个对象不是空对象,则它不会变成密封对象,因为密封对象的所有自身属性必须是不可配置的.
    var hasProp = { fee: "fie foe fum" };
    Object.preventExtensions(hasProp);
    console.log(Object.isSealed(hasProp)); // false

    // 如果把这个属性变的不可配置,则这个对象也就成了密封对象.
    Object.defineProperty(hasProp, "fee", { configurable: false });
    console.log(Object.isSealed(hasProp)); // true

    // 最简单的方法来生成一个密封对象,当然是使用Object.seal.
    var sealed = {};
    Object.seal(sealed);
    console.log(Object.isSealed(sealed)); // true

    // 一个密封对象同时也是不可扩展的.
    console.log(Object.isExtensible(sealed)); // false

    // 一个密封对象也可以是一个冻结对象,但不是必须的.
    console.log(Object.isFrozen(sealed)); // true ，所有的属性都是不可写的
    var s2 = Object.seal({ p: 3 });
    console.log(Object.isFrozen(s2)); // false， 属性"p"可写

    var s3 = Object.seal({ get p() { return 0; } });
    console.log(Object.isFrozen(s3)); // true ，访问器属性不考虑可写不可写,只考虑是否可配置
```

## 更多

*   [Object.isSealed()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Object/isSealed)