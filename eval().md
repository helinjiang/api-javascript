`eval()` 函数可计算某个字符串，并执行其中的的 JavaScript 代码。

> *[warning]* ：`eval()` 的功能非常强大，但不推荐使用，甚至在ECMAScript 5的严格模式下使用时，程序会报错。

## 定义和用法

### 语法

`eval(string)`

| 参数 | 描述 |
| --- | --- |
| string | 必需。要计算的字符串，其中含有要计算的 JavaScript 表达式或要执行的语句。 |

### 返回值

通过计算 `string` 得到的值（如果有的话）。

### 说明

该方法只接受原始字符串作为参数，如果 `string` 参数不是原始字符串，那么该方法将不作任何改变地返回。因此请不要为 `eval()` 函数传递 `String` 对象来作为参数。

如果参数中没有合法的表达式和语句，则抛出 `SyntaxError` 异常。

如果非法调用 `eval()`，则抛出 `EvalError` 异常。

如果传递给 `eval()` 的 Javascript 代码生成了一个异常，`eval()` 将把该异常传递给调用者。

## 实例

```javascript
    eval("2+3"); //=> 5
    eval("2+3+"); //=> Uncaught SyntaxError: Unexpected end of input
```

## TIY

*   [如何使用 eval()。](http://www.w3school.com.cn/tiy/t.asp?f=jseg_eval)

## 更多

*   [JavaScript eval() 函数](http://www.w3school.com.cn/jsref/jsref_eval.asp)