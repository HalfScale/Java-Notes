# Abstract class and method

### Abstract class
```java
// Example for when to use an abstract class

public abstract class Animal { //syntax for declaring an abstract class
  //methods and properties here....
}

public class Dog extends {
 //methods and properties here....
}

public static void main(String[] args) {
  Animal dog = new Dog(); // make sense
  Animal animal = new Animal(); // what does an Animal object look like?
}
```
*Of course the example above depends on the context, wherein the type of animals is very important
for that specific application.*
- In Java there are classes that shouldn't be instatiated using the ```new``` operator.(Like the given example above,
like instantiating ```Animal``` class). but you can still use it as a reference type (mainly for polymorphism).
- The use of abstract classes is for the purpose of polymorphism( to make polymorphic arguement, return types and arrays)
- An abstract class has virtually* no use, no value, no purpose in life, unless it is extended.

### Abstract vs. Concrete
- A concrete class is specific enough to be instatiated, meaning it's ok to create an object of that type.
- A abstract class is more on being a base class and is generic enough to create a subclass of it.

### Abstract methods
- An abstract methods means the method must be overridden.
- You might think that some methods in an abstract class is too generic that it doesn't make sense, unless they're implemented 
by a more sepcific subclass.

```java
public abstract void eat();
```
- Abstract methods has no body(meaning no ```{}``` brackets)
- If you have a single 
