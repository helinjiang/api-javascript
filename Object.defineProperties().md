`Object.defineProperties()` 方法在一个对象上添加或修改一个或者多个自有属性，并返回该对象。

## 定义和用法

### 语法

`Object.defineProperties(obj, props)`

| 参数 | 描述 |
| --- | --- |
| _obj_ | 将要被添加属性或修改属性的对象 |
| _props_ | 该对象的一个或多个键值对定义了将要为对象添加或修改的属性的具体配置 |

### 返回值

修改后的原对象。

### 说明

如果只是针对一个属性，则可以考虑使用 `Object.defineProperty()`。

## 实例

```javascript
    var obj = {};

    Object.defineProperties(obj, {
        "property1": {
            value: true,
            writable: true
        },
        "property2": {
            value: "Hello",
            writable: false
        }
    });

    console.log(obj.property2); // "Hello"
```

## 更多

*   [Object.defineProperties()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Object/defineProperties)