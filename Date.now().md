`Date.now()`方法返回自 `1970年1月1日 00:00:00 UTC` 到当前时间的毫秒数。

## 定义和用法

### 语法

`var timeInMs = Date.now();`

### 返回值

返回自 `1970年1月1日 00:00:00 UTC` 到当前时间的毫秒数，类型为 `Number` 。

### 说明

该方法的结果与 `new Date().getTime()` 一致。

## 实例

``` javascript

    console.log(Date.now()); // 1449152818104
    console.log(new Date().getTime()); // 1449152818104

```

## 更多

*   [Date.now()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/now)