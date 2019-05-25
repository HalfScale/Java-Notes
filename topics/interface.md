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
- User interface when you want to declare a role that other classes can play regardless 
of where those classes are in the inheritance tree.
