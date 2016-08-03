# 内嵌JavaScript片段

如需嵌入JavaScript片段，将其放在反引号间即可：

```coffee
hi = `function() {
	return [document.title, "Hello JavaScript"].join(": ");
}`
```

转译为：

```js
var hi;

hi = function() {
return [document.title, "Hello JavaScript"].join(": ");
};
```
