`Math.cos(x)` 函数返回指定数值 “`x`” 的余弦值。

## 定义和用法

### 语法

`Math.cos(x)`

| 参数 | 描述 |
| --- | --- |
| _x_ | 一个以弧度为单位的数值 |

### 返回值

`x` 的余弦值。返回的是 `-1.0` 到 `1.0` 之间的数。

### 说明

由于 `Math.cos()` 是 `Math` 中的一个静态方法，你应该通过 `Math.cos()` 调用。（`Math` 不是构造器）

## 实例

在本例中，我们将返回不同数值的余弦值：

```javascript
    Math.cos(0);           // 1
    Math.cos(1);           // 0.5403023058681398

    Math.cos(Math.PI);     // -1
    Math.cos(2 * Math.PI); // 1
```

## 更多

*   [Math.cos()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/cos)