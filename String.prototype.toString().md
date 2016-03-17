`String.prototype.toString()` 方法返回指定对象的字符串形式。

## 定义和用法

### 语法

`stringObject.toString()`

### 返回值

指定对象的字符串形式。

### 说明

`String` 对象覆盖了 `Object` 对象的 `toString` 方法。对于 `String` 对象，`toString` 方法返回该对象的字符串形式，和 `String.prototype.valueOf()` 方法返回值一样。

## 实例

```javascript
    var str = "Hello World!";
    console.log(str.toString()); // Hello World!"  
```

## 更多

*   [String.prototype.toString()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/toString)