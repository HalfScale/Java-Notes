# Method overriding
- Is the ability of a subclass to change the original implementation of a method from a superclass.
- When you are overriding a method from a superclass, you're agreeing to fulfull the contract. The methods are the contract.
- Arguements and return types of your overriding method should be the same with it's superclass method to be overridden 

```java
public class Animal {
  
  public void makeNoise() {
    System.out.println("Animal making noise");
  }
}

public class Dog {
  
  public void makeNoise() {
    System.out.println("Arf Arf!");
  }
}

public static void main (String[] args) {
  Dog dog = new Dog();
  dog.makeNoise(); // Dog overiding the makeNoise() method
}
```
```
output:
Arf Arf!
```
- The example above demonstrates how a **Dog class** changes the implementation of ```makeNoise()``` method that is inhereted from its 
superclass(**Animal class**)

### Super keyword

```java
public class Animal {
  
  public void makeNoise() {
    System.out.println("Animal making noise");
  }
}

public class Dog {
  
  public void makeNoise() {
    super.makeNoise(); // notice this statement
    System.out.println("Arf Arf!");
  }
}

public static void main (String[] args) {
  Dog dog = new Dog();
  dog.makeNoise();
}
```
```
output:
Animal making noise
Arf Arf!
```
- The example above demonstrates how to retain the default implementation of subclass method while calling it's superclass method.
- The word ```super``` is denoted as the superclass(**Animal class**) while calling its method ```makeNoise()```
