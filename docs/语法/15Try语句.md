# Try/Catch/Finally语句

与JavaScript相同，不过可`catch`和`finnaly`部分都可省略：

```coffee
try
	allHellBreaksLoose()
	catsAndDogsLivingTogether()
catch error
	print error
finally
	cleanUp()
```

转译为：

```js
var error, error1;

try {
	allHellBreaksLoose();
	catsAndDogsLivingTogether();
} catch (error1) {
	error = error1;
	print(error);
} finally {
	cleanUp();
}
```

只有`try`部分：

```coffee
try
	allHellBreaksLoose()
	catsAndDogsLivingTogether()
```

转译为：

```js
try {
	allHellBreaksLoose();
	catsAndDogsLivingTogether();
} catch (undefined) {}
```
