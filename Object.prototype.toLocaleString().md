`Object.prototype.toLocaleString()` 方法返回一个该对象的字符串表示。该方法常被本地化的相关对象重写，从而返回“本地化”的字符串，以便于当前环境的用户辨识和使用。

## 定义和用法

### 语法

`obj.toLocaleString()`

### 返回值

对象的本地化的字符串

### 说明

`Object.prototype.toLocaleString()` 方法返回的是`Object.prototype.toString()` 方法的结果。

该函数提供了一个通用的 `toLocaleString()` 方法，即使不大可能被用到，因为JavaScript的许多内置对象都重写了该函数，以实现更适合自身的功能需要。

*   Array: `Array.prototype.toLocaleString()`
*   Number: `Number.prototype.toLocaleString()`
*   Date: `Date.prototype.toLocaleString()`

## 更多

*   [Object.prototype.toLocaleString()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Object/toLocaleString)