`Math.log(x)` 可返回指定数值 `x` 的自然对数。

## 定义和用法

### 语法

`Math.log(x)`

| 参数 | 描述 |
| --- | --- |
| _x_ | 一个数值 |

### 返回值

`x` 的自然对数。

### 说明

由于 `Math.log()` 是 `Math` 中的一个静态方法，你应该通过 `Math.log()` 调用。（`Math` 不是构造器）

参数 `x` 必须大于 `0`，如果为负数，则返回值为`NaN`。

## 实例

```javascript
    Math.log(-1); // NaN, out of range
    Math.log(0);  // -Infinity
    Math.log(1);  // 0
    Math.log(10); // 2.302585092994046
```

## 更多

*   [Math.log()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/log)