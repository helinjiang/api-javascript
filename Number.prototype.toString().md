`Number.prototype.toString()` 方法返回 `Number` 对象的字符串形式。

## 定义和用法

### 语法

`numObj.toString([radix])`

| 参数 | 描述 |
| --- | --- |
| _radix_ | 指定要用于数字到字符串的转换的基数(从 `2` 到 `36` )。如果未指定 `radix` 参数，则默认值为 `10`。 |

### 返回值

`Number` 对象的字符串形式。

### 说明

`Number` 对象覆盖了 `Object` 对象的 `toString` 方法。对于 `Number` 对象，`toString` 方法返回该对象的字符串形式。

*   如果 `radix` 参数不在 `2` 到 `36` 之间（`[2, 36]`），将会抛出一个 `RangeError`。
*   如果 `radix` 参数大于 `10`，则会使用字母来表示大于 `9` 的数字，比如基数为 `16` 的情况，则使用 `a` 到 `f` 的字母来表示 `10` 到 `15`。
*   如果 `radix` 参数没有指定，则使用 `10`。
*   如果 `radix` 参数是负数，则会保留负号。即使 `radix` 是 `2` 时也是如此：返回的字符串包含一个负号（`-`）前缀和正数的二进制表示，不是数值的二进制补码。

## 实例

```javascript
    var count = 10;

    console.log(count.toString()); // "10"
    console.log((17).toString()); // "17"

    var x = 6;

    console.log(x.toString(2)); // "110"
    console.log((254).toString(16)); // "fe"
    console.log((-10).toString(2)); // "-1010"
    console.log((-0xff).toString()); // "-11111111"
```

## 更多

*   [Number.prototype.toString()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Number/toString)