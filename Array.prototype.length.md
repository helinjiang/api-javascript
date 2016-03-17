`Array.prototype.length` 属性表示一个无符号 32-bit 整数，返回一个数组中的元素个数。

`Array.prototype.length` 属性的属性特性：

<dl class="dl-horizontal">

<dt>writable</dt>

<dd>`true`</dd>

<dt>enumerable</dt>

<dd>`false`</dd>

<dt>configurable</dt>

<dd>`false`</dd>

</dl>

## 定义和用法

### 语法

`arrayObject.length`

### 描述

`length` 属性的值是一个 `0` 到 `2^32-1` 的整数。

你可以通过减小 `length` 属性的值来截短一个数组，但不能通过增大 `length` 属性的值来延长这个数组，也就是说，如果你将一个拥有两个元素的数组的 `length` 属性设置为 3，那么这个数组仍然只包含两个元素，最后一个元素不存在。因此， `length` 属性不能真正表示数组中定义的值的序号。

## 实例

```javascript

    fvar numbers = [1, 2, 3, 4, 5];

    for (var i = 0; i < numbers.length; i++) {
        numbers[i] *= 2;
    }
    // numbers现在为[2,4,6,8,10];

```

## 更多

*   [Array.prototype.length](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/length)