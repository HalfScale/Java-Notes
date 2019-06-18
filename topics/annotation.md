# Annotations
- A form of metadata, provide data about a program that is not part of the program itself. Annotations have no direct effect on 
the operation of the code they annotate.

### Usages

```java
@Entity
```
- It's simplest form

```java
@Override
public void myAwesomeMethod() {...}
```
- ```@Override``` is commonly used for methods to overide it's parent method.

```java
@Author(
   name = "Benjamin Franklin",
   date = "3/27/2003"
)

// or

@SuppressWarning( value= "unchecked")
void myMethod() {...}
```
- Annotations can include elements, which can be named or unamed, and there are value for those element

```java
@SuppressWarning("unchecked")
void myMethod() {...}
```
- If its just one element named value, then the name can be omitted
