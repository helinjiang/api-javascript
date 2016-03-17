`Number.prototype.toPrecision()` 方法以指定的精度返回该数值对象的字符串表示。

## 定义和用法

### 语法

`numObj.toPrecision(precision)`

| 参数 | 描述 |
| --- | --- |
| _precision_ | 一个用来指定数字位数的整数。如果忽略该参数，则该方法表现类似于 `Number.prototype.toString()`。如果该参数是一个非整数值，将会向下舍入到最接近的整数。 |

### 返回值

以定点表示法或指数表示法表示的一个数值对象的字符串表示，四舍五入到 `precision` 参数指定的显示数字位数。查看 `Number.prototype.toFixed()` 方法关于四舍五入的讨论，同样应用于 `toPrecision` 方法。

### 说明

如果 `precison` 参数不在 `1` 和 `100` （包括）之间，将会抛出一个 `RangeError` 。执行环境也可以支持更大或更小的范围。ECMA-262 只需要最多 `21` 位显示数字。

当调用该方法的对象不是 `Number` 时抛出 `TypeError` 异常。

## 实例

``` javascript

    var num = new Number(10000);
    console.log(num.toPrecision(1)); // 1e+4
    console.log(num.toExponential(1));  // 1.0e+4, 与toPrecision唯一的区别

```

## 更多

*   [Number.prototype.toFixed()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Number/toFixed)
*   [JavaScript toPrecision() 方法](http://www.w3school.com.cn/jsref/jsref_toprecision.asp)