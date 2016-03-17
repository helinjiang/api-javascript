`String.prototype.indexOf()` 方法返回指定值在字符串对象中首次出现的位置。

## 定义和用法

### 语法

`stringObject.indexOf(searchValue[, fromIndex])`

| 参数 | 描述 |
| --- | --- |
| _searchValue_ | 一个字符串表示被查找的值 |
| _fromIndex_ | 表示调用该方法的字符串中开始查找的位置。它的合法取值是 `0` 到 `stringObject.length - 1`。默认值为 `0`。 |

### 说明

该方法从 `fromIndex` 位置开始，从头到尾顺序查找子串 `searchValue` 在 `stringObject` 中首次出现的位置。如果不存在，则返回 `-1`。

*   如果省略 `fromIndex` 参数，或者 `fromIndex < 0` ，则查找整个字符串（等效于 `fromIndex = 0`）
*   如果 `fromIndex >= stringObject.length` ，则该方法返回 `-1`
*   如果被查找的字符串 `searchValue` 是一个空字符串，则`fromIndex < stringObject.length`时该方法返回 `fromIndex`，`fromIndex >= stringObject.length` 时该方法返回 `stringObject.length`

`indexOf` 方法区分大小写。

如果需要获得 `searchValue` 最后出现的位置，可以使用[`lastIndexOf()`](string-prototype-lastindexof.html)方法。

## 实例

```javascript

    var str = "Hello world!";
    console.log(str.indexOf("Hello")); // 0
    console.log(str.indexOf("World")); // -1，注意indexOf()方法对大小写敏感！
    console.log(str.indexOf("world")); // 6
    console.log(str.indexOf("world", 7)); // -1，从下标是7的字符开始检索
    console.log(str.indexOf("", 11)); // 11
    console.log(str.indexOf("", 12)); // 12，str的长度为12，大于或等于12时，搜索空字符串最多为12
    console.log(str.indexOf("", 13)); // 12

```

## 更多

*   [String.prototype.indexOf()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/indexOf)
*   [JavaScript indexOf() 方法](http://www.w3school.com.cn/jsref/jsref_indexOf.asp)