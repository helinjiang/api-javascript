`unescape()` 函数可对通过 `escape()` 编码的字符串进行解码。

> *[warning]* ：ECMAScript v3 已从标准中删除了 `unescape()` 函数，并反对使用它，因此应该用 `decodeURI()` 和 `decodeURIComponent()` 取而代之。

## 定义和用法

### 语法

`unescape(string)`

| 参数 | 描述 |
| --- | --- |
| string | 必需。要解码或反转义的字符串。 |

### 返回值

`string` 被解码后的一个副本。

### 说明

该函数的工作原理是这样的：通过找到形式为 `%xx` 和 `%uxxxx` 的字符序列（x 表示十六进制的数字），用 Unicode 字符 `\u00xx` 和 `\uxxxx` 替换这样的字符序列进行解码。

## 实例

``` javascript

    var test1 = escape("何林江@web前端：http://www.helinjiang.com");
    console.log(test1); //  %u4F55%u6797%u6C5F@web%u524D%u7AEF%uFF1Ahttp%3A//www.helinjiang.com

    var test2 = unescape(test1);
    console.log(test2); //  "何林江@web前端：http://www.helinjiang.com"

```

## 更多

*   [unescape()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/unescape)
*   [JavaScript unescape() 函数](http://www.w3school.com.cn/jsref/jsref_unescape.asp)