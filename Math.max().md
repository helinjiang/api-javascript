`Math.max([value1[,value2, ...]])` 返回零个或更多个数值的最大值。

## 定义和用法

### 语法

`Math.max([value1[,value2, ...]]) `

| 参数 | 描述 |
| --- | --- |
| _value1, value2, ..._ | 一组数值，在 ECMASCript 3 之前，该方法只有两个参数。 |

### 返回值

参数中最大的值。如果没有参数，则返回 `-Infinity` 。如果有某个参数为 `NaN` ，或是不能转换成数字的非数字值，则返回 `NaN`。

### 说明

由于 `Math.max()` 是 `Math` 中的一个静态方法，你应该通过 `Math.max()` 调用。（`Math` 不是构造器）

## 实例

### 实例1 常规用法

```javascript
    Math.max(10, 20);   //  20
    Math.max(-10, -20); // -10
    Math.max(-10, 20);  //  20
```

### 实例2 与apply的妙用

下面的方法使用 `apply` 方法寻找一个数值数组中的最大元素。`getMaxOfArray([1,2,3])` 等价于 `Math.max(1, 2, 3)`，但是你可以使用 `getMaxOfArray` 作用于任意长度的数组上。

```javascript
    function getMaxOfArray(numArray) {
        return Math.max.apply(null, numArray);
    }
```

## 更多

*   [Math.max()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/max)