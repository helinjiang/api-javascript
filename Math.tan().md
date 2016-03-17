`Math.tan(x)` 方法返回`x`的正切值。

## 定义和用法

### 语法

`Math.tan(x)`

| 参数 | 描述 |
| --- | --- |
| _x_ | 一个数值，表示一个角（单位：弧度）。 |

### 返回值

参数 `x` 的正切值。

### 说明

由于 `Math.tan()` 是 `Math` 中的一个静态方法，你应该通过 `Math.tan()` 调用。（`Math` 不是构造器）

## 实例

``` javascript

    //下面的函数返回变量 x 的正切值
    function getTan(x) {
       return Math.tan(x);
    }

    //下面的函数可以接受以度为单位的数值，将其转为弧度，然后返回其正切值。
    function getTanDeg(deg) {
       var rad = deg * Math.PI/180;
       return Math.tan(rad);
    }

```

## 更多

*   [Math.tan()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/tan)