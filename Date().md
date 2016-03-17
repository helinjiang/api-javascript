`Date()`方法可返回当天的日期和时间。

## 定义和用法

### 语法

`Date()`

### 返回值

字符串，当天的日期和时间

### 说明

该方法与`new Date()`返回结果是不一样的，后者返回Date对象，它提供了更多与时间相关的方法，我们也推荐使用后者来操作时间。

## 实例

```javascript
    var dateStr = Date();
    console.log(dateStr); //=>"Sat Sep 05 2015 11:22:22 GMT+0800 (中国标准时间) "
    console.log(typeof dateStr); //=>"string"

    var dateObj = new Date();
    console.log(typeof dateObj); //=>"object"
    console.log(dateObj.getTime()); //=>1441423342563 ，Date对象有很多操作时间的方法
```

## TIY

*   [如何使用 Date() 来取得当天的日期。](http://www.w3school.com.cn/tiy/t.asp?f=jseg_date)

## 更多

*   [JavaScript Date() 方法](http://www.w3school.com.cn/jsref/jsref_Date.asp)