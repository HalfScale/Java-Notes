# Interfaces in Java

```java
// Syntax

public interface Pet { // instead of `class` replace it with `interface`
  
  // Declaring it as 'public' and 'abstract' keyword is optional
  void beFriednly();
  void lick();
  
}

public class Dog implements Pet {
  
  //Implement the methods from the Pet interface
  public void beFriendly() {
    // code here...
  }
  
  public void lick() {
    // code here...
  }
}
```
- Java interfaces solve your problem of multiple inheritance by giving you a polymorphic
benefits. (You can't extend multiple classes but you can implement multiple interfaces)
- Interface is like a 100% abstract class. You can only define abstract methods.
- Classes from different inheritance tree can implement the same interface.

![](../img/java/interfacemultiple.PNG)
- Use interface when you want to declare a role that other classes can play regardless 
of where those classes are in the inheritance tree.

### Default Methods

```java 
//Using default method
public interface Pet {
  void eat();
  void beFriendly();
  
  default boolean isRoaming() {
    //some code here...
  }
}

public interface IPetPlus extends Pet {
  default boolean isRoaming();
}
```
- Suppose you inserted a new method inside an existing interface that is already implemented by several classes.
all classes that implement that interface will break. So to deal with it it's either you make a sub-interface for that interface 
or make a ```default``` method.
