`Object.isFrozen()` 方法判断一个对象是否被冻结（frozen）。

## 定义和用法

### 语法

`Object.isFrozen(obj)`

| 参数 | 描述 |
| --- | --- |
| _obj_ | 指定的对象 |

### 返回值

`true`：已被冻结，`false`：尚未被冻结。

### 说明

一个对象是冻结的（frozen）是指它不可扩展，所有属性都是不可配置的（non-configurable），且所有数据属性（data properties）都是不可写的（non-writable）。数据属性是值那些没有取值器（getter）或赋值器（setter）的属性。

### 兼容性

在 ES5 中，如果参数不是一个对象类型，将抛出一个 `TypeError` 异常。在 ES6 中， non-object 参数将被视为一个冻结的普通对象，因此会返回 `true` 。

```javascript
    Object.isFrozen(1);
    // TypeError: 1 is not an object (ES5 code)

    Object.isFrozen(1);
    // true                          (ES6 code)
```

## 实例

```javascript
    // 一个对象默认是可扩展的,所以它也是非冻结的.
    console.log(Object.isFrozen({})); // false

    // 一个不可扩展的空对象同时也是一个冻结对象.
    var vacuouslyFrozen = Object.preventExtensions({});
    console.log(Object.isFrozen(vacuouslyFrozen)); // true

    // 一个非空对象默认也是非冻结的.
    var oneProp = { p: 42 };
    console.log(Object.isFrozen(oneProp)); // false

    // 让这个对象变的不可扩展,并不意味着这个对象变成了冻结对象,
    // 因为p属性仍然是可以配置的(而且可写的).
    Object.preventExtensions(oneProp);
    console.log(Object.isFrozen(oneProp)); // false

    // ...如果删除了这个属性,则它会成为一个冻结对象.
    delete oneProp.p;
    console.log(Object.isFrozen(oneProp)); // true

    // 一个不可扩展的对象,拥有一个不可写但可配置的属性,则它仍然是非冻结的.
    var nonWritable = { e: "plep" };
    Object.preventExtensions(nonWritable);
    Object.defineProperty(nonWritable, "e", { writable: false }); // 变得不可写
    console.log(Object.isFrozen(nonWritable)); // false

    // 把这个属性改为不可配置,会让这个对象成为冻结对象.
    Object.defineProperty(nonWritable, "e", { configurable: false }); // 变得不可配置
    console.log(Object.isFrozen(nonWritable)); // true

    // 一个不可扩展的对象,拥有一个不可配置但可写的属性,则它仍然是非冻结的.
    var nonConfigurable = { release: "the kraken!" };
    Object.preventExtensions(nonConfigurable);
    Object.defineProperty(nonConfigurable, "release", { configurable: false });
    console.log(Object.isFrozen(nonConfigurable)); // false

    // 把这个属性改为不可写,会让这个对象成为冻结对象.
    Object.defineProperty(nonConfigurable, "release", { writable: false });
    console.log(Object.isFrozen(nonConfigurable)); // true

    // 一个不可扩展的对象,只拥有一个访问器属性,则它仍然是非冻结的.
    var accessor = { get food() { return "yum"; } };
    Object.preventExtensions(accessor);
    console.log(Object.isFrozen(accessor)); // false

    // ...但把这个属性改为不可配置,会让这个对象成为冻结对象.
    Object.defineProperty(accessor, "food", { configurable: false });
    console.log(Object.isFrozen(accessor)); // true

    // 使用Object.freeze是冻结一个对象最方便的方法.
    var frozen = { 'a': 81 };
    console.log(Object.isFrozen(frozen)); // false
    Object.freeze(frozen);
    console.log(Object.isFrozen(frozen)); // true

    // 一个冻结对象也是一个密封对象.
    console.log(Object.isSealed(frozen)); // true

    // 当然,更是一个不可扩展的对象.
    console.log(Object.isExtensible(frozen)); // false
```

## 更多

*   [Object.isFrozen()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Object/isFrozen)