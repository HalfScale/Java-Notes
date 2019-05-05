# Methods in Java

### Declaration 

```java
public String getName() {
  return "My name";
}
```
- ```public``` stands for the access type of the method.
- ```String``` stands for the what will the method return to the caller.
- ```getName()``` is mostly the named of the method which is user defined.
- ```{ }``` is the body of them method where you will make your statements.

### Parameters and Arguements of a method

```java
public class Main {
  
  public static void main(String[] args) {
  
    //Variable to be passed to the parameter of the method (Arguement)
    int myFavoriteNum = 16; 
    
    printNumber(myFavoriteNum);
  }
  
  public void printNumber(int num) {
    //variable 'num' is the parameter that the method takes.
    System.out.println("Number: " + num);
  }
}
```

- **Parameters** are the one that the method takes. While **Arguements** are the one that you pass in the method parameter.

### Pass by value/copy

```java
public class Main {
  public static void main(String[] args) {
    int x = 7;
    go(x);
  }

  public void go(int z) {
    z = 0;
  }
}
```
- Passing the variable ```x``` as the arguement. The bits in ```x``` are copied and the copy lands on ```z```
- The value of ```z``` inside of the method is changed. But the variable ```x``` is not affected by the change since
the ```x``` variable only passes the copy of its bits and not the actual reference.
