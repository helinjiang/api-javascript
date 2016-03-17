`String.prototype.search()` 方法执行一个查找，看该字符串对象与一个正则表达式是否匹配。

## 定义和用法

### 语法

`stringObject.search(regexp)`

| 参数 | 描述 |
| --- | --- |
| _regexp_ | 一个正则表达式（regular expression）对象。如果传入一个非正则表达式对象，则会使用 `new RegExp(obj)` 隐式地将其转换为正则表达式对象。 |

### 返回值

`stringObject` 中第一个与 `regexp` 相匹配的子串的起始位置。如果没有找到任何匹配的子串，则返回 `-1`。

### 说明

`search()` 方法不执行全局匹配，它将忽略标志 `g`。它总是从字符串的开始进行检索，返回 `stringObject` 的第一个匹配的位置。

该方法与[`indexOf()`](string-prototype-indexof.html)较为相似，也是返回第一个匹配的位置，但`indexOf()`只接受字符串（如果是 `RegExp` 对象则会被强制转换为字符串）。

当你想要知道字符串中是否存在某个模式（pattern）时可使用 `search`，类似于正则表达式的 `test` 方法。当要了解更多匹配信息时，可使用 `match`（会更慢），该方法类似于正则表达式的 `exec` 方法。

## 实例

```javascript
    var str = "Hello,world! Good world!"
    console.log(str.search(/world/)) //=>6，只返回第一个匹配的位置
    console.log(str.search(/good/)) //=>-1
    console.log(str.search(/good/i)) //=>13，增加标志i之后，可以忽略大小写

    /**
     * 注意下面这个例子的结果，使用search和indexOf的结果是不一样的。
     * search参数中的字符串会被隐式转换为 new RegExp('./xxx/test1.js')，而"."代表的是任意非换行字符
     */
    console.log('{ggg}/xxx/test1.js'.search('./xxx/test1.js')); // 4     
    console.log('{ggg}/xxx/test1.js'.indexOf('./xxx/test1.js')); // -1   
```

## 更多

*   [String.prototype.search()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/search)
*   [JavaScript search() 方法](http://www.w3school.com.cn/jsref/jsref_search.asp)