# Add `extender` keyword
Its easiest to show this in an example:

```java
// `extender` keyword/type to reference the extending class. Especially useful for libraries where you want to allow method chaining.

// In the lib:

public class Lib {
    public extender libFunc() {
        Lib lib = extender; // Inside this class extender would simply resolve to Lib/this.
        return extender;
    }
}

// In your code, you are now able to extend lib and add functionality, and method chaining doesn't break:

public class MyLib extends Lib {
    public MyLib myFunc() {
        return this;
    }
}

// In Main:

public class Main {
    public static void main() {
        MyLib obj = new MyLib().libFunc().myFunc(); // works due to "extender"
    }
}
```
