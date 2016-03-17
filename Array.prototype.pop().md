`Array.prototype.pop()`方法用于删除并返回数组的最后一个元素。

> 该方法会改变原数组，数组长度减`1`，并返回最后一个元素。

## 定义和用法

### 语法

`arrayObject.pop()`

### 返回值

`arrayObject` 数组的最后一个元素。

### 说明

`pop()` 方法将删除 `arrayObject` 的最后一个元素，把数组长度减 `1`，并且返回它删除的元素的值。如果数组已经为空，则 `pop()` 不进行任何操作，并返回 `undefined` 值。

要想删除并返回数组的第一个元素，请使用 [`shift()`](array-prototype-shift.html) 方法。

## 实例

```javascript
    var arr = ["George", "John", "Thomas"] ;
    console.log(arr); // ["George", "John", "Thomas"] 
    console.log(arr.pop()); // "Thomas"，返回数组最后一个元素
    console.log(arr); // ["George", "John"]，注意此时数组发生了变化

    var arrEmpty = [] ;
    console.log(arrEmpty); // [] 
    console.log(arrEmpty.pop()); // undefined，空数组pop()返回undefined
    console.log(arrEmpty); // []，空数组pop()后还是空数组
```

## 更多

*   [Array.prototype.pop()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/pop)
*   [JavaScript pop() 方法](http://www.w3school.com.cn/jsref/jsref_pop.asp)