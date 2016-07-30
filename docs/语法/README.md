# 基础

CoffeeScript采用缩进式语法，无需`;`和`{}`。不过`;`也可用来在单行中合并表达式。

函数调用无需`()`：

```coffee
console.log sys.inspect object
```

转译为：

```js
console.log(sys.inspect(object));
```
