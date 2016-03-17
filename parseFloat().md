`parseFloat()` 函数可解析一个字符串，并返回一个浮点数。

## 定义和用法

### 语法

`parseFloat(_string_)`

| 参数 | 描述 |
| --- | --- |
| _string_ | 必需。要被解析的字符串。 |

### 返回值

返回解析后的数字。

### 说明

该函数指定字符串中的首个字符是否是数字。如果是，则对字符串进行解析，直到到达数字的末端为止，然后以数字返回该数字，而不是作为字符串。

`parseFloat()` 是全局函数，不属于任何对象。

`parseFloat()` 将它的字符串参数解析成为浮点数并返回。如果在解析过程中遇到了正负号（`+` 或 `-`）、数字 (`0-9`)、小数点，或者科学记数法中的指数（`e` 或 `E`）以外的字符，则它会忽略该字符以及之后的所有字符，返回当前已经解析到的浮点数。

> 您可以通过调用 `isNaN` 函数来判断 `parseFloat()` 的返回结果是否是 `NaN`。如果让 NaN 作为了任意数学运算的操作数，则运算结果必定也是 `NaN`。

如果字符串的第一个字符不能被转换为数字，那么 `parseFloat()` 会返回 `NaN`。

开头和结尾的空格是允许的，将被忽略。

如果只想解析数字的整数部分，请使用 `parseInt()` 方法。

## 实例

```javascript

    console.log(parseFloat("10")); //=> 10
    console.log(parseFloat("10.00")); //=> 10
    console.log(parseFloat("10.33.55")); //=> 10.33，第二个小数点将被看成无效
    console.log(parseFloat("34 45 66")); //=> 34
    console.log(parseFloat(" 60 ")); //=> 60
    console.log(parseFloat("40 year")); //=> 40
    console.log(parseFloat("He was 40")); //=> NaN
    console.log(parseFloat("FF2")); //=> NaN

    console.log(parseFloat("3.14")); //=> 3.14
    console.log(parseFloat("314e-2")); //=> 3.14; //=> 3.14
    console.log(parseFloat("0.0314E+2")); //=> 3.14
    console.log(parseFloat("3.14more non-digit characters")); //=> 3.14

```

## TIY

*   [ECMAScript 类型转换](http://www.w3school.com.cn/js/pro_js_typeconversion.asp)

## 更多

*   [JavaScript parseFloat() 函数](http://www.w3school.com.cn/jsref/jsref_parseFloat.asp)