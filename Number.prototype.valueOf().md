`Number.prototype.valueOf()` 方法返回一个被 `Number` 对象包装的原始值（primitive value）。

## 定义和用法

### 语法

`numObj.valueOf()`

### 返回值

`numObj` 的原始值（primitive value）。

### 说明

> 该方法通常在 JavaScript 内部被调用，而不是在代码里显式调用。

## 实例

``` javascript

    var numObj = new Number(10);
    console.log(typeof numObj); // object

    var num = numObj.valueOf();
    console.log(num); // 10
    console.log(typeof num); // number

```

## 更多

*   [Number.prototype.valueOf()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Number/valueOf)