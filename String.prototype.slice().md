`String.prototype.slice()` 方法提取字符串中的一部分，并返回这个新的字符串。

## 定义和用法

### 语法

`stringObject.slice(beginSlice[, endSlice])`

| 参数 | 描述 |
| --- | --- |
| _beginSlice_ | 从该索引（以 `0` 为基数）处开始提取原字符串中的字符。如果该参数为负数，则它将被当作 `stringObject.length + beginSlice` ，表示从原字符串中的倒数第几个字符开始抽取。例如：`slice(-2)`表示抽取了原字符串中的倒数第二个字符到最后一个字符(包含最后一个字符)。 |
| _endSlice_ | 在该索引（以 `0` 为基数）处结束提取字符串。如果省略该参数，`slice`会一直提取到字符串末尾。如果该参数为负数，则它将被当作 `stringObject.length + endSlice` ，表示在原字符串中的倒数第几个字符结束抽取。`slice(-2, -1)` 表示抽取了原字符串中的倒数第二个字符到最后一个字符（不包含最后一个字符，也就是只有倒数第二个字符)。 |

### 返回值

一个新的字符串。包括字符串 `stringObject` 从 `beginSlice` 开始（包括 `beginSlice`）到 `endSlice` 结束（不包括 `endSlice`）为止的所有字符，即`[beginSlice, endSlice)`。

### 说明

`String` 对象的方法 `slice()`、`substring()` 和 `substr()` 都可返回字符串的指定部分。`slice()` 比 `substring()` 要灵活一些，因为它允许使用负数作为参数。`slice()` 与 `substr()` 有所不同，因为它用两个字符的位置来指定子串，而 `substr()` 则用字符位置和长度来指定子串。

还要注意的是，`String.slice()` 与 `Array.slice()` 相似。

> 如果 `endSlice <= beginSlice` （若某一个值为负数，则使用 `stringObject.length` 将其转换一次），则结果将返回空字符串 `""` ，而不是 `undefined`。

## 实例

```javascript
    var str = "Hello happy world!";
    console.log(str.slice(6)) // "happy world!"，提取从位置 6 开始的所有字符
    console.log(str.slice(6, 11)) // "happy"，提取位置 6~11 的所有字符,注意：happy中‘y’的下标是10
    console.log(str.slice(6, -1)) // "happy world"，这里的-1相当于str.length-1

    console.log(str.slice(6, 5)) //  ""
    console.log(str.slice(6, 6)) //  ""
    console.log(str.slice(6, -6666)) //  ""
```

## 更多

*   [String.prototype.slice()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/slice)
*   [JavaScript slice() 方法](http://www.w3school.com.cn/jsref/jsref_slice_string.asp)