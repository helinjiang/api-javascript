`Object.prototype.propertyIsEnumerable()` 方法用来判断某个对象是否含有指定的可枚举的自身属性。

## 定义和用法

### 语法

`obj.propertyIsEnumerable(prop)`

| 参数 | 描述 |
| --- | --- |
| _prop_ | 要检测的属性名称 |

### 返回值

`true`：可枚举的自身属性， `false`：不是可枚举的自身属性。

### 说明

所有继承了 `Object.prototype` 的对象都会从原型链上继承到 `propertyIsEnumerable` 方法，这个方法可以用来检测一个对象是否含有特定的可枚举的自身属性。

`for...in` 循环可遍历到所有可枚举的属性，除了包括可枚举的自身属性，也包括从原型链上继承的可枚举属性，只有可枚举的自身属性时 `Object.prototype` 才会返回 `true`。

如果对象没有指定的属性，`Object.prototype` 返回 `false`。

> `Object.prototype.hasOwnProperty()` 用来判断对象是否包含指定的自身属性，包括可枚举的和不可枚举的；而 `Object.prototype.propertyIsEnumerable()`只是判断对象是否包含指定的可枚举的自身属性，不包括不可枚举的自身属性。它们都只判断自身属性，而不考虑从原型链上继承的属性。

## 实例

### 例子 1：propertyIsEnumerable方法的基本用法

``` javascript

    var o = {};
    var a = [];
    o.prop = '我是个可枚举属性';
    a[0] = '我是个可枚举属性';

    o.propertyIsEnumerable('prop');   // 返回true
    a.propertyIsEnumerable(0);        // 返回true

```

### 例子 2：用户自定义对象和引擎内置对象

``` javascript

    var a = ['我是个可枚举属性'];

    a.propertyIsEnumerable(0);          // 返回true
    a.propertyIsEnumerable('length');   // 返回false

    Math.propertyIsEnumerable('random');   // 返回false
    this.propertyIsEnumerable('Math');     // 返回false

```

### 例子 3：自身属性和继承属性

``` javascript

    var a = [];
    a.propertyIsEnumerable('constructor'); // 返回false，constructor不是自身属性

    function firstConstructor() {
        this.property = 'is not enumerable';
    }

    firstConstructor.prototype.firstMethod = function() {};

    function secondConstructor() {
        this.method = function method() {
            return 'is enumerable';
        };
    }

    secondConstructor.prototype = new firstConstructor();
    secondConstructor.prototype.constructor = secondConstructor;

    var o = new secondConstructor();
    o.arbitraryProperty = 'is enumerable';

    o.propertyIsEnumerable('arbitraryProperty'); // 返回true
    o.propertyIsEnumerable('method'); // 返回true
    o.propertyIsEnumerable('property'); // 返回false，property是继承属性

    o.property = 'is enumerable';

    o.propertyIsEnumerable('property'); // 返回true

    // 继承属性都返回false
    o.propertyIsEnumerable('prototype'); // 返回false 
    o.propertyIsEnumerable('constructor'); // 返回false
    o.propertyIsEnumerable('firstMethod'); // 返回false

```

## 更多

*   [Object.prototype.propertyIsEnumerable()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Object/propertyIsEnumerable)