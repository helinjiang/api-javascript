`getHours()`方法可返回时间的小时字段。

## 定义和用法

### 语法

`dateObject.getHours()`

### 返回值

`dateObject` 的小时字段，以本地时间显示。返回值是 `0` （午夜） 到 `23` （晚上 11 点）之间的一个整数。

### 说明

由 `getHours()` 返回的值是一个两位的数字。不过返回值不总是两位的，如果该值小于 `10`，则仅返回一位数字。

## 实例

```javascript

    var d = new Date();
    console.log(d.getHours()); //=>12，假设当前时间为2015.9.5 12:24:05

    var d1 = new Date("8 21, 1999 01:15:00");
    console.log(d1.getHours()); //=>1

```

## TIY

*   [如何使用 getHours(), getMinutes() 以及 getSeconds() 来显示当前的时间。](http://www.w3school.com.cn/tiy/t.asp?f=jseg_datetime)
*   [如何使用 getHours(), getMinutes() 以及 getSeconds() 来显示当前的时间。](http://www.w3school.com.cn/tiy/t.asp?f=jseg_datetime2)

## 更多

*   [JavaScript getHours() 方法](http://www.w3school.com.cn/jsref/jsref_getHours.asp)