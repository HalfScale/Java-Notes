# Objects and Java Garbage Collection
- An object's life depeneds on it's live references
- A local variable lives only within the method that declared the variable.
- An instance variable lives as long as the object does. If the object is still alive, so are its instance variable.

### Garbage collection
- You can make an object eligible for garbage collection if the object has no references to it.
```java

// sample 1
public void go() {
  Life life = new Life();
}

// sample 2
Life life = new Life();
life = new Life();

// sample 3
Life life = new Life();
life = null;


```
- On **Sample 1** The object dies if the method execution reaches the end of the curly brace(or end of the method).
- On **Sample 2** The first ```Life``` object dies because it is reprogrammed to another new ``Life``` Object.
- On **Sample 3** The first ```Life``` object dies because the reference to it is removed and assigned to nothing(*null*).
