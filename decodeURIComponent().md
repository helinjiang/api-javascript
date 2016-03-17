`decodeURIComponent()` 函数可对 `encodeURIComponent()` 函数编码的 `URI` 进行解码。

## 定义和用法

### 语法

`decodeURIComponent(encodedURI)`

| 参数 | 描述 |
| --- | --- |
| _encodedURI_ | 必需。一个字符串，含有编码 `URI` 组件或其他要解码的文本。 |

### 返回值

`encodedURI` 的副本，其中的十六进制转义序列将被它们表示的字符替换。

## 实例

```javascript

    var test = "http://www.helinjiang.com/Hello World/";
    var testURI = encodeURIComponent(test);
    console.log(testURI); // http%3A%2F%2Fwww.helinjiang.com%2FHello%20World%2F
    console.log(decodeURIComponent(testURI)); // http://www.helinjiang.com/Hello World/

```

## 更多

*   [JavaScript decodeURIComponent() 函数](http://www.w3school.com.cn/jsref/jsref_decodeURIComponent.asp)