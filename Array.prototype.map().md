`Array.prototype.map()` 方法返回一个由原数组中的每个元素调用一个指定方法后的返回值组成的新数组。

> 该方法不会改变原数组，而会返回一个新数组。

## 定义和用法

### 语法

`arrayObject.map(callback[, thisArg])`

| 参数 | 描述 |
| --- | --- |
| _callback_ | 原数组中的元素经过该方法后返回一个新的元素

<dl class="dl-horizontal">

<dt>currentValue</dt>

<dd>`callback` 的第一个参数，数组中当前被传递的元素。</dd>

<dt>index</dt>

<dd>`callback` 的第二个参数，数组中当前被传递的元素的索引。</dd>

<dt>array</dt>

<dd>`callback` 的第三个参数，调用 `map` 方法的原数组。</dd>

</dl>

 |
| _thisArg_ | 执行 `callback` 函数时 `this` 指向的对象 |

### 返回值

返回一个新的数组。

### 说明

`map` 方法会给原数组中的每个元素都按顺序调用一次 `callback` 函数，并且 每次执行后的返回值组合起来形成一个新数组。

*   `callback` 函数只会在有值的索引上被调用；那些从来没被赋过值或者使用 `delete` 删除的索引则不会被调用。
*   `callback` 函数会被自动传入三个参数：数组元素，元素索引，原数组本身。

如果 `thisArg` 参数有值，则每次 `callback` 函数被调用的时候，`this` 都会指向 `thisArg` 参数上的这个对象。如果省略了 `thisArg` 参数，或者赋值为 `null` 或 `undefined` ，则 `this` 指向全局对象 。

`map` 不修改调用它的原数组本身（当然可以在 `callback` 执行时改变原数组）。

使用 `map` 方法处理数组时，数组元素的范围是在 `callback` 方法第一次调用之前就已经确定了。在 `map` 方法执行的过程中：原数组中新增加的元素将不会被 `callback` 访问到；若已经存在的元素被改变或删除了，则它们的传递到 `callback` 的值是 `map` 方法遍历到它们的那一时刻的值；而被删除或从来未被赋值的元素将不会被访问到。

## 实例

### 例子 1：将数组中的单词转换成对应的复数形式

```javascript

    function fuzzyPlural(single) {
        var result = single.replace(/o/g, 'e');
        if (single === 'kangaroo') {
            result += 'se';
        }
        return result;
    }

    var words = ["foot", "goose", "moose", "kangaroo"];
    console.log(words.map(fuzzyPlural)); //["feet", "geese", "meese", "kangareese"]

```

### 例子 2：求数组中每个元素的平方根

```javascript

    var numbers = [1, 4, 9];
    var roots = numbers.map(Math.sqrt);

    console.log(roots); // [1, 2, 3]
    console.log(numbers); // [1, 4, 9]，注意原数组并未改变

```

### 例子 3：一个容易犯的错误

通常情况下，`map` 方法中的 `callback` 函数只需要接受一个参数，就是正在被遍历的数组元素本身。但这并不意味着 `map` 只给 `callback` 传了一个参数。这个思维惯性可能会让我们犯一个很容易犯的错误。

```javascript

    // 下面的语句返回什么呢？你可能觉的会是[1, 2, 3]，但实际的结果是 [1, NaN, NaN]
    ["1", "2", "3"].map(parseInt); // [1, NaN, NaN]

    /**
     * 通常使用parseInt时,只需要传递一个参数.但实际上,parseInt可以有两个参数.第二个参数是进制数.可以通过语句"alert(parseInt.length)===2"来验证.
     * map方法在调用callback函数时,会给它传递三个参数:当前正在遍历的元素, 元素索引, 原数组本身.
     * 第三个参数parseInt会忽视, 但第二个参数不会,也就是说,parseInt把传过来的索引值当成进制数来使用.从而返回了NaN.
     *
     * 应该使用如下的用户函数returnInt
     */

    function returnInt(element) {
        return parseInt(element, 10);
    }

    ["1", "2", "3"].map(returnInt); // [1, 2, 3]  

```

## 更多

*   [Array.prototype.map()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/map)