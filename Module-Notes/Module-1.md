# IT201 Java Programming

## Module 1

### Concept of Object Oriented Programming

Object-Oriented Programming (OOP) is a programming paradigm that revolves around the concept of objects, which are instances of classes. Java is an object-oriented programming language, and it heavily relies on the principles of OOP. The main concepts of OOP in Java include:

1. Classes and Objects: A class is a blueprint or template that defines the properties (data) and behaviors (methods) of objects. An object, on the other hand, is an instance of a class. Objects encapsulate data and provide a way to interact with that data through methods.

2. Encapsulation: Encapsulation refers to the bundling of data and methods within a class, where the data is kept private and can only be accessed through public methods. This concept helps in achieving data abstraction and provides data security by hiding the internal implementation details.

3. Inheritance: Inheritance allows classes to inherit the properties and behaviors of other classes. A class that inherits from another class is called a subclass or derived class, while the class being inherited from is called the superclass or base class. In Java, inheritance is implemented using the keyword "extends."

4. Polymorphism: Polymorphism means the ability of an object to take on multiple forms. In Java, polymorphism is achieved through method overriding and method overloading. Method overriding allows a subclass to provide its own implementation of a method already defined in its superclass, while method overloading allows multiple methods with the same name but different parameters in a class.

5. Abstraction: Abstraction involves creating abstract classes and interfaces that define a common interface for a set of subclasses. Abstract classes cannot be instantiated and serve as a blueprint for other classes to inherit from. Interfaces, on the other hand, define a contract that a class must adhere to by implementing its methods.

6. Association, Aggregation, and Composition: These are different types of relationships between classes. Association represents a relationship where objects of one class are connected to objects of another class. Aggregation represents a "has-a" relationship, where one class contains another class as a member, but the contained class can exist independently. Composition is a stronger form of aggregation, where the lifetime of the containing class is dependent on the lifetime of the contained class.

### Features of Java

Java is a powerful and versatile programming language that offers a wide range of features. Here are some key features of Java:

1. Object-Oriented: Java is designed to be object-oriented, which means it supports the concepts of classes, objects, inheritance, encapsulation, and polymorphism. This allows for modular and reusable code, promoting code organization and maintainability.

2. Platform Independence: Java programs can run on any platform that has a Java Virtual Machine (JVM) installed. The JVM acts as an intermediary between the Java code and the underlying hardware, allowing Java programs to be platform-independent.

3. Automatic Memory Management: Java manages memory allocation and deallocation automatically through its garbage collection mechanism. Developers don't need to manually allocate and free memory, reducing the chances of memory leaks and memory-related errors.

4. Strong Standard Library: Java provides a comprehensive standard library that offers a wide range of pre-built classes and APIs for common tasks. This includes libraries for input/output operations, networking, GUI development (Swing and JavaFX), database connectivity (JDBC), multithreading, and more. The standard library saves development time and effort by providing ready-to-use components.

5. Exception Handling: Java has a robust exception handling mechanism, allowing developers to handle and recover from runtime errors and exceptional conditions gracefully. This helps in writing more reliable and fault-tolerant code.

6. Multi-threading: Java supports concurrent programming through its built-in support for multithreading. Multiple threads can run concurrently within a Java program, allowing for efficient utilization of system resources and enabling the development of responsive and scalable applications.

7. Security: Java includes built-in security features, such as a security manager and a sandboxed execution environment, which help in creating secure applications. Java's security model protects against malicious code by enforcing strict access controls and ensuring secure execution of programs.

8. Rich API Documentation: Java has extensive and well-documented APIs, providing detailed documentation for its classes, interfaces, and methods. This makes it easier for developers to understand and utilize the available functionality and promotes code reusability.

9. Community and Ecosystem: Java has a large and active developer community, offering abundant resources, libraries, frameworks, and tools. The ecosystem includes popular frameworks like Spring, Hibernate, and Apache Struts, as well as integrated development environments (IDEs) such as Eclipse, IntelliJ IDEA, and NetBeans.

10. Backward Compatibility: Java strives to maintain backward compatibility, allowing older Java code to run seamlessly on newer versions. This helps in preserving and protecting investments in existing Java applications and libraries.

### How is Java Different from C++

Java and C++ are both popular programming languages, but they have some significant differences in terms of their features, syntax, and design principles. Here are some key differences between Java and C++:

1. Memory Management: One of the major differences between Java and C++ is how they handle memory management. In C++, developers have manual control over memory allocation and deallocation using features like new and delete. On the other hand, Java uses automatic memory management through garbage collection, where the JVM automatically deallocates memory for objects that are no longer referenced. This makes Java less prone to memory leaks and segmentation faults.

2. Platform Independence: Java is designed to be platform-independent. Java code is compiled into bytecode, which can run on any platform with a Java Virtual Machine (JVM). In contrast, C++ code is compiled into machine-specific binaries, requiring separate compilation for different platforms.

3. Object-Oriented Programming: Both Java and C++ are object-oriented languages, but they differ in certain aspects. Java enforces strong object-oriented principles, making all code reside within classes, supporting single inheritance (except for interfaces), and enforcing encapsulation through access modifiers. C++ provides more flexibility in terms of supporting multiple inheritance, allowing direct memory manipulation through pointers, and offering features like operator overloading and friend functions.

4. Exception Handling: Java and C++ have different approaches to exception handling. Java enforces checked exceptions, where all exceptions that a method may throw must be declared in its signature or handled using try-catch blocks. In C++, exception handling is optional and relies on the use of try-catch blocks. C++ also supports a mechanism called RAII (Resource Acquisition Is Initialization), which helps manage resources by automatically invoking destructors.

5. Standard Library: Java has a rich and extensive standard library that provides a wide range of pre-built classes and APIs for common tasks, including networking, I/O, concurrency, GUI development, and more. C++ also has a standard library, but it is generally considered less comprehensive compared to Java's standard library. C++ programmers often rely on external libraries and frameworks to fill the gaps.

6. Performance: C++ is often considered to have better performance than Java in certain scenarios. Since C++ allows direct memory manipulation and has more control over low-level details, it can be more efficient in terms of memory usage and execution speed. Java, on the other hand, provides a layer of abstraction through the JVM, which may introduce some overhead in terms of performance. However, modern JVM implementations have made significant optimizations, narrowing the performance gap between the two languages.

#### Data Types

Java provides several built-in data types to handle different kinds of data. The data types in Java can be categorized into two main groups: primitive data types and reference data types. Here's an overview of the data types in Java:

Primitive Data Types:
1. boolean: Represents a boolean value, either true or false.

    ```java
    boolean isStudent = true;
    ```

2. byte: Represents a 8-bit integer value.

    ```java
    byte number = 10;
    ```

3. short: Represents a 16-bit integer value.

    ```java
    short count = 1000;
    ```

4. int: Represents a 32-bit integer value.

    ```java
    int age = 25;
    ```

5. long: Represents a 64-bit integer value.

    ```java
    long population = 1000000000L;
    ```

6. float: Represents a 32-bit floating-point value.

    ```java
    float temperature = 25.5f;
    ```

7. double: Represents a 64-bit floating-point value.

    ```java
    double pi = 3.14159;
    ```

8. char: Represents a single character (16-bit Unicode character).

    ```java
    char grade = 'A';
    ```


Reference Data Types:
1. Classes: Classes are reference data types that represent objects. They are defined using class definitions and can have properties (data members) and behaviors (methods).

    ```java
    Date today = new Date();
    ```

2. Arrays: Arrays are used to store multiple values of the same type. They can be created for any data type, including primitive and reference types.

    ```java
    int[] numbers = {1, 2, 3, 4, 5};
    ```

3. Interfaces: Interfaces are reference data types that define a contract for classes to implement. They specify a set of methods that a class must provide.

    ```java

    // Define an interface named Shape
    interface Shape {
        double getArea(); // Abstract method
        double getPerimeter(); // Abstract method
    }

    // Implementing the interface in a class
    class Circle implements Shape {
        private double radius;

        public Circle(double radius) {
            this.radius = radius;
        }

        @Override
        public double getArea() {
            return Math.PI * radius * radius;
        }

        @Override
        public double getPerimeter() {
            return 2 * Math.PI * radius;
        }
    }

    class Rectangle implements Shape {
        private double length;
        private double width;

        public Rectangle(double length, double width) {
            this.length = length;
            this.width = width;
        }

        @Override
        public double getArea() {
            return length * width;
        }

        @Override
        public double getPerimeter() {
            return 2 * (length + width);
        }
    }

    // Usage
    public class Main {
        public static void main(String[] args) {
            Shape circle = new Circle(5.0);
            System.out.println("Circle area: " + circle.getArea());
            System.out.println("Circle perimeter: " + circle.getPerimeter());

            Shape rectangle = new Rectangle(4.0, 6.0);
            System.out.println("Rectangle area: " + rectangle.getArea());
            System.out.println("Rectangle perimeter: " + rectangle.getPerimeter());
        }
    }
    ```

4. Enumerations: Enumerations define a fixed set of constants. They are useful for representing a group of related values.

    ```java
    enum DayOfWeek {
        MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY, SUNDAY
    }
    DayOfWeek day = DayOfWeek.MONDAY;
    ```

5. String: Used to store a sequence of characters.

    ```java
    String name = "John";
    ```

Additionally, Java provides the concept of wrapper classes, which are reference types that encapsulate the corresponding primitive types. For each primitive type, there is a corresponding wrapper class that provides useful methods and allows primitive values to be treated as objects. For example, the wrapper class Integer encapsulates the int data type.

```java
Integer number = Integer.valueOf(10);
```

The primitive data types are stored directly in memory, while reference data types are stored as references (memory addresses) that point to the actual object or data in memory.

Java also allows for user-defined data types, where you can create your own classes or structures to represent complex data structures or entities specific to your application.

It's worth noting that Java is a statically-typed language, meaning that variables must have a declared type, and their type cannot change during runtime.

### Identifiers

In Java, identifiers are used to name variables, methods, classes, packages, and other program elements. They serve as unique names to refer to these elements within the program. Here are some rules and examples of using identifiers in Java:

1. Rules for naming identifiers:
   - Must start with a letter (A-Z or a-z), underscore (_), or dollar sign ($).
   - Subsequent characters can be letters, digits (0-9), underscores, or dollar signs.
   - Cannot use reserved keywords as identifiers (e.g., `int`, `class`, `if`).
   - Java is case-sensitive, so `name` and `Name` are different identifiers.

2. Examples of valid identifiers:
   ```java
   int count;
   double averageScore;
   String firstName;
   final int MAX_SIZE = 100;
   Student student1;
   ```

3. Examples of invalid identifiers:
   ```java
   int 123abc;        // Starts with a digit
   float average%age; // Contains special character '%'
   String class;      // Reserved keyword 'class'
   double 4score;     // Starts with a digit
   ```

4. Naming conventions:
   - Class names should start with an uppercase letter and follow CamelCase convention. Example: `Person`, `Student`.
   - Variable and method names should start with a lowercase letter and follow camelCase convention. Example: `firstName`, `calculateAverage()`.
   - Constants should be in all uppercase letters with words separated by underscores. Example: `MAX_SIZE`, `PI_VALUE`.
   - Package names should be in lowercase letters. Example: `com.example.myproject`.

### Arrays

Arrays in Java are used to store a fixed-size sequential collection of elements of the same type. They provide a convenient way to work with multiple values of the same data type. Here's an overview of working with arrays in Java:

1. Declaring an array:
   ```java
   // Syntax: dataType[] arrayName;
   int[] numbers;
   ```

2. Creating an array:
   ```java
   // Syntax: arrayName = new dataType[arraySize];
   numbers = new int[5]; // Creates an array of size 5
   ```

3. Initializing an array:
   ```java
   // Syntax: dataType[] arrayName = {value1, value2, value3, ...};
   int[] numbers = {1, 2, 3, 4, 5}; // Initializes the array with values
   ```

4. Accessing array elements:
   ```java
   // Syntax: arrayName[index];
   int firstNumber = numbers[0]; // Accesses the first element of the array
   ```

5. Modifying array elements:
   ```java
   numbers[1] = 10; // Modifies the second element of the array
   ```

6. Array length:
   ```java
   int size = numbers.length; // Retrieves the length/size of the array
   ```

7. Iterating through an array:
   ```java
   for (int i = 0; i < numbers.length; i++) {
       System.out.println(numbers[i]);
   }
   ```

8. Multi-dimensional arrays:
   ```java
   int[][] matrix = {{1, 2, 3}, {4, 5, 6}, {7, 8, 9}}; // Creates a 2D array
   int value = matrix[1][2]; // Accesses an element in a 2D array
   ```

9. Arraycopy:
   ```java
   int[] source = {1, 2, 3, 4, 5};
   int[] destination = new int[5];
   System.arraycopy(source, 0, destination, 0, source.length); // Copies array elements
   ```

Arrays in Java have a fixed size, which is determined at the time of creation. The elements in an array are accessed using zero-based indexing. It's important to note that arrays are objects in Java, and they provide several methods and properties for working with arrays effectively.

Additionally, Java provides the `java.util.Arrays` class, which offers various utility methods for sorting, searching, and manipulating arrays.

### Operators

Operators in Java are symbols that perform operations on operands (variables, constants, or expressions) and produce a result. Java provides a variety of operators for arithmetic, assignment, comparison, logical, bitwise, and more. Here are some commonly used operators in Java:

1. Arithmetic Operators:
   - Addition: `+`
   - Subtraction: `-`
   - Multiplication: `*`
   - Division: `/`
   - Modulo (Remainder): `%`
   - Increment: `++`
   - Decrement: `--`

2. Assignment Operators:
   - Simple Assignment: `=`
   - Addition Assignment: `+=`
   - Subtraction Assignment: `-=`
   - Multiplication Assignment: `*=`
   - Division Assignment: `/=`
   - Modulo Assignment: `%=`

3. Comparison Operators:
   - Equal to: `==`
   - Not equal to: `!=`
   - Greater than: `>`
   - Less than: `<`
   - Greater than or equal to: `>=`
   - Less than or equal to: `<=`

4. Logical Operators:
   - Logical AND: `&&`
   - Logical OR: `||`
   - Logical NOT: `!`

5. Bitwise Operators:
   - Bitwise AND: `&`
   - Bitwise OR: `|`
   - Bitwise XOR: `^`
   - Bitwise NOT: `~`
   - Left Shift: `<<`
   - Right Shift: `>>`
   - Unsigned Right Shift: `>>>`

6. Conditional (Ternary) Operator:
   - Syntax: `condition ? expression1 : expression2`

7. instanceof Operator:
   - Used to check if an object is an instance of a particular class.
   - Syntax: `object instanceof className`

8. Precedence and Associativity:
   - Operators have different levels of precedence and associativity, determining the order of evaluation in complex expressions.
   - Parentheses can be used to override the default precedence.

### Inheritance

In Java, multilevel inheritance refers to a type of inheritance where a class extends another class, and that subclass becomes the superclass for another class. This creates a hierarchical structure with multiple levels of inheritance. Each subclass inherits the properties and methods of its immediate superclass and adds its own unique characteristics. Here's an example of multilevel inheritance in Java:

```java
// Superclass
class Animal {
    void eat() {
        System.out.println("Animal is eating...");
    }
}

// Subclass inheriting from Animal
class Dog extends Animal {
    void bark() {
        System.out.println("Dog is barking...");
    }
}

// Subclass inheriting from Dog
class Labrador extends Dog {
    void color() {
        System.out.println("Labrador is brown in color.");
    }
}

// Usage
public class Main {
    public static void main(String[] args) {
        Labrador labrador = new Labrador();
        labrador.eat();   // Inherited from Animal class
        labrador.bark();  // Inherited from Dog class
        labrador.color(); // Specific to Labrador class
    }
}
```

In the above example, we have a superclass `Animal` that has a method `eat()`. The `Dog` class extends `Animal` and adds its own method `bark()`. Then, the `Labrador` class extends `Dog` and adds its own method `color()`.

In the `main()` method, we create an object of the `Labrador` class and can access all the inherited methods and the specific method of each class. The `Labrador` object can call `eat()` (inherited from `Animal`), `bark()` (inherited from `Dog`), and `color()` (specific to `Labrador`).

Multilevel inheritance allows us to create a hierarchy of related classes, where each subclass inherits properties and behaviors from its immediate superclass and can further extend them. It promotes code reusability and allows for organizing classes in a logical and structured manner. However, it's important to use inheritance judiciously to avoid excessive complexity and tight coupling between classes.

### Method Overiding

Method overriding in Java allows a subclass to provide its own implementation of a method that is already defined in its superclass. It provides the ability to customize the behavior of inherited methods. To override a method, the subclass must have a method with the same name, return type, and parameters as the superclass method. Here's an example that demonstrates method overriding in Java:

```java
// Superclass
class Animal {
    void makeSound() {
        System.out.println("Animal is making a sound.");
    }
}

// Subclass overriding the makeSound() method
class Cat extends Animal {
    @Override
    void makeSound() {
        System.out.println("Cat is meowing.");
    }
}

// Usage
public class Main {
    public static void main(String[] args) {
        Animal animal = new Animal();
        animal.makeSound(); // Output: "Animal is making a sound."

        Cat cat = new Cat();
        cat.makeSound();    // Output: "Cat is meowing."
    }
}
```

In the above example, we have a superclass `Animal` with a method `makeSound()`. The `Cat` class extends `Animal` and overrides the `makeSound()` method with its own implementation.

In the `main()` method, we create an object of the `Animal` class and call the `makeSound()` method, which executes the implementation defined in the `Animal` class. Then, we create an object of the `Cat` class and call the same method. Since the `Cat` class has overridden the method, the overridden implementation in the `Cat` class is executed.

Key points about method overriding:
- The method in the subclass must have the same name, return type, and parameters as the method in the superclass.
- The `@Override` annotation is optional but recommended for better code readability and to avoid accidental mistakes.
- The method in the subclass should have the same or a more accessible access modifier (e.g., if the superclass method is `public`, the overriding method can be `public` or `protected` but not `private`).
- The subclass method can throw the same, narrower, or no checked exceptions, but it cannot throw broader checked exceptions.
- Method overriding is based on dynamic or runtime polymorphism, where the method implementation to be executed is determined at runtime based on the actual object type.

Method overriding allows subclasses to provide their own behavior while maintaining a consistent interface defined by the superclass. It is a fundamental concept in object-oriented programming and promotes code extensibility and flexibility.

### Abstract Classes

In Java, an abstract class is a class that cannot be instantiated and is meant to be subclassed. It serves as a blueprint for creating derived classes and can contain abstract methods (methods without a body) as well as concrete methods (methods with an implementation). Here's an overview of abstract classes in Java:

1. Declaring an abstract class:
   ```java
   // Syntax: abstract class ClassName { ... }
   abstract class Animal {
       // ...
   }
   ```

2. Abstract methods:
   - Abstract methods are declared without an implementation, using the `abstract` keyword.
   - They are meant to be overridden by the subclasses.
   - Subclasses must provide an implementation for all abstract methods inherited from the abstract superclass.
   ```java
   abstract void makeSound();
   ```

3. Concrete methods:
   - Concrete methods in an abstract class have a complete implementation.
   - Subclasses can inherit and use these methods as-is, without overriding.
   ```java
   void eat() {
       System.out.println("Animal is eating.");
   }
   ```

4. Instantiation:
   - Abstract classes cannot be directly instantiated using the `new` keyword.
   - They are meant to be extended by concrete subclasses.
   ```java
   // Animal animal = new Animal(); // Invalid
   ```

5. Subclassing an abstract class:
   - Subclasses of an abstract class are required to provide implementations for all abstract methods inherited from the superclass.
   - The subclass can also add its own additional methods and fields.
   ```java
   class Cat extends Animal {
       void makeSound() {
           System.out.println("Cat is meowing.");
       }
   }
   ```

6. Usage:
   - Abstract classes can be used as references to objects of their concrete subclasses.
   ```java
   Animal animal = new Cat();
   animal.makeSound(); // Output: "Cat is meowing."
   animal.eat(); // Output: "Animal is eating."
   ```

Abstract classes provide a way to define common behavior and characteristics among a group of related classes while allowing subclasses to customize specific functionality. They act as a template for creating concrete classes and promote code reuse and abstraction. It's important to note that abstract classes can also have fields, constructors, and can be extended by other abstract classes.

### Final Classes

In Java, a final class is a class that cannot be subclassed or extended. Once a class is declared as final, it cannot be inherited by any other class. Here's an overview of final classes in Java:

1. Declaring a final class:
   ```java
   // Syntax: final class ClassName { ... }
   final class FinalClass {
       // ...
   }
   ```

2. Inheritance restriction:
   - A final class cannot be subclassed by any other class.
   - Any attempt to extend a final class will result in a compilation error.
   ```java
   // Example of extending a final class (Invalid)
   // class SubClass extends FinalClass { ... }
   ```

3. Usage of final classes:
   - Final classes are typically used when the design of a class is complete and should not be altered or overridden.
   - They can be used to prevent unintended modifications to critical classes or to ensure specific behavior remains consistent across all instances of the class.

4. Benefits of final classes:
   - Final classes provide security by preventing the creation of subclasses that may alter or override critical behavior.
   - They guarantee the immutability and integrity of the class's implementation.
   - Final classes can be optimized by the compiler for better performance.

5. Examples of final classes in Java:
   - Some examples of final classes in Java include `java.lang.String`, `java.lang.Integer`, and `java.lang.Math`.
   - These classes are declared as final to ensure that their behavior remains consistent and cannot be modified through subclassing.

It's important to note that while a class can be declared final, individual methods and variables within that class can still be declared non-final, allowing for further customization or extension of specific members while maintaining the overall integrity of the class.

### String Class

In Java, the `String` class is a built-in class that represents a sequence of characters. It is widely used for manipulating and storing textual data. The `String` class is part of the `java.lang` package, which is automatically imported into every Java program. Here's an overview of the `String` class in Java:

1. Creating a `String` object:
   - There are multiple ways to create a `String` object:
     ```java
     String str1 = "Hello"; // Using string literal
     String str2 = new String("World"); // Using the "new" keyword
     ```

2. String immutability:
   - Once a `String` object is created, it cannot be changed (immutable).
   - Operations on strings, such as concatenation or substring, result in the creation of new `String` objects.
   ```java
   String greeting = "Hello";
   greeting = greeting + " World"; // Creates a new String object
   ```

3. String methods:
   - The `String` class provides numerous methods to manipulate and work with strings, including:
     - Retrieving the length: `int length()`
     - Concatenating strings: `String concat(String str)`
     - Extracting substrings: `String substring(int beginIndex)` or `String substring(int beginIndex, int endIndex)`
     - Converting case: `String toLowerCase()` or `String toUpperCase()`
     - Checking for equality: `boolean equals(Object obj)` or `boolean equalsIgnoreCase(String str)`
     - Finding characters and substrings: `int indexOf(int ch)` or `int indexOf(String str)`
     - Splitting a string: `String[] split(String regex)`
     - Replacing characters or substrings: `String replace(char oldChar, char newChar)` or `String replace(CharSequence target, CharSequence replacement)`
     - And many more...

4. String comparison:
   - String comparison can be performed using the `equals()` method or the `compareTo()` method.
   - The `equals()` method checks for content equality, while the `compareTo()` method compares lexicographically.
   ```java
   String str1 = "Hello";
   String str2 = "Hello";
   boolean isEqual = str1.equals(str2); // true
   int comparison = str1.compareTo(str2); // 0
   ```

5. String formatting:
   - The `String` class supports formatting capabilities through the `format()` method, similar to the `printf()` method in C.
   ```java
   String formattedString = String.format("Name: %s, Age: %d", name, age);
   ```

6. StringBuilder and StringBuffer:
   - For efficient manipulation of strings, especially when concatenating or modifying them frequently, Java provides the `StringBuilder` and `StringBuffer` classes. They offer mutable alternatives to the immutable `String` class.

The `String` class is extensively used in Java programs for working with text-based data. Its immutability ensures the integrity and safety of string manipulation operations.

### Difference between Applet and Application

Here's a comparison between Java applets and Java applications:

|                    | Java Applet                                                    | Java Application                                               |
|--------------------|----------------------------------------------------------------|---------------------------------------------------------------|
| Execution         | Runs inside a web browser as part of a web page (HTML document) | Runs as a standalone program on the desktop or server          |
| Entry Point        | `init()` method                                               | `main()` method                                               |
| User Interface     | Limited user interface capabilities                            | Can have a full-fledged user interface                         |
| Deployment         | Requires embedding in an HTML document and hosted on a web server | Distributed as a JAR file or executable and installed locally |
| Security Model    | Restricted by the Java Applet Security Manager                 | Not subject to the same security restrictions                 |
| Network Access    | Restricted network access (subject to applet sandbox)         | Can freely access network resources                           |
| Interaction       | Can interact with HTML elements on the web page                | Can interact with the operating system and file system        |
| Accessibility      | Restricted access to system resources                          | Full access to system resources                               |
| Usage            | Less common in modern web development due to security concerns and limited capabilities | Widely used for desktop applications, server-side applications, and more |

It's important to note that Java applets have significantly declined in popularity and usage due to security concerns and the advancement of web technologies. Modern web development predominantly relies on other technologies like JavaScript, HTML5, and CSS for client-side functionality. Java applications, on the other hand, continue to be widely used for various purposes, including desktop applications, server-side applications, enterprise systems, and more.

### Runtime Polymorphism

Runtime polymorphism, also known as dynamic polymorphism, is a feature of object-oriented programming languages like Java. It allows a subclass to provide its own implementation of a method that is already defined in its superclass, and the appropriate method is determined at runtime based on the actual object type. Here's an explanation of runtime polymorphism in Java:

1. Superclass and Subclass Relationship:
   - There must be a superclass and one or more subclasses involved.
   - The superclass contains a method that can be overridden by its subclasses.

2. Method Overriding:
   - The subclass must override the method defined in the superclass.
   - The method in the subclass should have the same name, return type, and parameters as the method in the superclass.
   - The `@Override` annotation is optional but recommended for better code readability.

3. Upcasting:
   - The subclass object can be upcasted to the superclass type.
   - This means a reference variable of the superclass can refer to an object of the subclass.
   - This allows for treating different subclasses as instances of the common superclass.

4. Dynamic Method Dispatch:
   - The method to be executed is determined dynamically at runtime based on the actual object type.
   - When a method is called on a superclass reference variable that points to a subclass object, the overridden method in the subclass is executed.

Here's an example to illustrate runtime polymorphism in Java:

```java
// Superclass
class Animal {
    void makeSound() {
        System.out.println("Animal is making a sound.");
    }
}

// Subclass
class Cat extends Animal {
    @Override
    void makeSound() {
        System.out.println("Cat is meowing.");
    }
}

// Subclass
class Dog extends Animal {
    @Override
    void makeSound() {
        System.out.println("Dog is barking.");
    }
}

// Usage
public class Main {
    public static void main(String[] args) {
        Animal animal1 = new Cat(); // Upcasting
        Animal animal2 = new Dog(); // Upcasting

        animal1.makeSound(); // Output: "Cat is meowing."
        animal2.makeSound(); // Output: "Dog is barking."
    }
}
```

In the example, we have a superclass `Animal` with a method `makeSound()`. The subclasses `Cat` and `Dog` override the `makeSound()` method with their own implementations.

In the `main()` method, we create objects of the `Cat` and `Dog` classes and assign them to `Animal` reference variables (`animal1` and `animal2`). When the `makeSound()` method is called on these reference variables, the appropriate overridden method in the respective subclass is executed. This is determined dynamically at runtime based on the actual object type.

Runtime polymorphism allows for code flexibility, extensibility, and code reuse. It enables the implementation of polymorphic behavior, where different objects can exhibit different behaviors based on their specific types, even though they are accessed through a common superclass reference.

### Lambda Expression

Lambda expressions were introduced in Java 8 and provide a concise way to represent anonymous functions or "function literals." They allow you to write more compact and expressive code by treating functions as method arguments or return values. Here's an explanation of lambda expressions in Java:

1. Syntax:
   - Lambda expressions are defined using the following syntax:
   ```
   (parameters) -> expression
   ```
   or
   ```
   (parameters) -> { statements; }
   ```

2. Functional Interfaces:
   - Lambda expressions are used in conjunction with functional interfaces, which are interfaces with a single abstract method.
   - Functional interfaces provide the target type for lambda expressions, specifying the type of the parameter(s) and the return type.
   - Java provides built-in functional interfaces such as `Runnable`, `Comparator`, `Predicate`, `Consumer`, `Function`, and more.

3. Examples:
   - Lambda expressions can be used in various contexts, such as:
     - Runnable example:
     ```java
     Runnable runnable = () -> System.out.println("Hello, Lambda!");
     ```

     - Comparator example:
     ```java
     List<String> names = Arrays.asList("John", "Alice", "Bob", "David");
     Collections.sort(names, (a, b) -> a.compareTo(b));
     ```

     - Predicate example:
     ```java
     List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);
     List<Integer> evenNumbers = numbers.stream()
                                        .filter(n -> n % 2 == 0)
                                        .collect(Collectors.toList());
     ```

4. Benefits:
   - Concise syntax: Lambda expressions allow you to express behavior in a more compact and readable manner, reducing boilerplate code.
   - Improved code readability: Lambda expressions make code more expressive by focusing on the behavior or functionality being passed.
   - Enhanced functional programming: Lambda expressions facilitate the adoption of functional programming concepts and enable more functional-style programming in Java.

5. Restrictions:
   - Lambda expressions can only be used with functional interfaces.
   - The target type should have a single abstract method (SAM - Single Abstract Method) to match the lambda expression.

Lambda expressions bring functional programming constructs to Java and provide a more expressive way of writing code that involves passing behavior as data. They have become an essential feature in modern Java development, especially when working with collections, streams, and concurrent programming.