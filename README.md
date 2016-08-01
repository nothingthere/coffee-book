范力文

# CoffeeScript学习笔记

**CoffeeScript，取JavaScript精华。**

尽可能保证与转译后的JavaScript一致。

可与现有JavaScript库相互调用。

转译结果可读性强。

与原生JavaScript相比，执行效率有过之而无不及。

## 概览

```coffee
# 赋值
number = 42
opposite = true
# 条件语句
number = -42 if opposite

# 函数
square = (x) -> x * x

# 数组
list = [1,2,3,4,5]

# 对象
math =
    root: Math.sqrt
    square: square
    cube: (x) -> x * square x

# Splats参数
race = (winner, runners...) ->
    print winner, runners

# 条件
alert "I knew it!" if elvis?

# 数组操作
cubes = (math.cube num for num in list)
```

转译为：

```js
var cubes, list, math, num, number, opposite, race, square,
    slice = [].slice;

number = 42;

opposite = true;

if (opposite) {
    number = -42;
}

square = function (x) {
    return x * x;
};

list = [1, 2, 3, 4, 5];

math = {
    root: Math.sqrt,
    square: square,
    cube: function (x) {
        return x * square(x);
    }
};

race = function () {
    var runners, winner;
    winner = arguments[0], runners = 2 <= arguments.length ? slice.call(arguments, 1) : [];
    return print(winner, runners);
};

if (typeof elvis !== "undefined" && elvis !== null) {
    alert("I knew it!");
}

cubes = (function () {
    var i, len, results;
    results = [];
    for (i = 0, len = list.length; i < len; i++) {
        num = list[i];
        results.push(math.cube(num));
    }
    return results;
})();
```
