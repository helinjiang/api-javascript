`String.prototype.valueOf()` 方法返回一个被 `String` 对象包装的原始值（primitive value）。

## 定义和用法

### 语法

`stringObject.valueOf()`

### 返回值

`stringObject` 的原始值（primitive value）。

### 说明

`String` 对象的 `valueOf` 方法返回一个 `String` 对象的原始值，和 `String.prototype.toString()` 方法返回值一样。

> 该方法通常在 JavaScript 内部被调用，而不是在代码里显式调用。

## 实例

``` javascript

    var str = "Hello World!";
    console.log(str.valueOf()); // Hello World!"  

```

## 更多

*   [String.prototype.valueOf()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/valueOf)