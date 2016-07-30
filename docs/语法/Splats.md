# Splats

对于不确定参数个数的函数，可使用`...`代替。

`...`还可用来调用数组。

```coffee
gold = silver = rest = "unknown"

awardMedals = (first, second, others...) ->
    gold = first
    silver = second
    rest = others

contenders = [
    "Michael Phelps"
    "Liu Xiang"
    "Yao Ming"
    "Allyson Felix"
    "Shawn Johnson"
    "Roman Sebrle"
    "Guo Jingjing"
    "Tyson Gay"
    "Asafa Powell"
    "Usain Bolt"
]

awardMedals contenders...

alert "Gold: " + gold
alert "Silver: " + silver
alert "The Field: " + rest
```

转译为：

```js

```

wardMedals, contenders, gold, rest, silver,
	slice = \[].slice;

gold = silver = rest = "unknown";

awardMedals = function() {
	var first, others, second;
	first = arguments[0], second = arguments[1], others = 3 \<= arguments.length ? slice.call(arguments, 2) : \[];
	gold = first;
	silver = second;
	return rest = others;
};

contenders = ["Michael Phelps", "Liu Xiang", "Yao Ming", "Allyson Felix", "Shawn Johnson", "Roman Sebrle", "Guo Jingjing", "Tyson Gay", "Asafa Powell", "Usain Bolt"];

awardMedals.apply(null, contenders);

alert("Gold: " + gold);

alert("Silver: " + silver);

alert("The Field: " + rest);

```

```
