# OOP in JavaScript

### Constructor Functions

```javascript
// The capital name of the constructor function is in capital
// Just a convention.
function House(bedrooms, bathrooms, numSqft) {
	this.bedrooms = bedrooms;
	this.bathrooms = bathrooms;
	this.numSqft = numSqft;
}

var myHouse = House(2, 2, 256)
console.log(myHouse) // undefined
```

### 'new' keyword
- We use the new keyword to assign 'this' to an empty object
and set its properties through the parameters.
```javascript
// The capital name of the constructor function is in capital
// Just a convention.
function House(bedrooms, bathrooms, numSqft) {
	this.bedrooms = bedrooms;
	this.bathrooms = bathrooms;
	this.numSqft = numSqft;
}

var myHouse = new House(2, 2, 256)
myHouse.bedrooms; // 2
myHouse.bathrooms; // 2
myHouse.numSqft; // 256
```
- So how the 'new' keyword works?
	- It first creates an empty object.
	- It then sets the keyword 'this' to be that empty object.
	- It adds the line 'return this' to the end of the function,
	which follows it.
	- It adds a property onto the empty object called '__proto__'
	which links the prototype property on the constructor function
	to the empty object.

### Multiple Constructors
- This is used when two functions posses the same properties 
to avoid redundancy or duplication of code.

```javascript
function Car(make, name, year) {
	this.make = make;
	this.name = name;
	this.year = year;
	this.weight = 4;
}

function Motorcycle(make, name, year) {
	// We used Car function and called the 'call' function
	// to change 'this' context to 'Motorcycle' function
	// So the 'this' keyword is actually modifying the 'Motorcycle' object.
	Car.call(this, make, name, year); 
	this.weight = 2;
}
```