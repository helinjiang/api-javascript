`String.prototype.concat()` 方法将一个或多个字符串与原字符串连接合并，形成一个新的字符串并返回。

## 定义和用法

### 语法

`stringObject.concat(string2, string3[, ..., stringN])`

| 参数 | 描述 |
| --- | --- |
| string2...stringN | 和原字符串连接的多个字符串 |

### 返回

合并之后的

### 说明

该方法将一个或多个字符串与原字符串连接合并，形成一个新的字符串并返回，并不影响原字符串。

> *[warning]* ：强烈建议使用赋值操作符（ `+` , `+=` ）代替 `concat` 方法。参看 性能测试（[perfomance test](http://jsperf.com/concat-vs-plus-vs-join)）。

## 实例

```javascript
var hello = "Hello, ";
console.log(hello.concat("Kevin", " have a nice day.")); // Hello, Kevin have a nice day.
```

## 更多

*   [String.prototype.concat()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/concat)