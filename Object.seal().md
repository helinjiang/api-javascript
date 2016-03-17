`Object.seal()` 方法可以密封一个对象，返回被密封之后的对象。

## 定义和用法

### 语法

`Object.seal(obj)`

| 参数 | 描述 |
| --- | --- |
| _obj_ | 将要被密封的对象 |

### 返回值

被密封之后的对象。

### 说明

密封对象是指那些不能添加新的属性，不能删除已有属性，以及不能修改已有属性的可枚举性、可配置性、可写性，但可能可以修改已有属性的值的对象。

*   密封一个对象会让这个对象变的不能添加新属性，且所有已有属性会变的不可配置。
*   属性不可配置的效果就是属性变的不可删除，以及一个数据属性不能被重新定义成为访问器属性，或者反之。但属性的值仍然可以修改。
*   尝试删除一个密封对象的属性或者将某个密封对象的属性从数据属性转换成访问器属性，结果会静默失败或抛出 `TypeError` 异常（严格模式）。
*   不会影响从原型链上继承的属性。

## 实例

```javascript
    var obj = {
        prop: function() {},
        foo: "bar"
    };

    // 可以添加新的属性,已有属性的值可以修改,可以删除
    obj.foo = "baz";
    obj.lumpy = "woof";
    delete obj.prop;

    var o = Object.seal(obj);

    console.log(o === obj); // true
    console.log(Object.isSealed(obj)); // true

    // 仍然可以修改密封对象上的属性的值.
    obj.foo = "quux";

    // 但你不能把一个数据属性重定义成访问器属性.
    Object.defineProperty(obj, "foo", {
        get: function() {
            return "g";
        }
    }); // 抛出TypeError异常

    // 现在,任何属性值以外的修改操作都会失败.
    obj.quaxxor = "the friendly duck"; // 静默失败,新属性没有成功添加
    delete obj.foo; // 静默失败,属性没有删除成功

    // ...在严格模式中,会抛出TypeError异常
    function fail() {
        "use strict";
        delete obj.foo; // 抛出TypeError异常
        obj.sparky = "arf"; // 抛出TypeError异常
    }
    fail();

    // 使用Object.defineProperty方法同样会抛出异常
    Object.defineProperty(obj, "ohai", {
        value: 17
    }); // 抛出TypeError异常

    Object.defineProperty(obj, "foo", {
        value: "eit"
    }); // 成功将原有值改变
```

## 更多

*   [Object.seal()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Object/seal)