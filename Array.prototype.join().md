`Array.prototype.join()` 方法将数组中的所有元素连接成一个字符串，元素之间是通过指定的分隔符进行分隔的。

> 该方法不会改变原数组，而会返回转换之后的字符串。

## 定义和用法

### 语法

`arrayObject.join([separator = ','])`

| 参数 | 描述 |
| --- | --- |
| _separator_ | 可选，用于指定连接每个数组元素的分隔符。 |

### 返回值

返回一个字符串。该字符串是通过把 `arrayObject` 的每个元素转换为字符串，然后把这些字符串连接起来，并在两个元素之间插入 `separator` 字符串而生成的。

### 说明

如果省略`separator`参数，则默认使用逗号（`,`）作为分隔符。如果 `separator` 是一个空字符串（`""`），那么数组中的所有元素将被直接连接。

## 实例

```javascript

    var a = ['Wind', 'Rain', 'Fire'];
    var myVar1 = a.join();      // myVar1的值变为"Wind,Rain,Fire"
    var myVar2 = a.join(', ');  // myVar2的值变为"Wind, Rain, Fire"
    var myVar3 = a.join(' + '); // myVar3的值变为"Wind + Rain + Fire"
    var myVar4 = a.join("");    // myVar4的值变为"WindRainFire"

```

## 更多

*   [Array.prototype.join()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/join)
*   [JavaScript join() 方法](http://www.w3school.com.cn/jsref/jsref_join.asp)