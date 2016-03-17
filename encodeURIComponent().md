`encodeURIComponent()` 函数可把字符串作为 `URI` 组件进行编码。

## 定义和用法

### 语法

`encodeURIComponent(URIstring)`

| 参数 | 描述 |
| --- | --- |
| _URIstring_ | 必需。一个字符串，含有 `URI` 组件或其他要编码的文本。 |

### 返回值

`URIstring` 的副本，其中的某些字符将被十六进制的转义序列进行替换。

### 说明

`encodeURIComponent` 方法会替换所有的字符，但不包括以下字符，即使它们具有适当的 utf-8 转义序列：

| 类型 | 包含 |
| --- | --- |
| 非转义的字符 | alphabetic（字母）, decimal digits（数字）, `-` `_` `.` `!` `~` `*` `'` `(` `)` |

`encodeURIComponent()` 函数 与 `encodeURI()` 函数的区别之处，前者假定它的参数是 `URI` 的一部分（比如协议、主机名、路径或查询字符串）。因此 `encodeURIComponent()` 函数将转义用于分隔 `URI` 各个部分的标点符号。

## 实例

``` javascript

    console.log(encodeURIComponent("http://www.helinjiang.com")); // http%3A%2F%2Fwww.helinjiang.com
    console.log(encodeURIComponent("http://www.helinjiang.com/Hello World/")); // http%3A%2F%2Fwww.helinjiang.com%2FHello%20World%2F
    console.log(encodeURIComponent(",/?:@&=+$#")); // %2C%2F%3F%3A%40%26%3D%2B%24%23
    console.log(encodeURIComponent("123abcABC*_-_.!~*'()")); // 123abcABC*_-_.!~*'(),数字字母,以及部分标点符号不会被编码。

```

## 更多

*   [encodeURIComponent()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/encodeURIComponent)
*   [JavaScript encodeURIComponent() 函数](http://www.w3school.com.cn/jsref/jsref_encodeURIComponent.asp)