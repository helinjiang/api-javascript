`Math.sin(x)` 函数返回指定数值 “`x`” 的正弦值。

## 定义和用法

### 语法

`Math.sin(x)`

| 参数 | 描述 |
| --- | --- |
| _x_ | 一个数值（以弧度为单位） |

### 返回值

参数 `x` 的正弦值。返回值在 `-1.0` 到 `1.0` 之间，表示给定角度（单位：弧度）的正弦值。

### 说明

由于 `Math.sin()` 是 `Math` 中的一个静态方法，你应该通过 `Math.sin()` 调用。（`Math` 不是构造器）

## 实例

``` javascript

    Math.sin(3);       // 0.1411200080598672
    Math.sin(-3);      // -0.1411200080598672
    Math.sin(0);       // 0
    Math.sin(Math.PI); // 1.2246467991473532e-16

```

## 更多

*   [Math.sin()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/sin)