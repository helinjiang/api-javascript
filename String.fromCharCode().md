`String.fromCharCode()` 静态方法根据指定的 `Unicode` 编码中的序号值来返回一个字符串。

## 定义和用法

### 语法

`String.fromCharCode(num1, ..., numN) `

| 参数 | 描述 |
| --- | --- |
| num1, ..., numN | 一组序列数字，表示 `Unicode` 值。(范围 `0` ~ `65535` ) |

### 返回

字符串

### 说明

该方法返回一个字符串，而不是一个 `String` 对象。

该方法是 `String` 的静态方法，因此它的语法应该是 `String.fromCharCode()`，而不是 `myStringObject.fromCharCode()`。

要获取某个字符的Unicode编码，可以使用[`charCodeAt()`](string-charcodeat.html)方法。

> 字符的 `Unicode` 编码一般很少使用，但在某些场景下还是很有一定价值的。比如某一段敏感信息（例如关键算法）不想明文在js中定义，则使用`charCodeAt()`都转义为 `Unicode` 编码，然后使用`fromCharCode()`解码，就可以一定意义上达到加密的效果，尽管加密效果很容易破解，但聊胜于无。

## 实例

```javascript

    console.log(String.fromCharCode(72, 69, 76, 76, 79))  //=> HELLO
    console.log(String.fromCharCode(65, 66, 67))  //=> ABC
    console.log(String.fromCharCode("65"))  //=> A

```

## 更多

*   [String.fromCharCode()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/fromCharCode)
*   [JavaScript fromCharCode() 方法](http://www.w3school.com.cn/jsref/jsref_fromCharCode.asp)