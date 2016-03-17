`Array.prototype.sort()` 方法用于对数组的元素进行排序。 `sort` 可能不是[稳定的](https://zh.wikipedia.org/wiki/%E6%8E%92%E5%BA%8F%E7%AE%97%E6%B3%95#.E7.A9.A9.E5.AE.9A.E6.80.A7)。

> 该方法会改变原数组，并返回该数组的引用。

## 定义和用法

### 语法

`arrayObject.sort([compareFunction])`

| 参数 | 描述 |
| --- | --- |
| _compareFunction_ | 可选的。用来指定按某种顺序进行排列的函数。如果省略，元素按照字符串的`UNICODE`码位点（code point）排序。 |

### 返回值

原数组的引用。

### 说明

如果没有指明 `compareFunction` ，那么元素会被转换为字符串并按照`UNICODE`码位点顺序排序。要实现这一点，首先应把数组的元素都转换成字符串（如有必要），以便进行比较。例如 "Cherry" 会被排列到 "banana" 之前。当对数字进行排序的时候， 9 会出现在 80 之后，因为他们会先被转换为字符串，而 "80" 比 "9" 要靠前。

如果指明了 `compareFunction` ，那么数组会按照调用该函数的返回值排序。比较函数应该具有两个参数 `a` 和 `b`：

*   如果 `compareFunction(a, b)` 小于 `0` ，那么 `a` 会被排列到 `b` 之前；
*   如果 `compareFunction(a, b)` 等于 `0` ， `a` 和 `b` 的相对位置不变
*   如果 `compareFunction(a, b)` 大于 `0` ， `b` 会被排列到 `a` 之前。
*   `compareFunction(a, b)` 必须总是对相同的输入返回相同的比较结果，否则排序的结果将是不确定的。

## 实例

### 实例1 默认排序

```javascript

    var arr = ["c", "f", "d", "a", "b", "e"];
    console.log(arr); // ["c", "f", "d", "a", "b", "e"] 
    console.log(arr.sort()); // ["a", "b", "c", "d", "e", "f"] 
    console.log(arr); // ["a", "b", "c", "d", "e", "f"] ，注意原数组已发生了变化

```

### 实例2 自定义方法排序

可参考的比较函数伪代码写法如下：

`    // 一般的比较函数
    function compare(a, b) {
        if (a is less than b by some ordering criterion) {
            return -1;
        }
        if (a is greater than b by the ordering criterion) {
            return 1;
        }

        // a 和 b 相等
        return 0;
    }

    // 希望比较数字而非字符串，比较函数可以简单的两数相减，如下的函数将会将数组升序排列
    function compareNumbers(a, b) {
      return a - b;
    }
`

```javascript

    // 自定义比较函数
    function sortNumber(a, b) {
        return a - b;
    }

    var arr = [10, 5, 40, 25, 1000, 1];
    console.log(arr); // [10, 5, 40, 25, 1000, 1] 
    console.log(arr.sort()); // [1, 10, 1000, 25, 40, 5]，默认的字母顺序排序显然不是我们预期的
    console.log(arr.sort(sortNumber)); // [1, 5, 10, 25, 40, 1000]，自定义排序函数来实现数字间排序

    // 也可以使用函数表达式方便的书写
    var numbers = [4, 2, 5, 1, 3];
    numbers.sort(function(a, b) {
        return a - b;
    });
    console.log(numbers); // [1, 2, 3, 4, 5]

    // 对象可以按照某个属性排序
    var items = [
        { name: 'Edward', value: 21 },
        { name: 'Sharpe', value: 37 },
        { name: 'And', value: 45 },
        { name: 'The', value: -12 },
        { name: 'Magnetic' },
        { name: 'Zeros', value: 37 }
    ];

    items.sort(function(a, b) {
        if (a.name > b.name) {
            return 1;
        }
        if (a.name < b.name) {
            return -1;
        }
        // a 和 b 的 name 相等
        return 0;
    });

```

### 实例3 排序非ASCII字符

当排序非 ASCII 字符的字符串（如包含类似 `e`, `é`, `è`, `a`, `ä` 等字符的字符串）。一些非英语语言的字符串需要使用 `String.prototype.localeCompare()`。这个函数可以将函数排序到正确的顺序。

```javascript

    var items = ['réservé', 'premier', 'cliché', 'communiqué', 'café', 'adieu'];
    items.sort(function(a, b) {
        return a.localeCompare(b);
    });

    console.log(items); // ['adieu', 'café', 'cliché', 'communiqué', 'premier', 'réservé']

```

### 实例4 使用映射改善排序

`compareFunction` 可能需要对元素做多次映射以实现排序，尤其当 `compareFunction` 较为复杂，且元素较多的时候，某些 `compareFunction` 可能会导致很高的负载。使用 `map` 辅助排序将会是一个好主意。基本思想是首先将数组中的每个元素比较的实际值取出来，排序后再将数组恢复。

```javascript

    // 需要被排序的数组
    var list = ['Delta', 'alpha', 'CHARLIE', 'bravo'];

    // 对需要排序的数字和位置的临时存储
    var map = list.map(function(e, i) {
        return { index: i, value: e.toLowerCase() };
    })

    // 按照多个值排序数组
    map.sort(function(a, b) {
        return +(a.value > b.value) || +(a.value === b.value) - 1;
    });

    // 根据索引得到排序的结果
    var result = map.map(function(e){
        return list[e.index];
    });

    console.log(result); // ["alpha", "bravo", "CHARLIE", "Delta"]

```

## 更多

*   [Array.prototype.sort()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/sort)
*   [JavaScript sort() 方法](http://www.w3school.com.cn/jsref/jsref_sort.asp)