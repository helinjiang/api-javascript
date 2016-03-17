`getMilliseconds()` 方法可返回时间的毫秒。

## 定义和用法

### 语法

`dateObject.getMilliseconds()`

### 返回值

`dateObject`的毫秒字段，以本地时间显示。返回值是 `0` ~ `999` 之间的一个整数。

### 说明

由 `getMilliseconds()` 返回的值是一个三位的数字。不过返回值不总是三位的，如果该值小于 100，则仅返回两位数字，如果该值小于 10，则仅返回一位数字。

## 实例

``` javascript

       var d = new Date();
    console.log(d.getMilliseconds()); //=>555，假设当前时间为2015.9.5 12:24:47:555

    var d1 = new Date("8 21, 1999 01:15:00");
    console.log(d1.getMilliseconds()); //=>0

```

console.log(html);

## TIY

*   [如何使用 getMilliseconds() 来取得当前的毫秒。](http://www.w3school.com.cn/tiy/t.asp?f=jseg_getmilliseconds)
*   [如何使用 getHours(), getMinutes() 以及 getSeconds() 来显示当前的时间。](http://www.w3school.com.cn/tiy/t.asp?f=jseg_datetime)
*   [如何使用 getHours(), getMinutes() 以及 getSeconds() 来显示当前的时间。](http://www.w3school.com.cn/tiy/t.asp?f=jseg_datetime2)

## 更多

*   [JavaScript getMilliseconds() 方法](http://www.w3school.com.cn/jsref/jsref_getMilliseconds.asp)