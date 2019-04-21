# Generics 

- Generic enables types (classes and interfaces) to be parameters when defining classes
- Generic provides more type safety
- Was introduced on Java 5.0

**Example**
```java
List dogs = new List();
dogs.add(new Dog());
dogs.add(new Cat());
dogs.add(new Giraffe());

// A list of dogs could contain cats and giraffe without generics.
```
The example above is not using any generics. So there are no type safety checks and a List of dogs can include a cat, and a giraffe object. As if it were accepting an object of type Object.

```java
List<Dog> dogs = new List<>();
dogs.add(new Cat()); // compile time error!
dogs.add(new Giraffe()); // compile time error!

//With generics a list of Dog can only accept a Dog object
```
The example above now use generics. It produces error at compile time since the List of dogs can only contain of type Dog object.

**Diagram**

![](../img/java/woutgeneric.PNG)
![](../img/java/withgeneric.PNG)

*The picture above is from Head First Java*

### Generic Class

```java
public class ClassName <T> {
  private T t; // T stands for Type
  
  public void set(T t) {
    this.t = t;
  }
  
  public T get() {
    return t;
  }
}
```
### Generic Methods

```java
public class ClassName {
  
  public <T> void doSomething(T type) {
    // ... execute something here
  }
}
```
In generic methods, the type shoud be declared before the return type.

### Generic bounded types

```java
//For class

public class ClassName <T extends Number>{
  private T t;
  
  public void set(T t) { this.t = t; }
  
  public void get() { return t; }
}

//For method

public boolean <T extends Number> doSomething (T t) {
  // ... execute something here
}
```
- In the example above it's called *bounded type* generics. The types is being bounded(After the **extends** keyword) on a specific type. Making it more strict on the types that it accepts.
- The extends keyword in the generic context means **extends or implements a class**. In the example above the type only accepts a type that is a **Number** or it's subclasses.

```java
public class ClassName <T extends Integer> {
  private T n;
  
  public NaturalNumber(T n) { this.n = n }
  
  public boolean isEven() {
    return n.intValue() % 2 == 0;
  }
}
```
- Bounded type parameter allows you to invoke methods defined in the bounds (Given the example above).

### Generic Multiple Bounds

```java
public class ClassName <T extends Fire & Wind & Water> {
  // ... some code here
}
```
- A type variable with multiple bounds is a subtype of all types listed in the bound.
- If one of the bounds is a class it must be specified first.

```java
//List of the class/interface that will be implemented
class Fire { ... }
interface Wind { ... }
interface Water { ... }

//A class must be the first to be specified
class ClassName <T extends Fire & Wind & Water> { ... } // OK

//If not
class ClassName <T extends Wind & Fire & Water> { ... } // compile time error!
```
