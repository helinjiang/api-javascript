`parseInt()` 函数可解析一个字符串，并返回一个整数。

## 定义和用法

### 语法

`parseInt(_string_, _radix_)`

| 参数 | 描述 |
| --- | --- |
| _string_ | 必需。要被解析的字符串。 |
| _radix_ | 

可选。表示要解析的数字的基数。该值介于 `2` ~ `36` 之间。否则将返回 `NaN`。

 |

### 返回值

返回解析后的数字。

### 说明

当参数 `radix` 的值为 0，或没有设置该参数时，parseInt() 会根据 `string` 来判断数字的基数。

*   如果它以 “`0x`” 或 “`0X`” 开头，将以 `16` 为基数。
*   如果它以 “`0`” 开头，那么 ECMAScript 3的某些实现可能将其解析为以 `8` 为基数，建议此场景下时，指定基数。
*   如果它以 `1` ~ `9` 的数字开头，将以 `16` 为基数。

开头和结尾的空格是允许的。

如果字符串的第一个字符不能被转换为数字，那么 `parseFloat()` 会返回 `NaN`。

## 实例

```javascript

    console.log(parseInt("10")); //=> 10
    console.log(parseInt("19", 10)); //=> 19
    console.log(parseInt("11", 2)); //=> 3
    console.log(parseInt("17", 8)); //=> 15
    console.log(parseInt("1f", 16)); //=> 31
    console.log(parseInt("010")); //=> 10，注意该值在ECMAScript 3的某些实现中可能会返回8
    console.log(parseInt("010", 8)); //=> 8

```

## TIY

*   [如何使用 parseInt() 来解析不同的字符串](http://www.w3school.com.cn/tiy/t.asp?f=jseg_parseInt)
*   [ECMAScript 类型转换](http://www.w3school.com.cn/js/pro_js_typeconversion.asp)

## 更多

*   [JavaScript parseInt() 函数](http://www.w3school.com.cn/jsref/jsref_parseInt.asp)
*   如需更多有关类型转换的知识，请阅读 JavaScript 高级教程中的相关内容：