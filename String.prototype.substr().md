`String.prototype.substr()` 方法返回字符串中从指定位置开始的指定数量的字符。

## 定义和用法

### 语法

`stringObject.substr(start[, length])`

| 参数 | 描述 |
| --- | --- |
| _start_ | 开始提取字符的位置。如果该参数为负数，则它将被当作 `stringObject.length + start` ，表示从原字符串中的倒数第几个字符开始抽取。 |
| _length_ | 提取的字符数。如果省略了该参数，那么返回从 `stringObject` 的 `start` 位置到结尾的字串。 |

### 返回值

一个新的字符串，包含从 `stringObject` 的 `start`（包括 `start` 所指的字符） 处开始的 `length` 个字符。如果没有指定 `length`，那么返回的字符串包含从 `start` 到 `stringObject` 的结尾的字符。

### 说明

如果 `start` 为正值，且大于或等于字符串的长度，则返回一个空字符串。

如果 `start` 为负值，则它将被当作 `stringObject.length + start`。如果 `start` 为负值且 `abs(start)` 大于字符串的长度，则将使用 `0` 作为开始提取的索引。

如果 `length` 为 `0` 或负值，则 `substr` 方法返回一个空字符串。如果忽略 `length`，则将返回从 `stringObject` 的 `start` 位置到结尾的字串。

`substr()` 的参数指定的是子串的开始位置和长度，因此这与[`substring()`](string-prototype-substring.html) 和 [`slice()`](string-prototype-slice.html) 是有区别的。

> *[danger]* ：注意负的 `start` 参数在 IE8 及更早的版本中不支持，建议使用 `slice()` 或 `substring()` 来代替。

## 实例

``` javascript

    var str = "Hello world!";
    console.log(str.substr(1)); //=>"ello world!"
    console.log(str.substr(1, 7)); //=>"ello wo"

```

## 更多

*   [String.prototype.substring()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/substring)
*   [JavaScript substr() 方法](http://www.w3school.com.cn/jsref/jsref_substr.asp)