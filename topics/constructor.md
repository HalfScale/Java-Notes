# Constructor

```java
public class Duck {
  
  //Constructor with empty args
  public Duck() {
    //initialize values here
  }
}

public static void main(String[] args) {
  //
  Duck duck = new Duck();
}
```
- The code that runs when you instantiate an object using the ```new``` keyword
- Every class has constructor even if you dont write it yourself. The compiler writes are one for you.
- The key feature of a constuctor is that it runs before the object can be assigned to a reference. In other words the object
can run code its code before it can be used.

### Overloaded Constructors

```java
public class Duck{
  int size;
  String name;
  int height;
  
  //constructor with no args.
  public Duck() {
    size = 27;
    name = "Duck"
    height = 4
  }
  
  //constructor with args.
  public Duck(int duckSize) {
    size = duckSize;
  }
  
  public Duck(duckSize, duckName, duckHeight) {
    size = duckSize;
    name = duckName;
    height = duckHeight;
  }
}
```
- The compiler only writes a constructor for you if you didn't write any constructor at all. So you need to implement a no args
constructor yourself if you write one or more constructors.
