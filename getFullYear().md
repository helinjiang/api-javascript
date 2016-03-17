`getFullYear()`方法可返回一个表示年份的 4 位数字。

## 定义和用法

### 语法

`dateObject.getFullYear()`

### 返回值

当 `dateObject` 用本地时间表示时返回的年份。返回值是一个四位数，表示包括世纪值在内的完整年份，而不是两位数的缩写形式。

## 实例

```javascript

    var d = new Date();
    console.log(d.getFullYear()); //=>2015，假设当前时间为2015.9.5 12:24:05

    var d1 = new Date("8 21, 1999 01:15:00");
    console.log(d1.getFullYear()); //=>1999

```

## TIY

*   [如何使用 getDate(), getMonth() 以及 getFullYear() 以不同的格式来显示当前的日期。](http://www.w3school.com.cn/tiy/t.asp?f=jseg_datedate)

## 更多

*   [JavaScript getFullYear() 方法](http://www.w3school.com.cn/jsref/jsref_getFullYear.asp)