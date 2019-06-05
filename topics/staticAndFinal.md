# Statics and final in java
- The ```static``` keyword in java lets a method run without any instance of a class.

### Calling a static method

- A static method means behaviour of a class does not depend on its instance variables.
```java
public void doSomething() {
  Utilities.formatSomething("5000");
}
```
- You can invoke a static method using its class name(like the example above ```Utilities```) and then calling the desired method
to be used.

```java
public class Duck{
  private int size;
  
  public static void dsplayInfo() {
    System.out.println("Size using 'size' variable" + size); //What instance of a duck does it point to?
    System.out.println("Duck size is: " + getSize()); // Invalid invocation
  }
  
  public int getSize() {
    return size;
  }
}
```
- In static methods you can't use an instance variable and call a non-static method, because it doesn't know what instance of duck does it belongs to.

### Static variable
- The value of the static variables are only shared. Meaning one value per class and not per instance.

```java

public class Duck {
  
  private int size;
  private static duckCount;
  
  public Duck() {
    duckCount++; 
  }
  
  public int getSize() {
    return size;
  }
  
  public int setSize(int size) {
    this.size = size;
  } 
}

```
- The example above counts the ```Duck``` object thats is instantiated. So the counter variable dont go back to 0 since, it relies
on the class variable rather than per instance of a ```Duck``` that is created.

### Final keyword
- The ```final``` keyword is commonly used for declaring a variable that shouldn't be chaned or that is constant.

### Static initializer block and Final keyword

```java

public class Duck{
  private static final int size = 25; 
}

public class Duck{
  private static final int size; 
  
  static{
    size = 25;
  }
}
```
- When you have a variable that is ```static``` and ```final``` it is required to be initialized at ther very start. and it has two ways
of doing it. One is that assign a value to variable that is declared or assign a value to a variable inside a static initializer.
