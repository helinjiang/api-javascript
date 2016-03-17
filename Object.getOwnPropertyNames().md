`Object.getOwnPropertyNames()` 方法返回一个由指定对象的所有自身属性的属性名（包括不可枚举属性）组成的数组。

## 定义和用法

### 语法

`Object.getOwnPropertyNames(obj)`

| 参数 | 描述 |
| --- | --- |
| _obj_ | 指定的对象 |

### 返回值

指定对象的所有自身属性的属性名（包括不可枚举属性）组成的数组。

### 说明

`Object.getOwnPropertyNames` 返回一个数组，该数组对元素是 `obj` 自身拥有的可枚举或不可枚举属性名称字符串。 数组中枚举属性的顺序与通过 `for...in` 循环（或 `Object.keys()`）迭代该对象属性时一致。 数组中不可枚举属性的顺序未定义。

该方法不获取原型链上的属性。

如果你仅需要获取到可枚举属性，可用 `Object.keys()` 或用 `for...in` 循环（还会获取到原型链上的可枚举属性，不过可以使用 `Object.prototype.hasOwnProperty()` 方法过滤掉）。

### 兼容性

在 ES5 中，如果参数不是一个对象类型，将抛出一个 `TypeError` 异常。在 ES6 中， non-object 参数被强制转换为 object 。

``` javascript

    Object.getOwnPropertyNames('foo');
    // TypeError: "foo" is not an object (ES5 code)

    Object.getOwnPropertyNames('foo');
    // ['length', '0', '1', '2']  (ES6 code)

```

## 实例

### 例子 1

``` javascript

    var arr = ["a", "b", "c"];
    console.log(Object.getOwnPropertyNames(arr)); // ["0", "1", "2", "length"]，不保证依据顺序

    // 类数组对象
    var obj = {
        0: "a",
        1: "b",
        2: "c"
    };
    console.log(Object.getOwnPropertyNames(obj)); // ["0", "1", "2"]，不保证依据顺序

    // 使用Array.forEach输出属性名和属性值
    Object.getOwnPropertyNames(obj).forEach(function(val, idx, array) {
        console.log(val + " -> " + obj[val]);
    });
    // 输出，不保证依据顺序
    // 0 -> a
    // 1 -> b
    // 2 -> c

    //不可枚举属性
    var my_obj = Object.create({}, {
        getFoo: {
            value: function() {
                return this.foo;
            },
            enumerable: false
        }
    });
    my_obj.foo = 1;

    console.log(Object.getOwnPropertyNames(my_obj)); // ["getFoo", "foo"]，不保证依据顺序

```

### 例子 2：该方法不获取原型链上的属性

``` javascript

    function ParentClass() {}
    ParentClass.prototype.inheritedMethod = function() {};

    function ChildClass() {
        this.prop = 5;
        this.method = function() {};
    }

    ChildClass.prototype = new ParentClass();

    ChildClass.prototype.prototypeMethod = function() {};

    console.log(Object.getOwnPropertyNames(new ChildClass()) // ["prop", "method"])

```

### 例子 3：获取不可枚举的属性

``` javascript

    var target = myObject;
    var enum_and_nonenum = Object.getOwnPropertyNames(target);
    var enum_only = Object.keys(target);
    var nonenum_only = enum_and_nonenum.filter(function(key) {
        var indexInEnum = enum_only.indexOf(key);
        if (indexInEnum == -1) {
            // not found in enum_only keys mean the key is non-enumerable,
            // so return true so we keep this in the filter
            return true;
        } else {
            return false;
        }
    });

    console.log(nonenum_only);

```

## 更多

*   [Object.getOwnPropertyNames()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Object/getOwnPropertyNames)