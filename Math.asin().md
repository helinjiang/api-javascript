`Math.asin(x)` 函数返回指定数值 “`x`” 的反正弦（单位为弧度）。

## 定义和用法

### 语法

`Math.asin(x)`

| 参数 | 描述 |
| --- | --- |
| _x_ | `-1.0` ~ `1.0` 之间的数 |

### 返回值

`x` 的反正弦值。返回的值是 `-PI/2` 到 `PI/2` 之间的弧度值。

### 说明

由于 `Math.asin()` 是 `Math` 中的一个静态方法，你应该通过 `Math.asin()` 调用。（`Math` 不是构造器）

如果参数 `x` 小于 `-1.0` 或大于 `1.0` ，则将返回 `NaN`。

## 实例

```javascript
    Math.asin(-2);  // NaN
    Math.asin(-1);  // -1.5707963267948966 (-pi/2)
    Math.asin(0);   // 0
    Math.asin(0.5); // 0.5235987755982989
    Math.asin(1);   // 1.570796326794897 (pi/2)
    Math.asin(2);   // NaN
```

## 更多

*   [Math.asin()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/asin)