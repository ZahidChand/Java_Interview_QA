```Java
class Main {
    static {
        System.out.println("Static block executed");
    }
    public static void main(String[] args) {
        System.out.println("Main method executed");
    }
}
```

### Output:
```
Static block executed
Main method executed
```

### Explanation:
In Java, static blocks execute before the main method when the class is loaded into memory. Hence, the static block runs first, followed by the main method.

---

```Java
class Test {
    public void method(Object o) {
        System.out.println("Object method executed");
    }
    public void method(String s) {
        System.out.println("String method executed");
    }
    public static void main(String[] args) {
        Test t = new Test();
        t.method(null);
    }
}
```

### Output:
```
String method executed
```

### Explanation:
Java selects the most specific method when overloaded methods are available. Since `String` is a subclass of `Object`, the `method(String s)` is more specific than `method(Object o)`, so it gets executed.

---

```Java
class Test {
    public static void main(String[] args) {
      Integer a = 128;
      Integer b = 128;
      System.out.println(a==b);
    }
}
```

### Output:
```
false
```

### Explanation:
Integer values greater than 127 are not cached, so `a` and `b` refer to different objects, making `a == b` return `false`.

---

```Java
class Test {
    public static void main(String[] args) {
      try{
          throw new RuntimeException("Exception in try");
      }
      finally{
          System.out.println("Finally block executed");
      }
    }
}
```

### Output:
```
Finally block executed
ERROR!
Exception in thread "main" java.lang.RuntimeException: Exception in try
	at Test.main(Main.java:4)
```

### Explanation:
The `finally` block always executes before the program terminates, even if an exception is thrown.

---

```Java
class Test {
    public static void main(String[] args) {
      final int a;
      a = 10;
      System.out.println(a);
    }
}
```

### Output:
```
10
```

### Explanation:
A `final` variable can be assigned once. Since `a` is assigned before use, no compilation error occurs.

---

```Java
class Parent {
    static void display() {
        System.out.println("Parent executed");
    }
}

class Child extends Parent {
    static void display() {
        System.out.println("Child executed");
    }
}

public class Test {
    public static void main(String[] args) {
        Parent p = new Child();
        p.display();
    }
}
```

### Output:
```
Parent executed
```

### Explanation:
Static methods are not overridden; they are hidden. The reference type determines which method is called.

---

```Java
public class Test {
    public static void main(String[] args) {
       String a = "hello";
       String b = "hello";
       System.out.println(a==b);
    }
}
```

### Output:
```
true
```

### Explanation:
String literals are stored in the string pool, so `a` and `b` refer to the same object.

---

```Java
public class Test {
    public static void main(String[] args) {
       Integer a  = 1000;
       Integer b  = 1000;
       System.out.println(a.equals(b));
       System.out.println(a==b);
    }
}
```

### Output:
```
true
false
```

### Explanation:
`equals()` compares values, while `==` compares references. Large integers are not cached, so `a` and `b` are different objects.

---

```Java
public class Test {
    public static void main(String[] args) {
       Integer a  = 100;
       Integer b  = 100;
       System.out.println(a.equals(b));
       System.out.println(a==b);
    }
}
```

### Output:
```
true
true
```

### Explanation:
Integer values from -128 to 127 are cached, so `a` and `b` refer to the same object.

---

```Java
public class Test extends Thread {
    public void run(){
        System.out.println(Thread.currentThread().getPriority());
    }
    public static void main(String[] args) {
        Test t = new Test();
        t.setPriority(Thread.MAX_PRIORITY);
        t.start();
    }
}
```

### Output:
```
10
```

### Explanation:
`MAX_PRIORITY` is 10, so the thread runs with priority 10.

---

```Java
interface Test{
    int value = 10;
} 
public class Pro {
    public static void main(String[] args) {
        Test.value = 20;
        System.out.println(Test.value);
    }
}
```

### Output:
```
Pro.java:6: error: cannot assign a value to static final variable value
    Test.value = 20;
```

### Explanation:
Interface variables are implicitly `public`, `static`, and `final`, so they cannot be reassigned.

---

```Java
import java.util.HashMap;
public class Test {
    public static void main(String[] args) {
       HashMap<String,Integer> hm = new HashMap<>();
       hm.put(null,10);
       hm.put(null,20);
       System.out.println(hm.get(null));
    }
}
```

### Output:
```
20
```

### Explanation:
HashMap allows `null` keys, and the last inserted value overwrites previous ones.

---

```Java
class Parent{
    public void method(){
        System.out.print("Parent");
    }
}
class Child extends Parent{
    public void method(){
        System.out.print("Child");
    }
}
public class Test {
    public static void main(String[] args) {
      Parent p = new Child();
      p.method();
    }
}
```

### Output:
```
Child
```

### Explanation:
Method overriding ensures that the child class method is called when an instance of `Child` is assigned to a `Parent` reference.

---

```Java
public class Test{
    public static void main(String args[]){
        main(args);
    }
}
```

### Output:
```
Exception in thread "main" java.lang.StackOverflowError
```

### Explanation:
The `main` method calls itself recursively, leading to a `StackOverflowError`.
