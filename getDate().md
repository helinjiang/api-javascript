`getDate()`方法可返回当天的日期和时间。

## 定义和用法

### 语法

`dateObject.getDate()`

### 返回值

`dateObject` 所指的月份中的某一天，使用本地时间。返回值是 `1` ~ `31` 之间的一个整数。

## 实例

``` javascript

    var d = new Date();
    console.log(d.getDate()); //=>5，假设当前时间为2015.9.5 12:24:05

    var d1 = new Date("8 21, 1999 01:15:00");
    console.log(d1.getDate()); //=>21

```

## TIY

*   [如何使用 getDate() 来取得当前月份的日期。](http://www.w3school.com.cn/tiy/t.asp?f=jseg_getDate)
*   [如何使用 getDate(), getMonth() 以及 getFullYear() 以不同的格式来显示当前日期。](http://www.w3school.com.cn/tiy/t.asp?f=jseg_datedate)

## 更多

*   [JavaScript Date() 方法](http://www.w3school.com.cn/jsref/jsref_getDate.asp)