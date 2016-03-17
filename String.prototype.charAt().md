`String.prototype.charAt()`方法可返回指定位置的字符。

## 定义和用法

### 语法

`stringObject.charAt(index)`

| 参数 | 描述 |
| --- | --- |
| _index_ | 字符在字符串中的下标，区间范围`[0, stringObject.length - 1]`中的一个整数。 |

### 返回值

返回`index`位置的指定的单个字符（长度为 `1` 的字符串）。

### 说明

字符串中第一个字符的下标是 `0`。如果参数 `index` 不在 `0` 与 `string.length - 1` 之间（即区间范围为：`[0, string.length - 1]`），该方法将返回一个空字符串，而不是`undefined`。

### 实例

```javascript

    var str = "hello world!";
    console.log(str.charAt(6)); // "w"
    console.log(str.charAt(str.length + 100)); // " "，超出范围则返回空字符串
    console.log(str.charAt()); // "h"，如果不传参数，则等效于str.charAt(0)，因为空字符串最终被强制转换为0

```

## 更多

*   [String.prototype.charAt()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/charAt)
*   [JavaScript charAt() 方法](http://www.w3school.com.cn/jsref/jsref_charAt.asp)