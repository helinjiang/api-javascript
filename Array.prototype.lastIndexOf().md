`Array.prototype.lastIndexOf()` 方法返回根据给定元素找到的最后一个索引值，否则返回 `-1`。以 `formIndex` 处开始，从数组的后面向前依次逆序查找。

## 定义和用法

### 语法

`arrayObject.lastIndexOf(searchElement[, fromIndex = arrayObject.length - 1])`

| 参数 | 描述 |
| --- | --- |
| _searchElement_ | 位于数组中的元素 |
| _fromIndex_ | 起始查找点，默认值: `arrayObject.length - 1` |

### 返回值

返回根据给定元素找到的最后一个索引值。

### 说明

以 `formIndex` 处开始，从数组的后面向前依次逆序查找。

*   `formIndex` 默认值: `arrayObject.length - 1` ，即整个数组都被查找。
*   如果 `formIndex` 大于或等于数组长度，则整个数组都被查找。
*   如果 `formIndex` 是一个负值，则将其视为数组末尾向前的偏移，即 `-1` 表示从最后一个元素开始查找，`-2` 表示从倒数第二个元素开始查找 ，以此类推。
*   如果 `formIndex` 是一个负值，仍然从后向前逆序查询数组。
*   如果 `formIndex` 是一个负值，且其绝对值大于数组长度，则方法返回 -1，即数组不会被查找。

`lastIndexOf` 使用严格相等(strict equality ，即 `===` )比较 `searchElement` 和数组中的元素。

## 实例

``` javascript

    var array = [2, 5, 9, 2];
    var index = array.lastIndexOf(2); // 3
    index = array.lastIndexOf(7); // -1
    index = array.lastIndexOf(2, 3); // 3
    index = array.lastIndexOf(2, 2); // 0
    index = array.lastIndexOf(2, -2); // 0
    index = array.lastIndexOf(2, -1); // 3

```

## 更多

*   [Array.prototype.lastIndexOf()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/lastIndexOf)