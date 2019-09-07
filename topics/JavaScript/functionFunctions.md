# Call, Apply and Bind

- As functions are also Objects in JavaScript, these 3 methods are used to
control the invocation of the function(So a function can also have a function in JavaScript).

### Call / Apply function
- this functions(*call()*/*apply()*) are used to invoke the target function immediately.

#### Usage 
```javascript
// call() usage

var dog = {
	name: 'Fiddo'
}

function makeSound(sound, soundOne, soundTwo) {
	console.log(this.name + ' makes a sound:', sound, soundOne, soundTwo);
}

makeSound.call(dog, 'Arf! Arf!', 'Woof! Woof!', 'Raaaaf!');

//Output
// Fiddo makes a sound: Arf! Arf! Woof! Woof! Raaaaf!

```
- *Syntax: call(obj, a, b, c, d, e, ...)*
- The first parameter in ```call()``` method sets the *this* value, which is the object,
on which the function is invoked upon. In this case the *dog* object above.
- The rest of parameters are arguements to the actual function.

```javascript
var cat = {
	name: 'Mimi'
}

function makeSound(sound, soundOne, soundTwo) {
	console.log(this.name + ' makes a sound:', sound, soundOne, soundTwo);
}

makeSound.apply(cat, ['Meeow!', 'Puuurrr~', 'Meow Meow']);

//Output
// Mimi makes a sound: Meeow! Puuurrr~ Meow Meow
```
- *Syntax: apply(obj, [a, b, c, d, ...])*
- Similar to the call method, the first parameter is the Object that will be passed on. The
second parameter accepts an array of data.

### Bind function
```javascript
var cat = {
	name: 'Mimi'
}

function makeSound(sound, soundOne, soundTwo) {
	console.log(this.name + ' makes a sound:', sound, soundOne, soundTwo);
}

var catSound = makeSound.bind(cat, ['Meeow!', 'Puuurrr~', 'Meow Meow']);
catSound();

//Output
// Mimi makes a sound: Meeow! Puuurrr~ Meow Meow
```
- *Syntax: bind(obj, a, b, c, d, e, ...)*
- First arguement is the object that will be passed on, and the other parameters are for the
arguements that will be passed on the function. the bind returns the function that is called
upon a given function and can be used later on(compared to call/apply that executes immediately).