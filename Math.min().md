`Math.min()` 返回零个或更多个数值的最小值。

## 定义和用法

### 语法

`Math.min([value1[,value2, ...]]) `

| 参数 | 描述 |
| --- | --- |
| _value1, value2, ..._ | 一组数值，在 ECMASCript 3 之前，该方法只有两个参数。 |

### 返回值

参数中最小的值。如果没有参数，则返回 `Infinity`。如果有某个参数为 `NaN`，或是不能转换成数字的非数字值，则返回 `NaN`。

### 说明

由于 `Math.min()` 是 `Math` 中的一个静态方法，你应该通过 `Math.min()` 调用。（`Math` 不是构造器）

## 实例

### 实例1 常规用法

``` javascript

    var x = 10, y = -20;
    var z = Math.min(x, y);

```

### 实例2 使用 Math.min 裁剪值（clippint a value）

Math.min 经常用于裁剪一个值，以便使其总是小于或等于某个边界值。

``` javascript

    // 写法一
    var x = f(foo);
    if (x > boundary) {
        x = boundary;
    }

    // 写法二
    var x = Math.min(f(foo), boundary);

```

## 更多

*   [Math.min()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/min)