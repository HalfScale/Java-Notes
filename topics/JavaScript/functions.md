# JavaScript Functions

### Syntax
```javascript
function myFunction(param) {
  //body of the function
}
```

### Usage

- A basic call to the function named ```myFunction```.

```javascript

myFunction(args);

function myFunction(param) {
  //body of the function
}
```
- Difference between function declaration and function expression

```javascript
// Function declaration
function myFunction(param) {
  console.log('This is a function declaration');
}

// Function expression
var myFunc = function(param) {
  console.log('This is a function expression');
}
```

### Higher-Order Functions
- A higher-order function is a function that can take another function as an arguement or that returns 
a function as a result.

**Example (Basic)**
```javascript
callerFunc(executeFunc); // Outputs "Demonstrating a higher-order function"

function executeFunc() {
	console.log('Demonstrating a higher-order function');
}

function callerFunc(func) {
	func();
}
```

**Example (Advance)**

```javascript
function modify(original, replacement, source) {
	return function(source) {
		return source.replace(original, replacement);
	}
} 

var dogify = modify(/fox/ig, 'dog');

console.log(dogify('The crazy fox jumped over the building!'));
// Output
// The crazy dog jumped over the building!
```
