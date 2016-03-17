`String.prototype.localeCompare()`用本地特定的顺序来比较两个字符串。

## 定义和用法

### 语法

`stringObject.localeCompare(target)`

| 参数 | 描述 |
| --- | --- |
| target | 要以本地特定的顺序与 `stringObject` 进行比较的字符串。 |

### 返回值

说明比较结果的数字。如果 `stringObject` 小于 `target`，则 `localeCompare()` 返回小于 `0` 的数。如果 `stringObject` 大于 `target`，则该方法返回大于 `0` 的数。如果两个字符串相等，或根据本地排序规则没有区别，该方法返回 `0`。

### 说明

把 `<` 和 `>` 运算符应用到字符串时，它们只用字符的 `Unicode` 编码比较字符串，而不考虑当地的排序规则。以这种方法生成的顺序不一定是正确的。例如，在西班牙语中，其中字符 “`ch`” 通常作为出现在字母 “`c`” 和 “`d`” 之间的字符来排序。

`localeCompare()` 方法提供的比较字符串的方法，考虑了默认的本地排序规则。ECMAScript 标准并没有规定如何进行本地特定的比较操作，它只规定该函数采用底层操作系统提供的排序规则。

## 实例

```javascript
    var str = "a3";
    var str2 = "b2";
    var str3 = "a2";
    console.log(str.localeCompare(str2)); // -1，str中a的Unicode编码小于str2中b的Unicode编码，故返回-1
    console.log(str.localeCompare(str3)); // 1，在由多个字符组成的字符串中，如果第一个字符相同将比较第二的字符的Unicode编码。

    var arr = ["John", "Paul", "George", "Ringo"];
    arr.sort(function(a, b) {
        return a.localeCompare(b)
    });   
    console.log(arr); // ["George", "John", "Paul", "Ringo"]，localeCompare 可作为sort()的一个自定义排序方法，对数组经行排序。     
```

## 更多

*   [String.prototype.localeCompare()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/localeCompare)
*   [JavaScript localeCompare() 方法](http://www.w3school.com.cn/jsref/jsref_localeCompare.asp)