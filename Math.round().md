`Math.round(x)` 返回`x`四舍五入后最接近的整数值。

## 定义和用法

### 语法

`Math.round(x)`

| 参数 | 描述 |
| --- | --- |
| _x_ | 一个数值 |

### 返回值

`x` 四舍五入后最接近的整数值。

### 说明

由于 `Math.round()` 是 `Math` 中的一个静态方法，你应该通过 `Math.round()` 调用。（`Math` 不是构造器）

如果`x`的小数部分是`0.5`或者更大，则将被四舍五入到下一个更大的整数，反之，则被四舍五入到下一个更小的整数。

## 实例

把不同的数舍入为最接近的整数：

```javascript

    Math.round(0.49); // 0
    Math.round(0.60); // 1
    Math.round(5.8);  // 6
    Math.round(-5.8); // -6

```

## 更多

*   [Math.round()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/round)