`Object.preventExtensions()` 方法让一个对象变的不可扩展，也就是永远不能再添加新的属性，并返回这个变得不可扩展的对象。

## 定义和用法

### 语法

`Object.preventExtensions(obj)`

| 参数 | 描述 |
| --- | --- |
| _obj_ | 将要变得不可扩展的对象 |

### 返回值

变得不可扩展的对象。

### 说明

不可扩展的对象是指那些不能添加新的属性的对象。

*   如果一个对象可以添加新的属性，则这个对象是可扩展的。
*   不可扩展的对象的属性通常仍然可以被删除。
*   尝试给一个不可扩展对象添加新属性的操作将会失败，不过可能是静默失败，也可能会抛出 `TypeError` 异常（严格模式）。
*   `Object.preventExtensions()` 只能阻止一个对象不能再添加新的自身属性，仍然可以为该对象的原型添加属性。
*   在 ECMAScript 5 中可扩展的对象可以变得不可扩展，但反过来不行。

## 实例

```javascript

    // Object.preventExtensions将原对象变的不可扩展,并且返回原对象.
    var obj = {};
    var obj2 = Object.preventExtensions(obj);
    console.log(obj === obj2); // true

    // 字面量方式定义的对象默认是可扩展的.
    var empty = {};
    console.log(Object.isExtensible(empty)); // true

    // ...但可以改变.
    Object.preventExtensions(empty);
    console.log(Object.isExtensible(empty) ); // false

    // 使用Object.defineProperty方法为一个不可扩展的对象添加新属性会抛出异常.
    var nonExtensible = { removable: true };
    Object.preventExtensions(nonExtensible);
    Object.defineProperty(nonExtensible, "new", { value: 8675309 }); // 抛出TypeError异常

    // 在严格模式中,为一个不可扩展对象的新属性赋值会抛出TypeError异常.
    function fail()
    {
      "use strict";
      nonExtensible.newProperty = "FAIL"; // throws a TypeError
    }
    fail();

    // 一个不可扩展对象的原型是不可更改的,__proto__是个非标准魔法属性,可以更改一个对象的原型.
    var fixed = Object.preventExtensions({});
    fixed.__proto__ = { oh: "hai" }; // 抛出TypeError异常

```

## 更多

*   [Object.preventExtensions()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Object/preventExtensions)