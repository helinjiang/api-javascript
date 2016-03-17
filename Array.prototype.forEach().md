`Array.prototype.forEach()` 方法让数组的每一项都执行一次给定的函数。

> 该方法不会改变原数组。

## 定义和用法

### 语法

`arrayObject.forEach(callback[, thisArg])`

| 参数 | 描述 |
| --- | --- |
| _callback_ | 原数组中的元素经过该方法后返回一个新的元素

<dl class="dl-horizontal">

<dt>currentValue</dt>

<dd>`callback` 的第一个参数，数组中当前被传递的元素。</dd>

<dt>index</dt>

<dd>`callback` 的第二个参数，数组中当前被传递的元素的索引。</dd>

<dt>array</dt>

<dd>`callback` 的第三个参数，调用 `forEach` 方法的原数组。</dd>

</dl>

 |
| _thisArg_ | 执行 `callback` 函数时 `this` 指向的对象 |

### 返回值

返回一个新的数组。

### 说明

`forEach` 方法会给原数组中的每个元素都按顺序调用一次 `callback` 函数。

*   `callback` 函数只会在有值的索引上被调用；那些从来没被赋过值或者使用 `delete` 删除的索引则不会被调用。
*   `callback` 函数会被自动传入三个参数：数组元素，元素索引，原数组本身。

如果 `thisArg` 参数有值，则每次 `callback` 函数被调用的时候，`this` 都会指向 `thisArg` 参数上的这个对象。如果省略了 `thisArg` 参数，或者赋值为 `null` 或 `undefined` ，则 `this` 指向全局对象 。

`forEach` 不修改调用它的原数组本身（当然可以在 `callback` 执行时改变原数组）。

使用 `forEach` 方法处理数组时，数组元素的范围是在 `callback` 方法第一次调用之前就已经确定了。在 `forEach` 方法执行的过程中：原数组中新增加的元素将不会被 `callback` 访问到；若已经存在的元素被改变或删除了，则它们的传递到 `callback` 的值是 `forEach` 方法遍历到它们的那一时刻的值；而被删除或从来未被赋值的元素将不会被访问到。

> *[warning]* ：注意：没有办法中止或者跳出 `forEach` 循环，除了抛出一个异常。如果你需要这样，使用 `forEach()` 方法是错误的，你可以用一个简单的循环作为替代。如果您正在测试一个数组里的元素是否符合某条件，且需要返回一个布尔值，那么可使用 [Array.prototype.every](array-every.html) 或 [Array.prototype.some](array-every.html)。

## 实例

### 例子 1：打印出数组的内容

下面的代码会为每一个数组元素输出一行记录：

``` javascript

    function logArrayElements(element, index, array) {
        console.log("a[" + index + "] = " + element);
    }

    [2, 5, 9].forEach(logArrayElements);
    // logs:
    // a[0] = 2
    // a[1] = 5
    // a[2] = 9

```

### 例子 2：对象复制函数

下面的代码会创建一个给定对象的副本。 创建对象的副本有不同的方法，以下是只是一种方法，并解释了Array.prototype.forEach() 是如何使用ECMAScript 5 Object.* 元属性（meta property ）函数工作的。

``` javascript

    function copy(o) {
        var copy = Object.create(Object.getPrototypeOf(o));
        var propNames = Object.getOwnPropertyNames(o);

        propNames.forEach(function(name) {
            var desc = Object.getOwnPropertyDescriptor(o, name);
            Object.defineProperty(copy, name, desc);
        });

        return copy;
    }

    var o1 = {
        a: 1,
        b: 2
    };

    var o2 = copy(o1); // o2 looks like o1 now

```

## 更多

*   [Array.prototype.forEach()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)