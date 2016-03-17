`Array.prototype.push()` 方法添加一个或多个元素到数组的末尾，并返回数组新的长度（`length` 属性值）。

> 该方法会改变原数组，返回数组新的 `length` 属性值。

## 定义和用法

### 语法

`arrayObject.push(element1, ..., elementN)`

| 参数 | 描述 |
| --- | --- |
| elementN | 被添加到数组末尾的元素。 |

### 返回值

数组新的长度（`length` 属性值）。

### 说明

`push()` 方法可把它的参数顺序添加到 `arrayObject` 的尾部。它直接修改 `arrayObject`，而不是创建一个新的数组。

要想数组的开头添加一个或多个元素，请使用 [`Array.prototype.unshift()`](array-prototype-unshift.html) 方法。

## 实例

### 实例1 常规应用

```javascript
    var arr = ["George", "John", "Thomas"] ;
    console.log(arr); // ["George", "John", "Thomas"] 
    console.log(arr.push("James")); // 4，返回数组新的长度
    console.log(arr); // ["George", "John", "Thomas", "James"]，注意此时数组发生了变化
    console.log(arr.push("Hello","World")); // 6，返回数组新的长度
    console.log(arr); // ["George", "John", "Thomas", "James", "Hello", "World"]，注意此时数组发生了变化
```

### 实例2 配合apply()方法

该示例使用 `apply()` 添加第二个数组的所有元素。

```javascript
    var vegetables = ['parsnip', 'potato'];
    var moreVegs = ['celery', 'beetroot'];

    // Merge the second array into the first one
    // Equivalent to vegetables.push('celery', 'beetroot');
    Array.prototype.push.apply(vegetables, moreVegs);

    console.log(vegetables); // ['parsnip', 'potato', 'celery', 'beetroot']
```

## 更多

*   [Array.prototype.push()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/push)
*   [JavaScript push() 方法](http://www.w3school.com.cn/jsref/jsref_push.asp)