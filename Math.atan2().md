`Math.atan2(y, x)` 函数返回其参数比值的反正切值。

## 定义和用法

### 语法

`Math.atan2(y, x)`

| 参数 | 描述 |
| --- | --- |
| _x_ | 指定点的 X 坐标 |
| _y_ | 指定点的 Y 坐标 |

### 返回值

`-PI` 到 `PI` 之间的值，是从 X 轴正向逆时针旋转到点 (`x`,`y`) 时经过的角度。

### 说明

由于 `Math.atan2()` 是 `Math` 中的一个静态方法，你应该通过 `Math.atan2()` 调用。（`Math` 不是构造器）

请注意这个函数的参数顺序，Y 坐标在 X 坐标之前传递。

`atan2` 接受单独的 x 和 y 参数，而 `atan` 接受两个参数的比值。

## 实例

``` javascript

    Math.atan2(90, 15) // 1.4056476493802699
    Math.atan2(15, 90) // 0.16514867741462683

    Math.atan2( ±0, -0 )               // ±PI.
    Math.atan2( ±0, +0 )               // ±0.
    Math.atan2( ±0, -x )               // ±PI for x > 0.
    Math.atan2( ±0, x )                // ±0 for x > 0.
    Math.atan2( -y, ±0 )               // -PI/2 for y > 0.
    Math.atan2( y, ±0 )                // PI/2 for y > 0.
    Math.atan2( ±y, -Infinity )        // ±PI for finite y > 0.
    Math.atan2( ±y, +Infinity )        // ±0 for finite y > 0.
    Math.atan2( ±Infinity, x )         // ±PI/2 for finite x.
    Math.atan2( ±Infinity, -Infinity ) // ±3*PI/4.
    Math.atan2( ±Infinity, +Infinity ) // ±PI/4.

```

## 更多

*   [Math.atan2()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/atan2)