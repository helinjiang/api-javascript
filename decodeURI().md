`decodeURI()` 函数可对 `encodeURI()` 函数编码过的 `URI` 进行解码。

## 定义和用法

### 语法

`decodeURI(encodedURI)`

| 参数 | 描述 |
| --- | --- |
| _encodedURI_ | 一个经过 `URL` 编码的字符串。 |

### 返回值

`encodedURI` 的副本，其中的十六进制转义序列将被它们表示的字符替换。

## 实例

``` javascript

    var test = "http://www.helinjiang.com/Hello World/";
    var testURI = encodeURI(test);
    console.log(testURI); // http://www.helinjiang.com/Hello%20World/
    console.log(decodeURI(testURI)); // http://www.helinjiang.com/Hello World/

```

## 更多

*   [decodeURI()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/decodeURI)
*   [JavaScript decodeURI() 函数](http://www.w3school.com.cn/jsref/jsref_decodeURI.asp)