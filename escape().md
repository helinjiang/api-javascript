`escape()` 函数可对字符串进行编码，这样就可以在所有的计算机上读取该字符串。

> *[warning]* ：ECMAScript v3 反对使用该方法，建议使用 `decodeURI()` 和 `decodeURIComponent()` 替代它。

## 定义和用法

### 语法

`escape(string)`

| 参数 | 描述 |
| --- | --- |
| _string_ | 必需。要被转义或编码的字符串。 |

### 返回值

已编码的 `string` 的副本。其中某些字符被替换成了十六进制的转义序列。

### 说明

该方法不会对 `ASCII` 字母和数字进行编码，也不会对这些 `ASCII` 标点符号进行编码： `*` `@` `-` `_` `+` `.` `/` 。

其他所有的字符都会被转义序列替换。

可以使用 [`unescape()`](global-unescape) 对 `escape()` 编码的字符串进行解码。

## 实例

``` javascript

    console.log(escape("http://www.helinjiang.com")); //=> http%3A//www.helinjiang.com
    console.log(escape("*@-_+./")); //=>  *@-_+./

```

## 更多

*   [escape()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/escape)
*   [JavaScript escape() 函数](http://www.w3school.com.cn/jsref/jsref_escape.asp)