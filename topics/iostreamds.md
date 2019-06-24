# I/O Streams
- Represents an input source or an output destination.
- Different kinds of sources and destinations, disk files, devices, other programs and memory arrays.
- A stream is a **sequence of data**.

### Basic I/O implementation.

```java
public static void main (String[] args) {
  FileInputStream in = null;
  FileOutputStream out = null;
  
  try {
    in = new FileInputStream("E:\\test files io\\xandu.txt");
    out = new FileOutputStream("E:\\test files io\\new_xandu.txt");
    
    int c;
    
    while((c = in.read) != null) {
      out.write(c);
    }
    
  }finally {
    //Always close streams to avoid errors.
    if(in != null) {
      in.close();
    }
    
    if(out != null) {
      out.close();
    }
  }
  
}
```
- This kind of stream is only used for low level files or sources.(byte streams should only be used for the most primitive I/O).
