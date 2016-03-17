`String.prototype.lastIndexOf()` 方法返回指定值在字符串对象中最后一次出现的位置。

## 定义和用法

### 语法

`stringObject.lastIndexOf(searchValue[, fromIndex])`

| 参数 | 描述 |
| --- | --- |
| _searchValue_ | 一个字符串表示被查找的值 |
| _fromIndex_ | 表示调用该方法的字符串中开始查找的位置。它的合法取值是 `0` 到 `stringObject.length - 1`。默认值是 `stringObject.length`。 |

### 说明

该方法从 `fromIndex` 位置开始，从尾到头逆序查找子串 `searchValue` 在 `stringObject` 中最后一次出现的位置。如果不存在，则返回 `-1`。

*   如果省略 `fromIndex` 参数，或者 `fromIndex > stringObject.length` ，则查找整个字符串（等效于 `fromIndex = stringObject.length`）
*   如果 `fromIndex < 0` ，则查找第一个字符（等效于 `fromIndex = 0`）
*   如果被查找的字符串 `searchValue` 是一个空字符串，则`fromIndex < stringObject.length`时该方法返回 `fromIndex`，`fromIndex >= stringObject.length` 时该方法返回 `stringObject.length`

`lastIndexOf` 方法区分大小写。

如果需要获得 `searchValue` 首次出现的位置，可以使用[`indexOf()`](string-prototype-indexof.html)方法。

## 实例

``` javascript

    var str = "Hello world!";
    console.log(str.lastIndexOf("Hello")); // 0
    console.log(str.lastIndexOf("World")); // -1，注意lastIndexOf()方法对大小写敏感！
    console.log(str.lastIndexOf("world")); // 6
    console.log(str.lastIndexOf("world", 7)); // 6
    console.log(str.lastIndexOf("world", 5)); // -1
    console.log(str.lastIndexOf("", 11)); // 11
    console.log(str.lastIndexOf("", 12)); // 12，str的长度为12，大于或等于12时，搜索空字符串最多为12
    console.log(str.lastIndexOf("", 13)); // 12

```

## 更多

*   [String.prototype.lastIndexOf()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/lastIndexOf)
*   [JavaScript lastIndexOf() 方法](http://www.w3school.com.cn/jsref/jsref_lastIndexOf.asp)