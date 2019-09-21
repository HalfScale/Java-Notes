# 'This' keyword
- Usually deretmined by how a function is called(what we call 'execution context')
- Can be determined using four rules (global, object/implicit, explicit, new)

### Global Context
- When 'this' is not inside of a declared object
```javascript
console.log(this); // window object

function whatIsThis() {
	return this;
}

function variablesInThis() {
	//Since the value of this is the window
	//All we are doing here is creating a global variable
	this.person = "Elie";
}
variablesInThis();
console.log(person); //Elie

whatIsThis(); // window object
```
- Using 'use strict' to remove the value of 'this'(Points to the global variable *Window*) inside of a function as **undefined**
```javascript
'use strict'

console.log(this); // window object

function whatIsThis() {
	return this;
}

function variablesInThis() {
	this.person = "Elie";
}
whatIsThis(); // undefined

variablesInThis(); // Type Error for assigning ellie to an undefiend
```

### Implicit/Object
- When the keyword 'this' is inside a declared object.
```javascript
var person = {
	firstName: 'Marwin',
	sayHi: function() {
		return 'Hi ' + this.firstName
	}
	determineContext: function() {
		return this === person
	}
}
```
- In the example above the 'this' keyword now refers to the person variable/Object or it's context now is set to 'person' and not the window object.