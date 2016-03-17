`getDay()`方法可返回表示星期的某一天的数字。

## 定义和用法

### 语法

`dateObject.getDay()`

### 返回值

`dateObject`所指的星期中的某一天，使用本地时间。返回值是 `0` （周日）~ `6`（周六） 之间的一个整数。

## 实例

```javascript
    var d = new Date();
    console.log(d.getDay()); //=>5，假设今天是星期五
```

## TIY

*   [使用 getDay() 和一个数组来输出星期的名称，而不是数字。](http://www.w3school.com.cn/tiy/t.asp?f=jseg_date_weekday)

## 更多

*   [JavaScript getDay() 方法](http://www.w3school.com.cn/jsref/jsref_getDay.asp)