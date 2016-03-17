`Object.prototype.hasOwnProperty()` 方法用来判断某个对象是否含有指定的自身属性。

## 定义和用法

### 语法

`obj.hasOwnProperty(prop)`

| 参数 | 描述 |
| --- | --- |
| _prop_ | 要检测的属性名称 |

### 返回值

`true`：自身属性， `false`：不是自身属性。

### 说明

所有继承了 `Object.prototype` 的对象都会从原型链上继承到 `hasOwnProperty` 方法，这个方法可以用来检测一个对象是否含有特定的自身属性，和 `in` 运算符不同，该方法会忽略掉那些从原型链上继承到的属性。

## 实例

### 例子 1：自身属性和继承属性的区别

```javascript

    var o = new Object();
    o.prop = 'exists';
    o.hasOwnProperty('prop'); // 返回 true
    o.hasOwnProperty('toString'); // 返回 false
    o.hasOwnProperty('hasOwnProperty'); // 返回 false

```

### 例子 2：遍历一个对象的所有自身属性

下面的例子演示了如何在遍历一个对象的所有属性时忽略掉继承属性，注意这里 `for..in` 循环只会遍历可枚举属性，这通常就是我们想要的，直接使用 `Object.getOwnPropertyNames()` 方法也可以实现类似的需求。

```javascript

    var buz = {
        fog: 'stack'
    };

    for (var name in buz) {
        if (buz.hasOwnProperty(name)) {
            console.log('this is fog (' + name + ') for sure. Value: ' + buz[name]);
        } else {
            console.log(name); // toString or something else
        }
    }

```

## 更多

*   [Object.prototype.hasOwnProperty()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Object/hasOwnProperty)