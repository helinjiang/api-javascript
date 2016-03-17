`String.prototype.charCodeAt()` 方法可返回指定位置的字符的 Unicode 编码。

## 定义和用法

### 语法

`stringObject.charCodeAt(index)`

| 参数 | 描述 |
| --- | --- |
| _index_ | 字符在字符串中的下标，区间范围`[0, stringObject.length - 1]`中的一个整数。 |

### 返回

返回`stringObjedt`中指定字符的 Unicode ，范围（`0` - `65535` 之间的整数）。

### 说明

字符串中第一个字符的下标是 `0`。如果参数 `index` 不在 `0` 与 `string.length - 1` 之间（即区间范围为：`[0, string.length - 1]`），该方法将返回`NaN`。

方法 `charCodeAt()` 与 [`String.prototype.charAt()`](string-prototype-charat.html)方法执行的操作相似，只不过前者返回的是位于指定位置的字符的编码，而后者返回的是字符子串。

## 实例

```javascript

var str = "AB Hello world!"
console.log(str.charCodeAt(0)); // 65
console.log(str.charCodeAt(-1)); // NaN，index 是负数，或大于等于字符串的长度，则返回 NaN
console.log(str.charCodeAt()); // 65，如果不传参数，则等效于str.charCodeAt(0)，因为空字符串最终被强制转换为0
console.log(str.charCodeAt("abc")); // 65，对于无法强制转换成数字的字符串，也当作0处理

```

## 更多

*   [String.prototype.charCodeAt()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/charCodeAt)
*   [JavaScript charCodeAt() 方法](http://www.w3school.com.cn/jsref/jsref_charCodeAt.asp)