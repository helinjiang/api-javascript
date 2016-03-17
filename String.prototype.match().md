`String.prototype.match()` 方法可在字符串内检索指定的值，或找到一个或多个正则表达式的匹配。

## 定义和用法

### 语法

`stringObject.match(regexp)`

| 参数 | 描述 |
| --- | --- |
| _regexp_ | 一个正则表达式对象。如果传入一个非正则表达式对象，则会隐式地使用 `new RegExp(obj)` 将其转换为正则表达式对象。 |

### 返回值

一个包含匹配结果的数组，如果没有匹配项，则返回 `null`。

### 说明

`match()` 方法将检索字符串 `stringObject`，以找到一个或多个与 `regexp` 匹配的文本。这个方法的行为在很大程度上有赖于 `regexp` 是否具有标志 `g`：

| 标识 | 行为 |
| --- | --- |
| 无`g` | `match()` 方法将执行一次检索（匹配一次）。它返回和`RegExp.prototype.exec(str)`相同的结果。

*   如果没有找到任何匹配的文本， 则返回 `null`。
*   否则，它将返回一个数组，其中存放了与它找到的匹配文本有关的信息。该数组的第 `0` 个元素存放的是匹配文本，而其余的元素存放的是与正则表达式的子表达式匹配的文本。除了这些常规的数组元素之外，返回的数组还含有两个对象属性。`index` 属性声明的是匹配文本的起始字符在 `stringObject` 中的位置，`input` 属性声明的是对 `stringObject` 的引用。

```javascript
    /**
     * 下例的返回结果数组中，有两个元素["world", "or"]，其中第一个元素"world"是匹配结果，第二个"or"是子表达式匹配的文本
     * 而{index: 6, input: "Hello world!"}实际上是这个的数组的两个对象属性
     */
     var result = "Hello world!".match(/w(or)ld/);
     console.log(result); // ["world", "or", index: 6, input: "Hello world!"]
     console.log(result.length); // 2，因为数组元素为["world", "or"]
     console.log(result.index); // 6，同时该数组又有index和input两个属性值
```

 |
| 有`g` | `match()` 方法将执行全局检索，找到 `stringObject` 中的所有匹配子字符串（全局匹配，匹配多次）。

*   如果没有找到任何匹配的文本， 则返回 `null`。
*   否则，它将返回一个数组，其中存放了所有匹配的结果。注意返回的数组元素只是匹配的子串，不包括子表达式的结果，也没有 `index` 属性或 `input` 属性。

```javascript
    /**
     * 下例的返回结果数组中，只有一个元素["world"]，因为全局匹配只匹配到了一个结果。
     * 但结果中并未出现子表达式结果 "or" ,也没有 index 和 input 这两个对象属性
     */
     var result = "Hello world!".match(/w(or)ld/g);
     console.log(result); // ["world"]，不包括子表达式的结果
     console.log(result.length); // 1
     console.log(result.index); // undefined，同时该数组也没有index和input两个属性值
```

 |

`String.prototype.match()` 和 `RegExp.prototype.exec()` 的区别：

*   非全局检索模式下（无 `g`）：返回结果一致，没有任何区别。
*   全局检索模式下（有 `g`）：返回包含了所有匹配后的结果。`String.prototype.match()` 不需要去循环匹配，直接返回一个数组（无匹配情况下是 `null`），返回的数组元素只是匹配元素本身；而`RegExp.prototype.exec()` 需要循环匹配，每次匹配返回的元素不仅包含了匹配元素，还包含了子表达式结果及 `index` 和 `input` 这两个对象属性。

关于查找和匹配，还有一些其它的方法可以采用：

*   如果你只是需要某个子串在原字符串出现的位置，可以使用`indexOf()` 和 `lastIndexOf()`。
*   如果你只是需要知道一个字符串是否匹配一个正则表达式（`RegExp`），可使用 `RegExp.prototype.test(str)`。
*   如果你只是需要第一个匹配结果，你也可以使用 `RegExp.prototype.exec(str)`。

## 实例

```javascript
    var str = "Hello world! world Hello!";
    var test = str.match("world"); //使用字符串来检索
    console.log(test); // ["world", index: 6, input: "Hello world!"]
    console.log(test[0]); // "world"，返回数组的第一个元素就是匹配的值
    console.log(test.length); // 1，最多只有一个匹配结果
    console.log(test.index); // 6
    console.log(test.input); // "Hello world! world Hello!"

    // 使用String.prototype.match()方法来全局匹配
    var test1 = str.match(/world/g); 
    console.log(test1); // ["world", "world"]
    console.log(test1.length); // 2，使用全局匹配之后，会返回所有结果
    console.log(test1.index); // undefined，使用全局匹配之后，结果没有index和input属性

    // 使用RegExp.prototype.exec()方法来全局匹配
    var str = "Hello world! world Hello!",
        reg = /world/g,
        item;

    while (item = reg.exec(str)) {
        console.log(item);
    }
    // [ 'world', index: 6, input: 'Hello world! world Hello!' ]
    // [ 'world', index: 13, input: 'Hello world! world Hello!' ]

    console.log(str.match("World")) // null，如果是字符串形式，则match对大小写敏感
    console.log(str.match("worlld")) // null

    console.log("1 plus 2 equal 3".match(/\d+/g)); // ["1", "2", "3"]，使用全局匹配的正则表达式来检索字符串中的所有数字
```

## 更多

*   [String.prototype.match()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/match)
*   [JavaScript match() 方法](http://www.w3school.com.cn/jsref/jsref_match.asp)