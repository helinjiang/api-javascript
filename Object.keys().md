`Object.keys()` 方法返回一个由指定对象的所有可枚举的自身属性的属性名组成的数组。

## 定义和用法

### 语法

`Object.keys(obj)`

| 参数 | 描述 |
| --- | --- |
| _obj_ | 指定的对象 |

### 返回值

指定对象的所有自身属性的属性名（包括不可枚举属性）组成的数组。

### 说明

`Object.keys` 返回一个数组，该数组对元素是 `obj` 自身拥有的可枚举属性名称字符串。 数组中枚举属性的顺序与通过 `for...in` 循环迭代该对象属性时一致。

该方法不获取原型链上的属性。

你也可以用 `for...in` 循环来获取可枚举属性，不过 `for...in` 还会获取到原型链上的可枚举属性，需要配合使用 `Object.prototype.hasOwnProperty()` 方法过滤掉。

如果你想获取一个对象的所有属性,，甚至包括不可枚举的属性，可用 `Object.getOwnPropertyNames()` 方法。

### 兼容性

在 ES5 中，如果参数不是一个对象类型，将抛出一个 `TypeError` 异常。在 ES6 中， non-object 参数被强制转换为 object 。

``` javascript

    Object.keys("foo");
    // TypeError: "foo" is not an object (ES5 code)

    Object.keys("foo");
    // ["0", "1", "2"]                   (ES6 code)

```

## 实例

``` javascript

    var arr = ['a', 'b', 'c'];
    console.log(Object.keys(arr)); // ["0", "1", "2"]

    // array like object
    var obj = { 0: 'a', 1: 'b', 2: 'c' };
    console.log(Object.keys(obj)); // ["0", "1", "2"]

    // array like object with random key ordering
    var an_obj = { 100: 'a', 2: 'b', 7: 'c' };
    console.log(Object.keys(an_obj)); // ["2", "7", "100"]

    // getFoo is property which isn't enumerable
    var my_obj = Object.create({}, { getFoo: { value: function() { return this.foo; } } });
    my_obj.foo = 1;

    console.log(Object.keys(my_obj)); // ["foo"]

```

## 更多

*   [Object.keys()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Object/keys)