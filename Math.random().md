`Math.random()` 返回 `[0-1)` 的浮点值伪随机数（大于等于`0`，小于`1`）。

## 定义和用法

### 语法

`Math.random()`

### 返回值

`[0-1)` 的浮点值伪随机数。

### 说明

由于 `Math.random()` 是 `Math` 中的一个静态方法，你应该通过 `Math.random()` 调用。（`Math` 不是构造器）

## 实例

``` javascript

    // 返回一个大于等于0，小于1的伪随机数
    function getRandom() {
      return Math.random();
    }

    // 返回一个介于min和max之间的随机数
    function getRandomArbitrary(min, max) {
      return Math.random() * (max - min) + min;
    }

    // 返回一个介于min和max之间的整型随机数
    // Using Math.round() will give you a non-uniform distribution!
    function getRandomInt(min, max) {
      return Math.floor(Math.random() * (max - min + 1) + min);
    }

```

## 更多

*   [Math.random()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/random)