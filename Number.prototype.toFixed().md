`Number.prototype.toFixed()` 方法可把 `Number` 四舍五入为指定小数位数的数字。

## 定义和用法

### 语法

`numObj.toFixed(digits)`

| 参数 | 描述 |
| --- | --- |
| _digits_ | 小数点后数字的个数， `0` 到 `20` 之间的整数，包括 `0` 和 `20`，实现环境可能支持更大范围。如果忽略该参数，则默认为 `0`。 |

### 返回值

一个数值的字符串表现形式，不使用指数记数法，而是在小数点后有 `digits` 位数字。该数值在必要时进行四舍五入，另外在必要时会用 `0` 来填充小数部分，以便小数部分有指定的位数。 如果数值大于 `1e+21`，该方法会简单调用 `Number.prototype.toString()` 并返回一个指数记数法格式的字符串。

### 说明

如果 `digits` 参数太小或太大。`0` 到 `20`（包括）之间的值不会引起 `RangeError`。实现环境（implementations）也可以支持更大或更小的值。

当调用该方法的对象不是 `Number` 时抛出 `TypeError` 异常。

## 实例

```javascript
    var num = 13.33668;
    console.log(num.toFixed(2))  // 13.34
    console.log(num.toFixed(4))  // 13.3367
```

## 更多

*   [Number.prototype.toFixed()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Number/toFixed)
*   [JavaScript toFixed() 方法](http://www.w3school.com.cn/jsref/jsref_tofixed.asp)