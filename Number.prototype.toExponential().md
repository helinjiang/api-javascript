`Number.prototype.toExponential()` 方法以指数表示法返回该数值对象的字符串表示。

## 定义和用法

### 语法

`numObj.toExponential(fractionDigits)`

| 参数 | 描述 |
| --- | --- |
| _fractionDigits_ | 一个 `0` 到 `20` 之间的整数，包括 `0` 和 `20`，用来指定小数点后有几位数字。默认用尽可能多的位数。 |

### 返回值

返回 `numObj` 的字符串表示，采用指数计数法，即小数点之前有一位数字，小数点之后有 `fractionDigits` 位数字。该数字的小数部分将被舍入，必要时用 `0` 补足，以便它达到指定的长度。

### 说明

当 `fractionDigits` 太小或太大时抛出异常 `RangeError`。介于 `0` 和 `20`（包括 `20`）之间的值不会引起 `RangeError` 。 执行环境也可以支持更大或更小范围。

当调用该方法的对象不是 `Number` 时抛出 `TypeError` 异常。

## 实例

``` javascript

    var num = 186633;
    console.log(num.toExponential(1)); // 1.9e+5
    console.log(num.toExponential(2)); // 1.87e+5

```

## 更多

*   [Number.prototype.toExponential()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Number/toExponential)
*   [JavaScript toExponential() 方法](http://www.w3school.com.cn/jsref/jsref_toexponential.asp)