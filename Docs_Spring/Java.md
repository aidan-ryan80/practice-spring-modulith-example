# Moving from Python to Java
### Differences
##### General Differences
- Java is statically typed
- Java is compiled to Bytecode for the Java Virtual Machine (JVM)
##### Examples of Python vs Java

| **Task**            | **Python**            | **Java**                                     |
| ------------------- | --------------------- | -------------------------------------------- |
| **Print**           | `print("Hello")`      | `System.out.println("Hello");`               |
| **List/Array**      | `my_list = [1, 2, 3]` | `List<Integer> list = List.of(1, 2, 3);`     |
| **Dictionary/Map**  | `my_dict = {"a": 1}`  | `Map<String, Integer> map = Map.of("a", 1);` |
| **Null check**      | `if x is None:`       | `if (x == null) { ... }`                     |
| **For Loop**        | `for i in range(10):` | `for (int i = 0; i < 10; i++) { ... }`       |
| **Function/Method** | `def my_func(x):`     | `public int myMethod(int x) { ... }`         |

##### Structural Differences
- **Access Modifiers:** private, protected, and public are hard rules enforced by the compiler (will help in keeping modules decoupled)
- **Interfaces:** defines what a module can do without revealing how it does it
- **Stream API:** Java's version of comprehensions. Stream is a "pipe" of data that flows from a source to a destination

### Java Commands
##### Run a Java program with the Java Virtual Machine
```bash
java -jar target/<jar-name>.jar
```
