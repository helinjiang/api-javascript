`Math.acos(x)` 函数返回指定数值 “`x`” 的反余弦值（单位为弧度）。

## 定义和用法

### 语法

`Math.acos(x)`

| 参数 | 描述 |
| --- | --- |
| _x_ | `-1.0` ~ `1.0` 之间的数 |

### 返回值

`x` 的反余弦值。返回的值是 `0` 到 `PI` 之间的弧度值。

### 说明

由于 `Math.acos()` 是 `Math` 中的一个静态方法，你应该通过 `Math.acos()` 调用。（`Math` 不是构造器）

如果参数 `x` 小于 `-1.0` 或大于 `1.0` ，则将返回 `NaN`。

## 实例

```javascript
    Math.acos(-2);  // NaN
    Math.acos(-1);  // 3.141592653589793
    Math.acos(0);   // 1.5707963267948966
    Math.acos(0.5); // 1.0471975511965979
    Math.acos(1);   // 0
    Math.acos(2);   // NaN
```

## 更多

*   [Math.acos()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/acos)