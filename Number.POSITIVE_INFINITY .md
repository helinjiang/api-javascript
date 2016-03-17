`Number.POSITIVE_INFINITY` 属性表示在 JavaScript 里表示正无穷大，该值和全局对象的 `Infinity` 属性的值相同。

`Number.POSITIVE_INFINITY` 属性的属性特性：

|  属性         | 值     |
| ------------  | -------|
|  writable     | false  |
|  enumerable   | false  |
|  configurable | false  |

## 定义和用法

### 描述

该值的行为同数学上的无穷大（infinity）有一点儿不同：

*   任何正值，包括 `POSITIVE_INFINITY`，乘以 `POSITIVE_INFINITY` 为 `POSITIVE_INFINITY` 。
*   任何负值，包括 `NEGATIVE_INFINITY`，乘以 `POSITIVE_INFINITY` 为 `NEGATIVE_INFINITY`。
*   `0` 乘以 `POSITIVE_INFINITY` 为 `NaN`。
*   `NaN` 乘以 `POSITIVE_INFINITY` 为 `NaN`。
*   `POSITIVE_INFINITY` 除以任何负值（除了 `NEGATIVE_INFINITY`）为 `NEGATIVE_INFINITY`。
*   `POSITIVE_INFINITY` 除以任何正值（除了 `POSITIVE_INFINITY`）为 `POSITIVE_INFINITY`。
*   `POSITIVE_INFINITY` 除以 `NEGATIVE_INFINITY` 或 `POSITIVE_INFINITY` 是 `NaN`。
*   任何数除以 `POSITIVE_INFINITY` 为 `0`。

> 为了成功返回一个有限值，你可能会使用 `Number.POSITIVE_INFINITY` 属性来判断是否显示一个条件错误 。然而更好的方式是使用全局的 `isFinite` 方法来处理这种情况。

## 更多

*   [Number.POSITIVE_INFINITY](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Number/POSITIVE_INFINITY)