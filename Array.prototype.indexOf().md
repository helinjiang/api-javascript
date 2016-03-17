`Array.prototype.indexOf()` 方法返回根据给定元素找到的第一个索引值，否则返回 `-1`。以 `formIndex` 处开始，从数组的前面向后依次顺序查找。

## 定义和用法

### 语法

`arrayObject.indexOf(searchElement[, fromIndex = 0])`

| 参数 | 描述 |
| --- | --- |
| _searchElement_ | 位于数组中的元素 |
| _fromIndex_ | 起始查找点，默认值: `0` |

### 返回值

返回根据给定元素找到的第一个索引值。

### 说明

以 `formIndex` 处开始，从数组的前面向后依次顺序查找。

*   `formIndex`默认值: `0` ，即整个数组都被查找。
*   如果 `formIndex` 大于或等于数组长度，则停止查找并返回 `-1`。
*   如果 `formIndex` 是一个负值，则将其视为数组末尾向前的偏移，即 `-1` 表示从最后一个元素开始查找，`-2` 表示从倒数第二个元素开始查找 ，以此类推。
*   如果 `formIndex` 是一个负值，仍然从前向后顺序查询数组。
*   如果 `formIndex` 是一个负值，且其绝对值大于数组长度，则整个数组都将会被查询。

`indexOf` 使用严格相等(strict equality ，即 `===` )比较 `searchElement` 和数组中的元素。

## 实例

```javascript

    var array = [2, 5, 9];
    array.indexOf(2); // 0
    array.indexOf(7); // -1
    array.indexOf(9, 2); // 2
    array.indexOf(2, -1); // -1
    array.indexOf(2, -3); // 0

```

## 更多

*   [Array.prototype.indexOf()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf)