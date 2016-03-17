`Math.abs(x)` 函数返回指定数值 “`x`” 的绝对值。

## 定义和用法

### 语法

`Math.abs(x)`

| 参数 | 描述 |
| --- | --- |
| _x_ | 一个数值 |

### 返回值

`x` 的绝对值。

### 说明

由于 `Math.abs()` 是 `Math` 中的一个静态方法，你应该通过 `Math.abs()` 调用。（`Math` 不是构造器）

## 实例

传入一个非数字形式的字符串或者 `undefined`/empty 变量，将返回 `NaN`。传入 `null` 将返回 `0`。

```javascript

    Math.abs('-1');     // 1
    Math.abs(-2);       // 2
    Math.abs(null);     // 0
    Math.abs("string"); // NaN
    Math.abs();         // NaN

```

## 更多

*   [Math.abs()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/abs)