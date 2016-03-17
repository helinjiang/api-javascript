`String.prototype.toLocaleLowerCase()` 方法返回调用该方法的字符串被转换成小写之后的值，转换规则根据任何本地化特定的大小写映射。

## 定义和用法

### 语法

`stringObject.toLocaleLowerCase()`

### 返回值

一个新的字符串，原字符串中的所有大写字符全部被转换为了小写字符。

### 说明

与 `toLowerCase()` 不同的是，`toLocaleLowerCase()`方法按照本地方式把字符串转换为小写。一般而言，该方法的返回值与 `toLowerCase()` 一样，只有几种语言（如土耳其语）具有地方特有的大小写映射时，结果才有区别。

## 实例

``` javascript

    var str = "Hello World!";
    console.log(str.toLocaleLowerCase()); // "hello world! "
    console.log(str); // "Hello World!"，不会改变原字符串    

```

## 更多

*   [String.prototype.toLocaleLowerCase()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/toLocaleLowerCase)
*   [JavaScript toLocaleLowerCase() 方法](http://www.w3school.com.cn/jsref/jsref_toLocaleLowerCase.asp)