`String.prototype.replace()` 方法使用一个替换值（replacement，字符串或一个函数）替换掉一个匹配模式（pattern，字符串或者 `RegExp` ）在原字符串中的某些或所有匹配项，并返回替换后的字符串。

## 定义和用法

### 语法

`stringObject.replace(regexp|substr, newSubStr|function[, flags])`

| 参数 | 描述 |
| --- | --- |
| _regexp_ | 

一个 `RegExp` 对象。该正则所匹配的内容会被替换掉。

 |
| _substr_ | 

一个要被替换的字符串。

 |
| _newSubStr_ | 新子字符串。该字符串中可以内插一些特殊的变量名。 |
| _function_ | 一个用来创建新子字符串的函数，该函数的返回值将替换掉第一个参数匹配到的结果。 |
| _flags_ | **注意：该参数在 v8 内核（Chrome and NodeJs）中不起作用，它不符合标准，不赞成这么做，而是推荐使用一个带有相应标志（flags）的 `RegExp` 对象来代替此参数。**一个字符串指定正则表达式标志的组合，必须是以下一个或多个字符：`g`（全局替换）、`i`（忽略大小写）、`m`（多行模式） |

### 返回值

一个新的字符串。

### 说明

字符串 `stringObject` 的 `replace()` 方法执行的是查找并替换的操作。如果 `regexp` 具有全局标志 `g`，那么 `replace()` 方法将替换所有匹配的子串。否则，它只替换第一个匹配子串。

`replacement` 可以是字符串，也可以是函数。如果它是字符串，那么每个匹配都将由字符串替换。但是 `replacement` 中的 `$` 字符具有特定的含义。如下表所示，它说明从模式匹配得到的字符串将用于替换。

#### 使用字符串作为参数

替换字符串可以插入下面的特殊变量名：

| 变量名 | 代表的值 |
| --- | --- |
| $$ | 插入一个 `"$"` |
| $& | 插入匹配的子串 |
| $` | 插入当前匹配的子串左边的内容 |
| $' | 插入当前匹配的子串右边的内容 |
| $1、$2、...、$99 | 插入 `regexp` 中的第 `1` 到第 `99` 个子表达式相匹配的文本 |

#### 指定一个函数作为参数

你可以指定一个函数作为第二个参数。在这种情况下，当匹配执行后， 该函数就会执行。 函数的返回值作为替换字符串。 (注意: 上面提到的特殊替换参数在这里不能被使用。) 另外要注意的是， 如果第一个参数是正则表达式， 并且其为全局匹配模式， 那么这个方法将被多次调用， 每次匹配都会被调用。

下面是该函数的参数：

| 变量名 | 代表的值 |
| --- | --- |
| match | 匹配的子串。（对应于上述的 `$&` ） |
| p1, p2, ... | 子表达式匹配的文本（对应于上述的`$1`，`$2`等） |
| offset | 匹配到的子字符串在原字符串中的偏移量（比如，如果原字符串是 `"abcd"` ，匹配到的子字符串时 `"bc` ，那么这个参数将时 `1`） |
| $' | 插入当前匹配的子串右边的内容 |
| string | 被匹配的原字符串 |

## 实例

### 例子 1

在本例中，我们将使用 "China" 替换字符串中的 "world"：

```javascript

   var str = "Hello, world! world Hello World!";
   console.log(str.replace(/world/, "China")); // "Hello, China! world Hello World! "，如果没有全局标志g，则只是替换第一个匹配项
   console.log(str); // "Hello, world! world Hello World! "，原字符串并没有改变
   console.log(str.replace(/world/g, "China")); // "Hello, China! China Hello World!  "，有了全局标志g，则只是替换所有匹配，但区分大小写
   console.log(str.replace(/world/gi, "China")); // "Hello, China! China Hello China!  "，有全局标志g和忽略大小写标志i，则将匹配所有并且不区分大小写

```

### 例子2

本例中，我们将测试`replacement`中带`$`字符的场景：

```javascript

    var name = "Doe, John";
    console.log(name.replace(/(\w+)\s*,\s*(\w+)/, "Hello, $2 and $1!")); // "Hello, John and Doe! "，

    var str = '"a", "b"';
    console.log(str.replace(/"([^"]*)"/g, "'$1'")); // "'a', 'b'"，将双引号修改为单引号            

```

### 例子 3

在本例中，我们将把字符串中所有单词的首字母都转换为大写：

```javascript

    var str = "aaa bbb ccc";
    var result = str.replace(/\b\w+\b/g, function(word) {
        return word.substring(0, 1).toUpperCase() + word.substring(1);
    });
    console.log(result); // "Aaa Bbb Ccc"，将匹配到的单词首字母大写
    console.log(str.match(/\b\w+\b/g)); //  ["aaa", "bbb", "ccc"]，使用match()方法可以知道所有匹配项有哪些

```

## 更多

*   [String.prototype.replace()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/replace)
*   [JavaScript replace() 方法](http://www.w3school.com.cn/jsref/jsref_replace.asp)