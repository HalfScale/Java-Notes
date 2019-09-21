# Closures
- A closure is a function that makes us of variables
defined in outer functions that have previously returned.
- Closure exists when an inner function make use of variables
declared in an outer function which has previously returned.
- Closure does not exist if you don not return an inner function and if that inner function does not make use of variables returned by an outer function.
-We can use closures to create private variables and write better code that isolates our logic and application.

```javascript
function outer() {
	var data = 'Closures are ';
	return function inner() {
		var innerData = 'awesome'
		return data + innerData;
	}
}

outer(); // Returns the 'inner' function definition
outer()(); // Returns the concatenated string from the 'inner' function 
```

```javascript
function outer() {
	var count = 0;
	// We can return an anonymous function (Doesn't need a name)
	return function(num) {
		return count += num;
	}
}

var myFunc = outer();
myFunc(10) // return 10
myFunc(15) // return 25
myFunc(100) // return 125


```
