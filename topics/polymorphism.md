# Polymorphism

- The ability of an object to have many types of forms.

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
