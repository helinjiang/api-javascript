`Array.prototype.filter()` 方法使用指定的函数测试所有元素，并创建一个包含所有通过测试的元素的新数组。

> 该方法不会改变原数组，而会返回一个新数组。

## 定义和用法

### 语法

`arrayObject.filter(callback[, thisArg])`

| 参数 | 描述 |
| --- | --- |
| _callback_ | 用来测试数组的每个元素的函数

<dl class="dl-horizontal">

<dt>currentValue</dt>

<dd>`callback` 的第一个参数，数组中当前被传递的元素。</dd>

<dt>index</dt>

<dd>`callback` 的第二个参数，数组中当前被传递的元素的索引。</dd>

<dt>array</dt>

<dd>`callback` 的第三个参数，调用 `filter` 方法的原数组。</dd>

</dl>

 |
| _thisArg_ | 执行 `callback` 函数时 `this` 指向的对象 |

### 返回值

返回一个新的数组，且所有元素都满足 `callback` 条件。

### 说明

`filter` 方法会给原数组中的每个元素都按顺序调用一次 `callback` 函数，并且将执行的结果为“真值”（表示可转换为布尔值 `true` 的值）的元素组合起来形成一个新数组。

*   `callback` 函数只会在有值的索引上被调用；那些从来没被赋过值或者使用 `delete` 删除的索引则不会被调用。
*   那些没有通过 `callback` 测试的元素会被跳过，不会被包含在新数组中。
*   `callback` 函数会被自动传入三个参数：数组元素，元素索引，原数组本身。

如果 `thisArg` 参数有值，则每次 `callback` 函数被调用的时候，`this` 都会指向 `thisArg` 参数上的这个对象。如果省略了 `thisArg` 参数，或者赋值为 `null` 或 `undefined` ，则 `this` 指向全局对象 。

`filter` 不修改调用它的原数组本身（当然可以在 `callback` 执行时改变原数组）。

使用 `filter` 方法处理数组时，数组元素的范围是在 `callback` 方法第一次调用之前就已经确定了。在 `filter` 方法执行的过程中：原数组中新增加的元素将不会被 `callback` 访问到；若已经存在的元素被改变或删除了，则它们的传递到 `callback` 的值是 `filter` 方法遍历到它们的那一时刻的值；而被删除或从来未被赋值的元素将不会被访问到。

## 实例

### 例子 1：筛选排除掉所有的小值

下例使用 `filter` 创建了一个新数组，该数组的元素由原数组中值大于 `10` 的元素组成。

```javascript
    function isBigEnough(element) {
        return element >= 10;
    }

    var filtered = [12, 5, 8, 130, 44].filter(isBigEnough); // [12, 130, 44]
```

## 更多

*   [Array.prototype.filter()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)