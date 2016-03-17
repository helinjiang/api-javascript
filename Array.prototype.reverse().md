`Array.prototype.reverse()` 方法用于颠倒（反转）数组中元素的顺序。第一个元素会成为最后一个，最后一个会成为第一个。

> 该方法会改变原数组，并返回该数组的引用。

## 定义和用法

### 语法

`arrayObject.reverse()`

### 说明

该方法会改变原来的数组，而不会创建新的数组。

## 实例

``` javascript

    var arr = ["George", "John", "Thomas"] ;
    console.log(arr); // ["George", "John", "Thomas"] 
    console.log(arr.reverse()); // ["Thomas", "John", "George"]
    console.log(arr); // ["Thomas", "John", "George"]，注意此时原数组发生了变化

```

## 更多

*   [Array.prototype.reverse()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/reverse)
*   [JavaScript reverse() 方法](http://www.w3school.com.cn/jsref/jsref_reverse.asp)