`getYear()`方法可返回表示相对于1900年的年份。

## 定义和用法

### 语法

`dateObject.getYear()`

### 返回值

返回 `Date` 对象的年份字段。

## 实例

```javascript
    var d = new Date();
    console.log(d.getYear()); //=>115，假设当前时间为2015.9.5 12:24:05

    var d1 = new Date("8 21, 1999 01:15:00");
    console.log(d1.getYear()); //=>99

    var d2 = new Date("8 21, 1799 01:15:00");
    console.log(d2.getYear()); //=>-101

    var d3 = new Date("8 21, 2999 01:15:00");
    console.log(d3.getYear()); //=>1099

    var d4 = new Date("8 21, 1900 01:15:00");
    console.log(d4.getYear()); //=>0
```

## TIY

*   [如何使用 getYear() 来取得当前的年份。](http://www.w3school.com.cn/tiy/t.asp?f=jseg_getyear)

## 更多

*   [JavaScript getYear() 方法](http://www.w3school.com.cn/jsref/jsref_getYear.asp)