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

*The picture above is from Head First Java book*

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
- The extends keyword in the generic context means **extends or implements a class**. In the example above the type only accepts of type **Number** or it's subclasses.

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
### Generic Inheritance and Subtypes

```java
// Typical "is-a" relationship
public void someMethod(Number n) { ... }
someMethod(new Integer(10)); //OK
someMethod(new Double(10.1)) //OK

// "is-a" relationship in generics
public void boxTest(Box<Number> n) { ... }

Box<Integer> boxInt = new Box<>();
Box<Double> boxDouble = new Box<>();
Box<Number> boxNum = new Box<>();

boxTest(boxInt); // Error
boxTest(boxDouble); // Error
boxTest(boxNum); // OK
```
- Given the example above, you can't pass in ```Box<Integer>``` & ```Box<Double>```. They are not subtypes of ```Box<Number>```
### Diamond Operator
- The diamond operator(diamond syntax) ```<>``` was introduced in Java 7. The purpose of it is to simplify the use of generics when creating an object.

```java
//without diamond operator
List<Map<String, List<String>>> stringList = new ArrayList<Map<String, List<String>>>();

//with diamond operator
List<Map<String, List<String>>> stringList = new ArrayList<>();
``` 
- The difference is when using a diamond operator, making it much simpler and shorter. It also adds type inference and reduces verbosity.

### Type Inference

```java
//Generic Methods
BoxDemo.<Integer>addBox(Integer.valueOf(10), listOfIntegers);
BoxDemo.addBox(Integer.valueOf(20), listOfIntegers); //without the diamond operator is the same.

//Instantiation of Generic Classes
Map<String, Integer> myMap = new HashMap<String, Integer>();
Map<String, Integer> myMap = new HashMap<>(); //without diamond operator is the same.

```
- It enables you to invoke a **generic method** as you would an ordinary method, without specifying a type between the angle brackets. Java compiler automatically infers (from the method's arguement) that the type parameter is Integer.
- To take take advantage of type inference in **instantiating a class** you must use the diamond ```<>``` operator.

### Wildcards 

```java
//Unbounded wildcard
public static void process (List<?> list) { ... }

//Upper bounded wildcard
public static void process (List<? extends Number> list) { ... }

//Lower bounded wildcard
public static void process (List<? super Integer> list) { ... }
```
- In generic code, the question mark ```?```, called the wildcard, represents an unknown type.
- Unbounded wildcard accepts List of type ? (Unknown or any type).
- You can use upper **bounded wildcard** to relax the restriction on a variable.
- **Upper bounded wildcard** accepts the type on what it is bounded to and it's sublclass (ex. Number and it's subclass)
- **Lower bounded wildcard** accepts the type on what it is bounded to and it's superclass (ex. Integer and it's upperclass)
- When you use a wildcard the compiler stops you from adding references/objects into a collection (List, Set and etc).

```java
// This syntax

public void doSomething(List<? extends Number> list) {
  // execute something here...
}

// Is same with

public <T extends Number> void doSomething(List<T> list) {
  // execute something here...
}
```
*They have the same purpose but with different syntax. Then what is the advantage of one over the other?*

```java
// This is more efficient
public <T extends Number> void doSomething(List<T> one, List<T> two){
  // execute something here...
}

public void doSomething(List<? extends Number> one, List<? extends Number> two) {
  // execute something here...
}
```
- If this is the case then, declaring a parameter type once is more efficient
