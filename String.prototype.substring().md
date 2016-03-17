`String.prototype.substring()` 方法返回字符串两个索引之间（或到字符串末尾）的子串。

## 定义和用法

### 语法

`stringObject.substring(start[, stop])`

| 参数 | 描述 |
| --- | --- |
| _start_ | 一个 `0` 到字符串长度之间的整数。 |
| _stop_ | 

可选。一个 `0` 到字符串长度之间的整数。如果省略该参数，那么返回的子串会一直到字符串的结尾。

 |

### 返回值

一个新的字符串，该字符串值包含 `stringObject` 的一个子字符串，其内容是从 `start` 处到 `stop-1` 处的所有字符，其长度为 `stop` 减 `start`。

### 说明

`substring()` 方法返回的子串包括 `start` 处的字符，但不包括 `stop` 处的字符，即`[start, stop)`。

*   如果 `start` 等于 `stop`，`substring` 方法返回一个空字符串。
*   如果 `start` 大于 `stop` 大，那么该方法在提取子串之前会先交换这两个参数。
*   如果省略 `stop`，`substring` 方法提取字符一直到字符串末尾。
*   如果任一参数小于 `0` 或为 `NaN`，则被当作 `0`。
*   如果任一参数大于 `stringObject.length`，则被当作 `stringObject.length`。

> *[warning]* ：与 [`slice()`](string-protoype.slice.html) 和 [`substr()`](string-protoype.substr.html) 方法不同的是，`substring()` 不接受负的参数，如果为负数或者为无法最终转换成正整数的值，则返回原字符串。如果`start`超过字符串最大值，则返回空字符串。

## 实例

``` javascript

    var str = "Hello world!";
    console.log(str.substring(1)); // "ello world! "
    console.log(str.substring(1, 7)); // "ello w"
    console.log(str.substring(7, 1)); // "ello w"，如果start>stop，则会交换这两个参数
    console.log(str.substring(-1)); // "Hello world!"，如果为负数则返回原字符串
    console.log(str.substring("notcerrect")); // "Hello world!"，如果无法转换成正整数，则返回原字符串
    console.log(str.substring(1111)); // ""，如果start超出范围，则返回空字符串（length=0）
    console.log(str.substring(1, 1111)); // "ello world! "，如果stop超出范围，则返回的字符串会一直到字符串的结尾

```

## 更多

*   [String.prototype.substring()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/substring)
*   [JavaScript substring() 方法](http://www.w3school.com.cn/jsref/jsref_substring.asp)