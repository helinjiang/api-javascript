`Array.prototype.reduce()` 方法接收一个函数作为累加器（accumulator），数组中的每个值按顺序（从头到尾）开始缩减，最终为一个值。

> 该方法不会改变原数组。

## 定义和用法

### 语法

`arrayObject.reduce(callback, [initialValue])`

| 参数 | 描述 |
| --- | --- |
| _callback_ | 执行数组中每个值的函数

<dl class="dl-horizontal">

<dt>previousValue</dt>

<dd>`callback` 的第一个参数，上一次调用回调返回的值，或者是提供的初始值（`initialValue`）。</dd>

<dt>currentValue</dt>

<dd>`callback` 的第二个参数，数组中当前被传递的元素。</dd>

<dt>index</dt>

<dd>`callback` 的第三个参数，数组中当前被传递的元素的索引。</dd>

<dt>array</dt>

<dd>`callback` 的第四个参数，调用 `reduce` 方法的原数组。</dd>

</dl>

 |
| _initialValue_ | 作为第一次调用 `callback` 的第一个参数。 |

### 返回值

返回一个新的数组。

### 说明

`reduce` 方法会给原数组中的每个元素都按顺序调用一次 `callback` 函数。

*   `callback` 函数只会在有值的索引上被调用；那些从来没被赋过值或者使用 `delete` 删除的索引则不会被调用。
*   `callback` 函数会被自动传入四个参数：初始值（或者上一次回调函数的返回值），数组元素，元素索引，原数组本身。

关于 `callback` 函数：

*   第一次执行时，`previousValue` 和 `currentValue` 可以是一个值。
*   如果 `initialValue` 在调用 `reduce` 时被提供，那么第一个 `previousValue` 等于 `initialValue` ，并且`currentValue` 等于数组中的第一个值。
*   如果 `initialValue` 未被提供，那么`previousValue` 等于数组中的第一个值，`currentValue` 等于数组中的第二个值。
*   如果数组为空，并且没有提供`initialValue`， 会抛出 `TypeError` 。
*   如果数组仅有一个元素，并且没有提供`initialValue`， 或者有提供 `initialValue` 但是数组为空，那么此唯一值将被返回并且 `callback` 不会被执行。

## 实例

### 例子 1：将数组所有项相加

```javascript

    var total = [0, 1, 2, 3].reduce(function(a, b) {
        return a + b;
    });
    console.log(total); // 6

```

### 例子 2：数组扁平化

```javascript

    var flattened = [[0, 1], [2, 3], [4, 5]].reduce(function(a, b) {
        return a.concat(b);
    });
    console.log(flattened); // [0, 1, 2, 3, 4, 5]

```

## 更多

*   [Array.prototype.reduce()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce)