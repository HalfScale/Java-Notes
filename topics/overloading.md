# Method Overloading
- Is having two or more methods with the same name but with different arguements.
- Overloading has nothing to do with inheritance and polymorphism.

```java
public class Overloads {

  String uniqueId;
  
  public int addNums(int a, int b) {
    return a + b;
  }
  
  public double addNums(double a, double b) {
    return a + b;
  }
  
  public void setUniqueId(String theID) {
    uniqueId = theId;
  }
  
  public void setUniqueId(int ssNumber) {
    String numString = "" + ssNumber;
    setUniqueId(numString);
  }
}
```
