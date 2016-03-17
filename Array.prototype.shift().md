`Array.prototype.shift()` 方法用于删除并返回数组的第一个元素。

> 该方法会改变原数组，数组长度减`1`，并返回第一个元素。

## 定义和用法

### 语法

`arrayObject.shift()`

### 返回值

`arrayObject`数组的第一个元素。

### 说明

`shift()` 方法将删除 `arrayObject` 的第一个元素，把数组长度减 `1`，其他元素的序号`index`依次前移，并且返回它删除的元素。如果数组为空，那么 `shift()` 方法将不进行任何操作，返回 `undefined` 值。

要删除并返回数组的最后一个元素，请使用 [`Array.prototype.pop()`](array-prototype-pop.html) 方法。

## 实例

``` javascript

    var arr = ["George", "John", "Thomas"] ;
    console.log(arr); // ["George", "John", "Thomas"] 
    console.log(arr.shift()); // "George"，返回数组第一个元素
    console.log(arr); // ["John", "Thomas"]，注意此时原数组发生了变化

    var arrEmpty = [] ;
    console.log(arrEmpty); // [] 
    console.log(arrEmpty.shift()); // undefined，空数组shift()返回undefined
    console.log(arrEmpty); // [] ，空数组shift()后还是空数组

```

## 更多

*   [Array.prototype.shift()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/shift)
*   [JavaScript shift() 方法](http://www.w3school.com.cn/jsref/jsref_shift.asp)