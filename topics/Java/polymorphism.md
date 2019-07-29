# Polymorphism

- The ability of an object to have many forms.

```java
// normal instantiation
Dog dog = new Dog();
Cat cat = new Cat();

dog.makeSound();
cat.makeSound();

// with polymorphism

Animal dog = new Dog();
Animal cat = new Cat();

dog.makeSound();
cat.makeSound();
```
- With polymorphism you can assign to a reference variable its subclass type. As long as it extends the type that was given in the 
reference variable.

```java
public class Animal{
  
  public void eat() {
    // eat code here...
  }
  
  public void roam() {
    // roam code here...
  }
}

public class Dog extends Animal {
  public void bark() {
    // dog bark code here...
  }
}

public static void main(String[] args) {
  Animal dog = new Dog();
  dog.bark(); // Wont work!
  
  Dog myDog = new Dog();
  myDog.bark(); // this will work.
}
```
- Even though the you know that the ```Animal``` reference is refering to a ```Dog``` object, The compiler only looks at
the type reference variable(Animal) if the method you're calling is available. Since the ```Animal``` class does not have
the bark method, the statement above will not work.
