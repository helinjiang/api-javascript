`isFinite()` 函数用于检查其参数是否为有限数字（或可转换为有限数字）。

## 定义和用法

### 语法

`isFinite(number)`

| 参数 | 描述 |
| --- | --- |
| number | 必需。要检测的数字。 |

### 返回值

如果 `number` 是有限数字（或可转换为有限数字），那么返回 `true`。否则，如果 `number` 是 `NaN`（非数字），或者是正、负无穷大的数，则返回 `false`。

## 实例

```javascript

    console.log(isFinite(123)); //=> true
    console.log(isFinite(-1.23)); //=> true
    console.log(isFinite()); //=> false
    console.log(isFinite("hello")); //=> false
    console.log(isFinite(Number.NEGATIVE_INFINITY)); //=> false

```

## TIY

*   [如何使用 isFinite()。](http://www.w3school.com.cn/tiy/t.asp?f=jseg_isFinite)

## 更多

*   [JavaScript isFinite() 函数](http://www.w3school.com.cn/jsref/jsref_isFinite.asp)