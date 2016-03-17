`encodeURI()` 函数可把字符串作为 `URI` 进行编码。

## 定义和用法

### 语法

`encodeURI(URI)`

| 参数 | 描述 |
| --- | --- |
| _URI_ | 一个完整的 `URI` |

### 返回值

`URI` 的副本，其中的某些字符将被十六进制的转义序列进行替换。

### 说明

`encodeURI` 方法会替换所有的字符，但不包括以下字符，即使它们具有适当的 utf-8 转义序列：

| 类型 | 包含 |
| --- | --- |
| 保留字符 | `;` `,` `/` `?` `:` `@` `&` `=` `+` `$` |
| 非转义的字符 | alphabetic（字母）, decimal digits（数字）, `-` `_` `.` `!` `~` `*` `'` `(` `)` |
| Score | `#` |

如果 `URI` 组件中含有分隔符，比如 `?` 和 `#`，则应当使用 `encodeURIComponent()` 方法分别对各组件进行编码。

## 实例

```javascript 
    console.log(encodeURI("http://www.helinjiang.com")); // http://www.w3school.com.cn
    console.log(encodeURI("http://www.helinjiang.com/Hello World/")); // http://www.helinjiang.com/Hello%20World/
    console.log(encodeURI(",/?:@&=+$#")); // ,/?:@&=+$#
```

## 更多

*   [encodeURI()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/encodeURI)
*   [JavaScript encodeURI() 函数](http://www.w3school.com.cn/jsref/jsref_encodeuri.asp)