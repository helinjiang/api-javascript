`isNaN()` 函数用于检查其参数是否是非数字值。

## 定义和用法

### 语法

`isNaN(x)`

| 参数 | 描述 |
| --- | --- |
| x | 必需。要检测的值。 |

### 返回值

如果 `x` 是特殊的非数字值 `NaN`（或者能被转换为这样的值），返回的值就是 `true`。如果 `x` 是其他值,则返回 `false`。

### 说明

如果要判断某个值是否是 `NaN`，不能使用 `==` 或 `===` 运算符，因为把 `NaN` 与任何值（包括其自身）相比得到的结果均是 `false`。所以只能通过isNaN() 函数来判断。

`isNaN()` 函数通常用于检测 `parseFloat()` 和 `parseInt()` 的结果，以判断结果表示的是否是合法的数字（如果这两个函数无法将参数转换为数字，则返回结果是`NaN`）。当然也可以用 `isNaN()` 函数来检测算数错误，比如用 `0` 作除数的情况。

## 实例

```javascript
    console.log(isNaN(0)); //=>false
    console.log(isNaN(Infinity)); //=>false,Infinity也是数字，表示无限大
    console.log(isNaN("hello")); //=>true，NaN
    console.log(isNaN("hello", 12345)); //=>true, inNaN只比较第一个参数。
    console.log(isNaN()); //=>true,不传参数相当于：isNaN(undefined)，而undefined转换数字之后值为NaN
    console.log(isNaN("123")); //=>false，该字符串可以转换为数字123
    console.log(isNaN([])); //=>false，空数组可以转换为数字0
    console.log(isNaN({})); //=>true
    console.log(isNaN(null)); //=>false，null可以转换为数字0
```

## TIY

*   [亲自试一试](http://www.w3school.com.cn/tiy/t.asp?f=jseg_isNaN)

## 更多

*   [JavaScript isNaN() 函数](http://www.w3school.com.cn/jsref/jsref_isNaN.asp)