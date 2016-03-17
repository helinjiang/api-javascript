`Number.prototype.toLocaleString()` 方法返回一个该 `Number` 对象的字符串表示。该方法常被本地化的相关对象重写，从而返回“本地化”的字符串，以便于当前环境的用户辨识和使用。

## 定义和用法

### 语法

`numObj.toLocaleString([locales [, options]])`

### 返回值

本地化的字符串

## 实例

``` javascript

    var number = 3500;
    console.log(number.toLocaleString()); // 3,500 ，在不同环境下结果可能不一样

```

## 更多

*   [Number.prototype.toLocaleString()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Number/toLocaleString)