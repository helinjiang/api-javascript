`Object.prototype.valueOf()` 方法返回该对象的原始值表示。

## 定义和用法

### 语法

`obj.valueOf()`

### 返回值

该对象的原始值表示

### 说明

JavaScript 调用 `valueOf()` 方法来将对象转换为一个原始值。一般不需要你自己主动调用它，JavaScript 会在需要将对象转换成原始值的场景时，自动调用它。

默认情况下，每个对象都会从 `Object` 上继承到 `valueOf()` 方法。JavaScript中每一个内置的核心对象都重写了这个方法，以便返回适当的值。如果这个方法没有被这个对象自身或者更接近的上层原型上的同名方法重写，则调用该对象的 `valueOf()` 方法时会返回" `[object Object]` "。

> 对象转换成字符串都是通过调用其 `toString()` 方法，但 `String` 对象转换成原始类型的值时，则使用 `valueOf()`。所有的对象都可以转换成字符串(" `[object _type_]`" 或其它)，但很多对象是不需要将其转换成 `number`， `boolean` 或者 `function` 的。

## 实例

``` javascript

    function Dog(name, breed, color, sex) {
        this.name = name;
        this.breed = breed;
        this.color = color;
        this.sex = sex;
    }

    var theDog = new Dog("Gabby", "Lab", "chocolate", "female");

    // 采用继承而来的valueOf()方法，可以看到结果对我们而言是没多少意义的
    alert(theDog.valueOf()); // [object Object]

    // 重写valueOf()方法
    Dog.prototype.valueOf = function() {
        var ret = "Dog " + this.name + " is a " + this.sex + " " + this.color + " " + this.breed;
        return ret;
    }

    // 重写之后的输出
    alert(theDog.valueOf()); // "Dog Gabby is a female chocolate Lab"

```

## 更多

*   [Object.prototype.valueOf()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Object/valueOf)