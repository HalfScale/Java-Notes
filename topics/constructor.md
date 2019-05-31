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
  
  public Duck(int duckSize, String duckName, int duckHeight) {
    size = duckSize;
    name = duckName;
    height = duckHeight;
  }
}
```
- The compiler only writes a constructor for you if you didn't write any constructor at all. So you need to implement a no args
constructor yourself if you write one or more constructors.

### How constructors work

```java
public class Animal {

  public Animal() {
    System.out.println("Creating an animal object"):
  }
}

public class Hippo {

  public Hippo() {
    System.out.println("Creating an hippo object"):
  }
}

public static void main(String[] args) {
  System.out.println("Starting creation..."):
  Hippo hippo = new Hippo();
}
```

```java
output:
Starting creation...
Creating an animal object
Creating an hippo object
```
- During the creation of an object it calls it's superclass constructor and up to the Object class. The process is called constructor chaining.

```java
public class Hippo{
  
  public Hippo() {
    super();
    System.out.println("Creating an hippo object"):
  }
}


public class Hippo{
  
  public Hippo() {
    System.out.println("Creating an hippo object"):
    super(); //Bad thing to do (this won't compile)
  }
}
```
- To call a superclass constructor you will use the ```super()``` keyword.
- Even if you dont write the ```super()``` keyword, the constructor will automatically write it for you.
- You cannot put the ```super()``` keyword underneath of any statement.
- You can also pass some arguments to the ```super()``` if the superclass requires it.
