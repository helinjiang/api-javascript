`Array.prototype.unshift()` 方法可向数组的开头添加一个或更多元素，并返回新的长度（`length` 属性值）。

> 该方法会改变原数组，返回数组新的 `length` 属性值。

## 定义和用法

### 语法

`arrayObject.unshift(element1, ..., elementN)`

| 参数 | 描述 |
| --- | --- |
| element1, ..., elementN | 要添加到数组开头的元素。 |

### 返回值

数组新的长度（`length` 属性值）。

### 说明

`unshift()` 方法将把它的参数插入 `arrayObject` 的头部，并将已经存在的元素顺次地移到较高的下标处，以便留出空间。该方法的第一个参数将成为数组的新元素 `0`，如果还有第二个参数，它将成为新的元素 `1`，以此类推。

要把一个或多个元素添加到数组的尾部，请使用 [`Array.prototype.push()`](array-prototype-push.html) 方法。

## 实例

```javascript
    var arr = ["George", "John", "Thomas"];
    console.log(arr); // ["George", "John", "Thomas"] 
    console.log(arr.unshift("James")); // 4，返回数组新的长度
    console.log(arr); // ["James", "George", "John", "Thomas"]，注意此时数组发生了变化
    console.log(arr.unshift("Hello", "World")); // 6，返回数组新的长度
    console.log(arr); // ["Hello", "World", "James", "George", "John", "Thomas"]，注意此时数组发生了变化
```

## 更多

*   [Array.prototype.unshift()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/unshift)
*   [JavaScript unshift() 方法](http://www.w3school.com.cn/jsref/jsref_unshift.asp)