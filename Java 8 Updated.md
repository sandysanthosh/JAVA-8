Here are some common Java 8 interview questions along with brief answers:

### 1. **What are the new features introduced in Java 8?**
   - **Lambda Expressions**: Provide a clear and concise way to represent one method interface using an expression.
   - **Functional Interfaces**: Interfaces that have only one abstract method, e.g., `Runnable` or `Comparator`.
   - **Stream API**: Used to process sequences of elements in a functional style.
   - **Optional**: A container class to avoid null pointer exceptions by handling values that may or may not be present.
   - **Default Methods**: Allows methods in interfaces to have a default implementation.
   - **Method References**: Shorthand for lambda expressions to call a method.
   - **New Date-Time API**: Provides an improved, more flexible date and time handling.

### 2. **What is a Lambda Expression, and how is it used in Java 8?**
   - A Lambda Expression is an anonymous function that can be used to implement a method defined by a functional interface in a shorter syntax. Example:
     ```java
     (int x, int y) -> x + y;
     ```

### 3. **What is the Stream API in Java 8?**
   - Stream API allows you to process collections of objects in a functional manner. It supports operations like filter, map, reduce, and collect to perform bulk operations in a declarative style.
   Example:
   ```java
   List<String> list = Arrays.asList("a", "b", "c");
   list.stream().filter(s -> s.startsWith("a")).forEach(System.out::println);
   ```

### 4. **What is a functional interface?**
   - A functional interface is an interface with exactly one abstract method, but it can have any number of default or static methods. It is the basis for lambda expressions. Example:
     ```java
     @FunctionalInterface
     public interface MyFunctionalInterface {
         void execute();
     }
     ```

### 5. **What are default methods in interfaces, and why were they introduced?**
   - Default methods are methods defined in an interface with a default implementation. They allow new methods to be added to interfaces without affecting existing implementations of those interfaces. This helps in backward compatibility.

### 6. **Explain Optional in Java 8.**
   - `Optional` is a container class that may or may not contain a non-null value. It’s used to handle the possibility of null values in a more graceful way, avoiding `NullPointerException`.
     ```java
     Optional<String> name = Optional.ofNullable("John");
     name.ifPresent(System.out::println);
     ```

### 7. **What are method references in Java 8?**
   - Method references are a shorthand syntax for calling methods using `::`. They are often used in conjunction with lambda expressions.
     Example:
     ```java
     List<String> list = Arrays.asList("a", "b", "c");
     list.forEach(System.out::println);
     ```

### 8. **What are the types of method references in Java 8?**
   - **Static Method Reference**: `Class::staticMethod`
   - **Instance Method Reference of a particular object**: `instance::instanceMethod`
   - **Instance Method Reference of an arbitrary object of a particular type**: `Class::instanceMethod`
   - **Constructor Reference**: `Class::new`

### 9. **What is the difference between `map()` and `flatMap()` in Stream?**
   - **map()**: Transforms each element of the stream into another form. It returns a Stream of the same length.
   - **flatMap()**: Transforms each element into a stream and then flattens the streams into one single stream. It is used when you have a collection of collections.

### 10. **Explain the purpose of the `Collectors` class.**
   - The `Collectors` class provides various methods to collect the elements of a stream and convert them into different forms like `List`, `Set`, `Map`, or even concatenated strings.
     Example:
     ```java
     List<String> list = Arrays.asList("a", "b", "c");
     List<String> collected = list.stream().collect(Collectors.toList());
     ```

### 11. **What is the significance of `forEach()` in Java 8?**
   - `forEach()` is a terminal operation used to iterate over elements in a collection or stream and perform some action. It is often used to replace traditional loops.
     ```java
     List<String> list = Arrays.asList("a", "b", "c");
     list.forEach(System.out::println);
     ```

### 12. **What is the difference between `Stream` and `ParallelStream`?**
   - **Stream**: Processes elements sequentially.
   - **ParallelStream**: Divides the given collection into multiple parts, processes them in parallel using multiple threads, and then combines the results.

### 13. **What is the difference between `findFirst()` and `findAny()` in Stream API?**
   - **findFirst()**: Returns the first element from the stream.
   - **findAny()**: Returns any element from the stream, which can be useful for parallel streams where the order does not matter.

### 14. **How does Java 8 solve the problem of diamond operator with anonymous inner classes?**
   - In Java 7, the diamond operator (`<>`) was introduced to avoid redundancy when declaring types. However, it couldn’t be used with anonymous inner classes. In Java 8, this restriction was lifted, allowing diamond syntax in these cases as well.

### 15. **How are `Predicate`, `Consumer`, `Supplier`, and `Function` used in Java 8?**
   - **Predicate**: Represents a boolean-valued function.
     ```java
     Predicate<String> isEmpty = String::isEmpty;
     ```
   - **Consumer**: Represents an operation that accepts a single input argument and returns no result.
     ```java
     Consumer<String> print = System.out::println;
     ```
   - **Supplier**: Represents a supplier of results.
     ```java
     Supplier<Double> random = Math::random;
     ```
   - **Function**: Represents a function that accepts one argument and produces a result.
     ```java
     Function<Integer, Integer> square = x -> x * x;
     ```

Let me know if you need further explanations or additional questions!
