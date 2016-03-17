`Array.prototype.every()` 方法测试数组的所有元素是否都通过了指定函数的测试。

> 该方法不会改变原数组。

## 定义和用法

### 语法

`arrayObject.every(callback[, thisArg])`

| 参数 | 描述 |
| --- | --- |
| _callback_ | 用来测试每个元素的函数

<dl class="dl-horizontal">

<dt>currentValue</dt>

<dd>`callback` 的第一个参数，数组中当前被传递的元素。</dd>

<dt>index</dt>

<dd>`callback` 的第二个参数，数组中当前被传递的元素的索引。</dd>

<dt>array</dt>

<dd>`callback` 的第三个参数，调用 `map` 方法的原数组。</dd>

</dl>

 |
| _thisArg_ | 执行 `callback` 函数时 `this` 指向的对象 |

### 返回值

所有的元素都满足 `callback` 条件，则返回 `true`。

### 说明

`every` 方法会给原数组中的每个元素都调用一次 `callback` 函数，直到它找到一个使 `callback` 返回“假值”（表示可转换为布尔值 `false` 的值）的元素。

*   如果发现了一个这样的元素，`every` 方法将会立即返回 `false`。
*   否则，`callback` 调用每一个元素都返回 `true` 时，`every` 才会返回 `true`。
*   `callback` 只会为那些已经被赋值的索引调用，不会为那些被删除或从来没被赋值的索引调用。
*   `callback` 函数会被自动传入三个参数：数组元素，元素索引，原数组本身。

如果 `thisArg` 参数有值，则每次 `callback` 函数被调用的时候，`this` 都会指向 `thisArg` 参数上的这个对象。如果省略了 `thisArg` 参数，或者赋值为 `null` 或 `undefined` ，则 `this` 指向全局对象 。

`every` 不修改调用它的原数组本身（当然可以在 `callback` 执行时改变原数组）。

使用 `every` 方法处理数组时，数组元素的范围是在 `callback` 方法第一次调用之前就已经确定了。在 `every` 方法执行的过程中：原数组中新增加的元素将不会被 `callback` 访问到；若已经存在的元素被改变或删除了，则它们的传递到 `callback` 的值是 `every` 方法遍历到它们的那一时刻的值；而被删除或从来未被赋值的元素将不会被访问到。

## 实例

### 例子 1：检测所有数组元素的大小

下例检测数组中的所有元素是否都大于 `10`。

```javascript
    function isBigEnough(element, index, array) {
        return (element >= 10);
    }
    var passed1 = [12, 5, 8, 130, 44].every(isBigEnough); // false
    var passed2 = [12, 54, 18, 130, 44].every(isBigEnough); // true
```

## 更多

*   [Array.prototype.every()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/every)