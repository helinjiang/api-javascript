`String.prototype.split()` 方法用于把一个字符串分割成一个字符串数组。

## 定义和用法

### 语法

`stringObject.split([separator][, limit])`

| 参数 | 描述 |
| --- | --- |
| _separator_ | 指定用来分割字符串的字符（串）。`separator` 可以是一个字符串或正则表达式。 |
| _limit_ | 一个整数，限定返回的分割片段数量。`split` 方法仍然分割每一个匹配的 `separator`，但是返回的数组只会截取最多 `limit` 个元素。 |

### 返回值

一个字符串数组。该数组是通过在 `separator` 指定的边界处将字符串 `stringObject` 分割成子串创建的。返回的数组中的字串不包括 `separator` 自身。但是，如果 `separator` 是包含子表达式的正则表达式，那么返回的数组中包括与这些子表达式匹配的字串（但不包括与整个正则表达式匹配的文本）。

### 说明

当找到一个 `seperator` 时，`separator` 会从字符串中被移除，返回存进一个数组当中的子字符串。

*   如果忽略 `separator`，则返回的数组包含一个由原字符串组成的元素。例如 `"abc".split()` 会返回 `["abc"]` ，`"".split()` 会返回 `[""]` ，该数组长度为 `1`。
*   如果 `separator` 是一个空字符串，则 `stringObject` 将会转换成一个由原字符串中字符组成的数组。例如 `"abc".split("")` 会返回 `["a", "b", "c"]` 。但 `"".split("")` 将返回 `[]` ，该数组长度为 `0`。
*   如果 `separator` 是一个正则表达式，且包含捕获括号（capturing parentheses），则每次匹配到 `separator` 时，捕获括号匹配的结果将会插入到返回的数组中。然而，不是所有浏览器都支持该特性。

`String.prototype.split()` 执行的操作与 [`Array.prototype.join`](array-prototype-join.html) 执行的操作是相反的，前者是将字符串处理后返回数组，而后者是将数组处理后返回字符串。

## 实例

```javascript

    var str = "How are you?";
    console.log(str.split()); // ["How are you?"]
    console.log(str.split("")); // ["H", "o", "w", " ", "a", "r", "e", " ", "y", "o", "u", "?"] 
    console.log(str.split(" ")); // ["How", "are", "you?"]
    console.log(str.split(/\s+/)); // ["How", "are", "you?"]，正则表达式
    console.log(str.split(" ", 2)); // ["How", "are"]，截取前2个字符串

```

## 更多

*   [String.prototype.split()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/split)
*   [JavaScript split() 方法](http://www.w3school.com.cn/jsref/jsref_split.asp)