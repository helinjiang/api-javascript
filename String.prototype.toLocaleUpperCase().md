`String.prototype.toLocaleUpperCase()` 方法返回调用该方法的字符串被转换成大写写之后的值，转换规则根据任何本地化特定的大小写映射。

## 定义和用法

### 语法

`stringObject.toLocaleUpperCase()`

### 返回值

一个新的字符串，在其中 `stringObject` 的所有小写字符全部被转换为了大写字符。

### 说明

与 `toUpperCase()` 不同的是，`toLocaleUpperCase()` 方法按照本地方式把字符串转换为大写。一般而言，该方法的返回值与 `toUpperCase()` 一样，只有几种语言（如土耳其语）具有地方特有的大小写映射时，结果才有区别。

## 实例

```javascript

    var str = "Hello World!";
    console.log(str.toLocaleUpperCase()); //=>"HELLO WORLD! "
    console.log(str); //=>"Hello World!"，不会改变原字符串    

```

## 更多

*   [String.prototype.toLocaleUpperCase()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/toLocaleUpperCase)
*   [JavaScript toLocaleUpperCase() 方法](http://www.w3school.com.cn/jsref/jsref_toLocaleUpperCase.asp)