# Primitives and Wrapper Class

### Primitives
- byte, short, int, long, float, double, boolean, char
- A **null** value canno't be assigned to primitives

### Wrapper Class
- A wrapper class in an object that encapsulates a primitive type.
- Coresponding wrapper class for primitives **Byte(byte)**, **Short(short)**, **Integer(int)**, **Long(long)**, **Float(float)**, **Double(double)**, **Boolean(boolean)**, **Character(char)**
- Since a wrapper class is an object their default values will be null if not assigned.
- All primitives wrapper objects are final in java, which means they are immutable.

## Autoboxing and Unboxing

### Autoboxing
- Introduced in Java 5.0, Autoboxing is the automatic conversion of primitive types to their corresponding object wrapper class.

```java
List<Integer> numbers = new ArrayList<>();

for(int i = 0; i < 10; i++) {
  numbers.add(i);
}
```
- Since primitive types cannot be used in Collections or Generics, each time ```i``` is added to ```numbers``` a new Integer object is created.

### Unboxing
- Likewise, unboxing is the automatic conversion of object wrapper types into their corresponding primitive types.

```java
Integer a = new Integer(5);
int b = a;
```
- The compiler recognizes that unboxing is needed and does it automatically for you. Be careful, this automatic conversion causes performance issues and unexpected behaviour.

### Dangers of Autoboxing and Unboxing
- Autoboxing and Unboxing can cause performance to suffer by creating intermediate objects which creates more work for the Garbage Collector.

Example

```java
public class Example {
  private static Integer count = 0;
  
  public static void main(String[] args) {
    for(int i = 0; i < 1000; i++) {
      count += 1;
    }
  }
}
```

*Behind the scenes*
- ```count += 1``` is transformed into ```count = count + 1```
- Since count is a wrapper type, it must be unboxed into it's int value.
- The int value of ```count``` is added to 1 to produce a new int.
- The new primitive is assigned back to count, which is a wrapper type, so the compiler creates a new Integer object to assign back to the variable ```count```

- The loop will create 1000 integer object in memory. Those objects will need to be garbage collected later. This will have servere impact on the performance of your program.
