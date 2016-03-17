`getMonth()`方法可返回表示月份的数字。

## 定义和用法

### 语法

`dateObject.getMonth()`

### 返回值

`dateObject` 的月份字段，使用本地时间。返回值是 `0`（一月） 到 `11`（十二月） 之间的一个整数。

## 实例

```javascript

    var d = new Date();
    console.log(d.getMonth()); //=>8，假设当前时间为2015.9.5 12:24:05

    var d1 = new Date("8 21, 1999 01:15:00");
    console.log(d1.getMonth()); //=>7

```

## TIY

*   [如何使用 getMonth() 来取得当前月份的名称。](http://www.w3school.com.cn/tiy/t.asp?f=jseg_date_getmonth)
*   [如何使用 getDate(), getMonth() 以及 getFullYear() 以不同的格式来显示当前的日期。](http://www.w3school.com.cn/tiy/t.asp?f=jseg_datedate)

## 更多

*   [JavaScript getMonth() 方法](http://www.w3school.com.cn/jsref/jsref_getMonth.asp)