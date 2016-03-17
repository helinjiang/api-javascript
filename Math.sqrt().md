`Math.sqrt(x)` 函数返回`x`的平方根。

## 定义和用法

### 语法

`Math.sqrt(x)`

| 参数 | 描述 |
| --- | --- |
| _x_ | 一个数值 |

### 返回值

参数 `x` 的平方根。如果 `x` 小于 0，则返回 `NaN`。

### 说明

由于 `Math.sqrt()` 是 `Math` 中的一个静态方法，你应该通过 `Math.sqrt()` 调用。（`Math` 不是构造器）

如果要计算一个数的任意次根，可以使用 [`Math.pow()`](math-pow.html) 方法。

## 实例

```javascript
    Math.sqrt(9); // 3
    Math.sqrt(2); // 1.414213562373095

    Math.sqrt(1);  // 1
    Math.sqrt(0);  // 0
    Math.sqrt(-1); // NaN
```

## 更多

*   [Math.sqrt()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/sqrt)