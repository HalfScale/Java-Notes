# Object Equality

### Reference equality
- Two references, one object on the heap.
- Two references that refer to the same object on the heap are equal.
 - use the ```==``` operator, if you want to know if two references are really refering to the same object, which (remember) compares the bits variables.

### Object equality
- Two references, two objects on the heap but the objects are considered meaningfully equal.
- If you want to treat objects as equal (for example you decided that Song objects can only be equal if they have a matching title variable) you must override both **equal()** and **hashCode()** methods inherited from class Object.

![](../img/java/objectEquality1.PNG)

*This image is from Head First Java Book*

- The image above demonstrates why we should override both **equal()** and **hashCode()** method.

#### Java Object law for hashCode() and equals()

- If two objects are equal, they must have matching hashcodes.
- If two objects are equal, calling **equals()** on either object must return true. In other words if a.equals(b) then b.equals(a).
- If two objects have the same hashcode value, they are not required to be equal. But if they're equal, they must have the same hashcode value.
- So if you override **equals()**, you must override **hashCode()**
- The default behaviour of **hashCode()** is to generate a unique integer for each object on the heap. So if you don't override hashCode() in a class, no two objects of that type can ever be considered equal.
- The default behaviour of an **equals()** is to do an == comparison. In other words, to test wether the two references refer to a single object on the heap. so if you dont ovveride an **equals()** in a class, no two objects can ever be considered equal since references to two different objects will always contain different bit pattern.

#### Examples
[Why do I need to override the equals and hashCode methods in Java?](https://stackoverflow.com/questions/2265503/why-do-i-need-to-override-the-equals-and-hashcode-methods-in-java)
