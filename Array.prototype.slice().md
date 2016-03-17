`Array.prototype.slice()` 方法把数组中一部分的浅复制（shallow copy）存入一个新的数组对象中，并返回这个新的数组。

> 该方法不会改变原数组，而是返回一个子数组。

## 定义和用法

### 语法

`arrayObject.slice(begin[, end])`

| 参数 | 描述 |
| --- | --- |
| _begin_ | 从该索引处开始提取原数组中的元素（从`0`开始）。如果该参数为负数，则表示从原数组中的倒数第几个元素开始提取，也就是说，`-1` 指最后一个元素，`-2` 指倒数第二个元素，以此类推。如果省略该参数，则从索引`0`开始。 |
| _end_ | 在该索引处结束提取原数组中的元素（从`0`开始）。如果该参数为负数，则表示从原数组中的倒数第几个元素结束提取，也就是说，`-1` 指最后一个元素，`-2` 指倒数第二个元素，以此类推。如果省略该参数，则一直提取到原数组末尾。 |

### 返回值

返回一个新的数组，包含从 `begin` 到 `end` （不包括`end`）的 `arrayObject` 中的元素。

### 说明

如果想删除数组中的一段元素，应该使用方法 `Array.prototype.splice()`。

您可使用负值从数组的尾部选取元素。

如果在计算之后 `begin` 元素位置 在 `end` 元素位置之后，则返回空数组。

`slice()` 不修改原数组，只会返回一个包含了原数组中提取的部分元素的一个新数组。原数组的元素会按照下述规则被拷贝（"一级深拷贝"[one level deep]规则）：

*   字符串和数字(是原始值，而不是包装原始值的 `String` 和 `Number` 对象)：`slice()` 方法会复制字符串和数字的值放到新数组里。在一个数组里修改这些字符串或数字，不会影响另一个数组。
*   对象引用(非对象直接量)：`slice()`方法会复制对象引用放到新的数组里。原数组和新数组中的对象引用都指向同一个实际的对象，所以，当实际的对象被修改时，两个数组也同时会被修改。

如果向两个数组任意一个中添加了新元素，则另一个不会受到影响（因为它们是相互独立的）。

## 实例

```javascript

    var arr = ["George", "John", "Thomas"];
    console.log(arr); // ["George", "John", "Thomas"] 
    console.log(arr.slice(1)); // ["John", "Thomas"] ，返回一个新的数组
    console.log(arr); // ["James", "George", "John", "Thomas"]，注意原数组未有变化

    var arr2 = ["a", "b", "c", "d", "e", "f"];
    console.log(arr2); // ["a", "b", "c", "d", "e", "f"]  
    console.log(arr2.slice(2, 4)); // ["c", "d"] ，返回一个新的数组，注意不包含end那个元素
    console.log(arr2.slice(-5, -2)); // ["b", "c", "d"] ，返回一个新的数组，注意如果是负数则从末尾开始算位置
    console.log(arr2.slice(4, 2)); // [] ，如果start>end，则返回空数组
    console.log(arr2.slice(4, 4)); // [] ，如果start=end，则返回空数组
    console.log(arr2.slice(-5, 5)); // ["b", "c", "d", "e"] ，返回一个新的数组，可以混合使用
    console.log(arr2); // ["a", "b", "c", "d", "e", "f"] ，注意原数组未有变化

```

## 更多

*   [Array.prototype.slice()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/slice)
*   [JavaScript slice() 方法](http://www.w3school.com.cn/jsref/jsref_slice_array.asp)