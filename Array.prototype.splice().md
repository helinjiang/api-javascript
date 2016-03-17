`Array.prototype.splice()` 方法用新元素替换旧元素，以此修改数组的内容。

> 该方法会改变原数组，用新元素替换旧元素，然后返回被删除的元素组成的数组。

## 定义和用法

### 语法

`    arrayObject.splice(index , howMany[, element1[, ...[, elementN]]])

    arrayObject.splice(index) // SpiderMonkey/Firefox extension
`

| 参数 | 描述 |
| --- | --- |
| _index_ | 从数组的哪一位开始修改内容（数组第一位为 `0` ）。如果超出了数组的长度，则自动从数组末尾开始添加内容；如果是负值，则表示从数组末位开始的第几位。 |
| _howmany_ | 整数，表示要移除的数组元素的个数。 |
| element1, ..., elementN | 要添加进数组的元素。如果不指定，则 `splice` 只删除数组元素。 |

### 返回值

由被删除的元素组成的一个数组。如果只删除了一个元素，则返回只包含一个元素的数组。如果没有删除元素，则返回空数组。

### 说明

`splice()` 方法可删除从 `index` 处开始的 `howmany` 个元素，并且用参数列表中声明的 `element1, ..., elementN` 来替换那些被删除的元素。

*   如果 `howmany` 是 `0`，则不移除元素。这种情况下，至少应添加一个新元素。
*   如果 `howmany` 超出了 `index` 位之后的元素的总数，则从 `index` 向后至数组末尾的全部元素都将被删除（含第 `index` 位）。
*   如果没有指定 `howmany` 参数（如上第二种语法，是 SpiderMonkey 的扩展功能），将会删除第 `index` 位之后的所有元素（不含第 `index` 位）。

> 请注意，`splice()` 方法与 `slice()` 方法的作用是不同的，`splice()` 方法会直接对原数组进行修改，而 [`Array.prototype.slice()`](array-prototype-slice.html) 则会返回一个新的删除之后的子数组，而不会直接操作原数组。

## 实例

```javascript
    var arr = ["a", "b", "c", "d", "e", "f"];
    console.log(arr); //=>["c", "f", "d", "a", "b", "e"] 
    console.log(arr.splice(2, 0, "hello")); //=>[]，由于删除数量为0，因此返回的是空数组，同时增加了一个新元素
    console.log(arr); //=>["a", "b", "hello", "c", "d", "e", "f"]，注意原数组已发生了变化
    console.log(arr.splice(2, 1, "word")); //=>["hello"] ，删除了一个元素，又增加了一个元素
    console.log(arr); //=>["a", "b", "word", "c", "d", "e", "f"]，注意原数组已发生了变化
```

## 更多

*   [Array.prototype.splice()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/splice)
*   [JavaScript splice() 方法](http://www.w3school.com.cn/jsref/jsref_splice.asp)