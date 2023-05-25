#IT201 Java Programming

## Module 2

### Defining Packages

In Java, packages provide a way to organize related classes, interfaces, and resources into a single unit. Packages help avoid naming conflicts, improve code maintainability, and provide a clear hierarchical structure. Here's an explanation of defining packages in Java:

1. Package Declaration:
   - At the top of each Java source file, you can declare the package to which the file belongs.
   - The package declaration should be the first non-comment line in the source file.
   - Example of package declaration:
     ```java
     package com.example.myapp;
     ```

2. Package Naming Convention:
   - Packages are typically named using a hierarchical naming convention.
   - Package names are written in lowercase, and multiple words are separated by periods (`.`).
   - The convention is to use the reverse domain name of the organization as the package prefix.
   - Example of package naming convention:
     ```
     com.example.myapp
     ```

3. Package Structure:
   - Packages can have a hierarchical structure, with sub-packages within a package.
   - Sub-packages can be created by creating directories corresponding to the package names.
   - Example of package structure:
     ```
     com
     └── example
         └── myapp
             ├── MyClass.java
             └── MyInterface.java
     ```

4. Importing Packages:
   - To use classes or interfaces from other packages, you need to import them using the `import` statement.
   - The import statement is typically placed at the beginning of the Java source file, after the package declaration.
   - Example of importing a package:
     ```java
     import com.example.otherpackage.OtherClass;
     ```

   - You can also use the wildcard (`*`) to import all classes and interfaces from a package.
   - Example of wildcard import:
     ```java
     import com.example.otherpackage.*;
     ```

Defining packages in Java helps in organizing and managing related classes and interfaces. It allows for better code organization, reusability, and reduces the chances of naming conflicts. By following the package naming convention and creating a hierarchical structure, you can create a clear and logical structure for your Java project.


### Implementing Packages

Implementing packages in Java involves creating the directory structure and organizing the source files within those directories to match the package structure. Here's a step-by-step guide to implementing packages in Java:

1. Create the Package Directory Structure:
   - Determine the package name and follow the naming convention (e.g., `com.example.myapp`).
   - Create a directory for each segment of the package name, starting from the root directory of your project.
   - Example command to create directories:
     ```
     mkdir -p com/example/myapp
     ```

2. Place Source Files in the Corresponding Package Directory:
   - Move or create the Java source files into the appropriate package directory based on their package declaration.
   - The package declaration in the source file should match the package name.
   - Example:
     ```
     com
     └── example
         └── myapp
             ├── MyClass.java
             └── MyInterface.java
     ```

3. Add Package Declarations in Source Files:
   - Open each source file and add the package declaration at the top, matching the directory structure.
   - Example of package declaration in source files:
     ```java
     package com.example.myapp;
     ```

4. Compile and Build the Project:
   - Compile the source files using the `javac` command, ensuring that the package directory structure is preserved.
   - Example command to compile Java files in a package:
     ```
     javac -d <output_directory> <source_files>
     ```

5. Import Packages and Use Classes:
   - In your Java source files, import the required packages using the `import` statement.
   - Use the imported classes and interfaces from the packages in your code as needed.
   - Example of importing a package and using a class:
     ```java
     import com.example.myapp.MyClass;

     public class Main {
         public static void main(String[] args) {
             MyClass myObj = new MyClass();
             // Use myObj and other classes/interfaces from the package
         }
     }
     ```

#### Applying Packages

Applying packages in Java involves using classes and interfaces from different packages within your Java code. Here's a step-by-step guide on how to apply packages in Java:

1. Importing Packages:
   - Identify the packages containing the classes or interfaces you want to use in your code.
   - Import the required packages using the `import` statement at the top of your Java source file.
   - Example of importing a package:
     ```java
     import com.example.myapp.package1.ClassA;
     import com.example.myapp.package2.ClassB;
     ```

   - You can import specific classes/interfaces or use the wildcard (`*`) to import all classes/interfaces from a package.
   - Example of using the wildcard import:
     ```java
     import com.example.myapp.package1.*;
     ```

2. Using Imported Classes and Interfaces:
   - Once the packages are imported, you can create objects of the imported classes or use the imported interfaces in your code.
   - Example of using imported classes and interfaces:
     ```java
     public class Main {
         public static void main(String[] args) {
             ClassA objA = new ClassA();
             objA.methodA();

             ClassB objB = new ClassB();
             objB.methodB();
         }
     }
     ```

   - You can access the methods, variables, and other members of the imported classes/interfaces using the object references.

3. Compiling and Running the Code:
   - Compile the Java source file using the `javac` command, ensuring that the necessary packages are included in the classpath.
   - Example command to compile Java files with package dependencies:
     ```
     javac -cp .;<path_to_packages> Main.java
     ```

   - Run the compiled code using the `java` command, specifying the fully qualified name of the class containing the `main` method.
   - Example command to run the code:
     ```
     java -cp .;<path_to_packages> Main
     ```

By importing the required packages and using the classes and interfaces from those packages, you can apply packages in your Java code. This allows you to access functionality from different packages, enhance code organization, and avoid naming conflicts.

### Defining Interfaces

Defining interfaces in Java involves creating a contract or a set of methods that implementing classes must adhere to. Interfaces define the behavior that implementing classes should provide. Here's a step-by-step guide on how to define interfaces in Java:

1. Declare the Interface:
   - Start by declaring the interface using the `interface` keyword.
   - Interface names are typically written in CamelCase and should be descriptive of the behavior they represent.
   - Example of interface declaration:
     ```java
     public interface MyInterface {
         // Interface methods will be defined here
     }
     ```

2. Define Interface Methods:
   - Inside the interface, define the methods that implementing classes must implement.
   - Interface methods are declared without an implementation (no method body) and without the `public` or `private` modifiers.
   - Example of defining an interface method:
     ```java
     public interface MyInterface {
         void myMethod();
     }
     ```

3. Add Constants (Optional):
   - Interfaces can also define constants, which are typically declared as `public static final` variables.
   - Constants in interfaces are implicitly `public`, `static`, and `final`, so those modifiers are not required to be explicitly specified.
   - Example of adding a constant in an interface:
     ```java
     public interface MyInterface {
         int MAX_VALUE = 100;
     }
     ```

4. Extend Other Interfaces (Optional):
   - Interfaces can extend other interfaces to inherit their method declarations.
   - Use the `extends` keyword followed by the interface(s) to be extended.
   - Example of extending an interface:
     ```java
     public interface MyExtendedInterface extends InterfaceA, InterfaceB {
         // Additional method declarations can be added here
     }
     ```

5. Implementing Interfaces:
   - Classes that implement an interface must use the `implements` keyword and provide an implementation for all the methods defined in the interface.
   - Example of implementing an interface in a class:
     ```java
     public class MyClass implements MyInterface {
         public void myMethod() {
             // Method implementation goes here
         }
     }
     ```

6. Using Interfaces:
   - Interfaces are typically used as types for object references or as method parameters and return types.
   - Example of using an interface as a type:
     ```java
     MyInterface obj = new MyClass();
     obj.myMethod();  // Method call on the interface reference
     ```

By defining interfaces in Java and implementing them in classes, you can establish a contract for behavior that classes must adhere to. Interfaces allow for abstraction and polymorphism in Java, enabling code to be written against the interface type rather than specific implementation classes. This promotes loose coupling and flexibility in designing systems.


### Implementing Interfaces

Implementing interfaces in Java involves creating classes that provide the implementation for the methods declared in the interface. Here's a step-by-step guide on how to implement interfaces in Java:

1. Declare the Interface:
   - Start by declaring the interface that you want to implement (already defined in a separate interface file).
   - Example interface declaration:
     ```java
     public interface MyInterface {
         void myMethod();
     }
     ```

2. Create a Class:
   - Create a class that implements the interface using the `implements` keyword.
   - Example class declaration implementing the interface:
     ```java
     public class MyClass implements MyInterface {
         // Implement interface methods here
     }
     ```

3. Implement Interface Methods:
   - In the implementing class, provide the implementation for all the methods declared in the interface.
   - The methods must have the same signature (name and parameters) as defined in the interface.
   - Example implementation of the interface method:
     ```java
     public class MyClass implements MyInterface {
         public void myMethod() {
             // Provide the implementation for the method
             System.out.println("Hello, World!");
         }
     }
     ```

4. Use the Implementing Class:
   - Create objects of the implementing class and use the implemented interface methods.
   - Example of using the implementing class:
     ```java
     public class Main {
         public static void main(String[] args) {
             MyClass obj = new MyClass();
             obj.myMethod();  // Call the implemented method
         }
     }
     ```

5. Implement Multiple Interfaces (Optional):
   - A class can implement multiple interfaces by separating them with commas.
   - Provide implementations for all methods declared in each interface.
   - Example of implementing multiple interfaces:
     ```java
     public class MyClass implements InterfaceA, InterfaceB {
         // Implement methods from both interfaces
     }
     ```

By implementing interfaces in Java, you ensure that the implementing classes adhere to the contract defined by the interface. This allows for polymorphism, where objects of implementing classes can be treated as instances of the interface type. It also promotes code reusability and flexibility by allowing different implementations of the same interface.

### Applying Interfaces

Applying interfaces in Java involves using interfaces to define the behavior that classes should implement. Here's a step-by-step guide on how to apply interfaces in Java:

1. Declare the Interface:
   - Start by declaring the interface that defines the required methods.
   - Example interface declaration:
     ```java
     public interface MyInterface {
         void myMethod();
     }
     ```

2. Implement the Interface:
   - Create a class that implements the interface using the `implements` keyword.
   - Example class declaration implementing the interface:
     ```java
     public class MyClass implements MyInterface {
         // Implement interface methods here
     }
     ```

3. Implement Interface Methods:
   - In the implementing class, provide the implementation for all the methods declared in the interface.
   - The methods must have the same signature (name and parameters) as defined in the interface.
   - Example implementation of the interface method:
     ```java
     public class MyClass implements MyInterface {
         public void myMethod() {
             // Provide the implementation for the method
             System.out.println("Hello, World!");
         }
     }
     ```

4. Use the Interface Type:
   - Use the interface type to create objects and reference them.
   - Example of using the interface type:
     ```java
     public class Main {
         public static void main(String[] args) {
             MyInterface obj = new MyClass();  // Create object using interface type
             obj.myMethod();  // Call the interface method
         }
     }
     ```

5. Polymorphism with Interfaces:
   - Interface types can be used to achieve polymorphism by treating objects of different implementing classes as instances of the interface type.
   - Example of polymorphic behavior using interfaces:
     ```java
     MyInterface obj1 = new MyClass1();
     MyInterface obj2 = new MyClass2();
     
     obj1.myMethod();  // Calls the implementation in MyClass1
     obj2.myMethod();  // Calls the implementation in MyClass2
     ```

By applying interfaces in Java, you define a contract for classes to implement specific behavior. This allows for loose coupling, code abstraction, and flexibility in designing systems. Interfaces provide a way to achieve polymorphism and facilitate code reuse by enabling different implementations of the same interface.


### Importing Packages

Importing packages in Java allows you to access classes and interfaces from other packages in your code. Here's how you can import packages in Java:

1. Single-Class Import:
   - To import a specific class or interface from a package, use the `import` statement followed by the fully qualified name of the class or interface.
   - Example of importing a specific class:
     ```java
     import com.example.myapp.MyClass;
     ```

   - Example of importing a specific interface:
     ```java
     import com.example.myapp.MyInterface;
     ```

2. Wildcard Import:
   - To import all the classes and interfaces from a package, you can use the wildcard (`*`) character.
   - Example of importing all classes and interfaces from a package:
     ```java
     import com.example.myapp.*;
     ```

   - This imports all the classes and interfaces from the `com.example.myapp` package but does not import classes from its sub-packages.

3. Using Imported Classes and Interfaces:
   - After importing the required classes or interfaces, you can use them in your code directly by referencing their simple names.
   - Example of using an imported class:
     ```java
     MyClass obj = new MyClass();
     ```

   - Example of using an imported interface:
     ```java
     public class MyImplementation implements MyInterface {
         // Implement methods from MyInterface
     }
     ```

4. Compiling and Running the Code:
   - To compile the Java source file that uses imported packages, use the `javac` command and specify the classpath including the necessary packages.
   - Example command to compile the code:
     ```
     javac -cp .:<path_to_packages> MyClass.java
     ```

   - To run the compiled code, use the `java` command and specify the classpath including the necessary packages.
   - Example command to run the code:
     ```
     java -cp .:<path_to_packages> MyClass
     ```

By importing packages in Java, you can access classes and interfaces from different packages and utilize their functionality in your code. Importing specific classes or using wildcard imports helps in managing the dependencies of your code and promotes code organization and reusability.

### Uncaught Exceptions

Uncaught exceptions in Java refer to exceptions that are thrown during the execution of a program but not caught or handled by any exception handling mechanism. When an uncaught exception occurs, it propagates up the call stack until it reaches the top-level handler, which may terminate the program or perform some other default action.

Here's how uncaught exceptions are handled in Java:

1. Exception Propagation:
   - When an uncaught exception occurs in a method, the exception is propagated up the call stack to the caller method.
   - If the caller method doesn't catch or handle the exception, it further propagates to its caller, and so on.
   - This process continues until the exception is caught and handled or until it reaches the top-level handler.

2. Thread-Level Uncaught Exception Handler:
   - Java provides a mechanism to handle uncaught exceptions at the thread level using the `Thread.UncaughtExceptionHandler` interface.
   - You can set an uncaught exception handler for a specific thread by calling the `setUncaughtExceptionHandler()` method on the `Thread` object.
   - The uncaught exception handler's `uncaughtException()` method is called when an uncaught exception occurs in the thread.
   - Example of setting an uncaught exception handler for a thread:
     ```java
     Thread thread = new Thread(new Runnable() {
         public void run() {
             // Thread's code here
         }
     });
     thread.setUncaughtExceptionHandler(new Thread.UncaughtExceptionHandler() {
         public void uncaughtException(Thread t, Throwable e) {
             // Handle the uncaught exception here
         }
     });
     ```

3. Default Uncaught Exception Handler:
   - If no specific uncaught exception handler is set for a thread, the default uncaught exception handler is used.
   - The default behavior of the default uncaught exception handler is to print the stack trace and terminate the program.
   - You can set a default uncaught exception handler for all threads in the application by calling `Thread.setDefaultUncaughtExceptionHandler()`.
   - Example of setting a default uncaught exception handler:
     ```java
     Thread.setDefaultUncaughtExceptionHandler(new Thread.UncaughtExceptionHandler() {
         public void uncaughtException(Thread t, Throwable e) {
             // Handle the uncaught exception here
         }
     });
     ```

By handling uncaught exceptions in Java, you can perform custom actions when an exception is not caught and propagate up the call stack. This allows you to log the exception, perform cleanup tasks, display error messages, or take other appropriate actions based on the specific needs of your application.

### Multiple `catch` clauses

In Java, multiple catch clauses are used to handle different types of exceptions that can be thrown by a try block. When an exception occurs within the try block, each catch block is evaluated sequentially, and the catch block that matches the type of the thrown exception is executed. This allows you to handle different exceptions differently based on their types.

Here's the syntax for using multiple catch clauses in Java:

```java
try {
    // Code that may throw exceptions
} catch (ExceptionType1 e1) {
    // Exception handling for ExceptionType1
} catch (ExceptionType2 e2) {
    // Exception handling for ExceptionType2
} catch (ExceptionType3 e3) {
    // Exception handling for ExceptionType3
} catch (ExceptionType4 e4) {
    // Exception handling for ExceptionType4
} finally {
    // Code to be executed regardless of whether an exception occurred or not
}
```

Explanation:

- The `try` block contains the code that may throw exceptions.
- Each `catch` block specifies the exception type it can handle.
- When an exception occurs, Java checks each `catch` block sequentially to find a match between the thrown exception and the declared exception type.
- The first catch block that matches the exception type is executed, and the remaining catch blocks are skipped.
- Inside each catch block, you can provide specific exception handling code for that particular exception type.
- You can have multiple catch blocks to handle different types of exceptions.
- The `finally` block is optional and is used to specify code that should be executed regardless of whether an exception occurred or not.

Example:

```java
try {
    int[] numbers = {1, 2, 3};
    System.out.println(numbers[4]);  // Accessing an index out of bounds
} catch (ArrayIndexOutOfBoundsException e) {
    System.out.println("Array index out of bounds!");
} catch (NullPointerException e) {
    System.out.println("Null pointer exception occurred!");
} finally {
    System.out.println("This block is always executed!");
}
```

In the example above, if an exception occurs while accessing an index out of bounds in the array, the first catch block will handle the `ArrayIndexOutOfBoundsException`. If a `NullPointerException` occurs instead, the second catch block will handle it. The `finally` block will always be executed regardless of the type of exception or whether an exception occurred or not.

Using multiple catch clauses allows you to handle different exceptions separately, providing more specific exception handling based on the type of the thrown exception.

### Java's built-in exceptions

Java provides a set of built-in exceptions that are part of the Java language and libraries. These exceptions represent various error conditions or exceptional situations that can occur during the execution of a Java program. Here are some commonly used built-in exception classes in Java:

1. `ArithmeticException`:
   - This exception is thrown when an arithmetic operation encounters an exceptional condition, such as division by zero.
   - Example:
     ```java
     int result = 10 / 0;  // Throws ArithmeticException
     ```

2. `NullPointerException`:
   - This exception is thrown when a null reference is accessed and used where an object instance is expected.
   - Example:
     ```java
     String str = null;
     int length = str.length();  // Throws NullPointerException
     ```

3. `ArrayIndexOutOfBoundsException`:
   - This exception is thrown when an array is accessed with an invalid index (either negative or beyond the array size).
   - Example:
     ```java
     int[] numbers = {1, 2, 3};
     int value = numbers[5];  // Throws ArrayIndexOutOfBoundsException
     ```

4. `NumberFormatException`:
   - This exception is thrown when a string cannot be parsed into a numeric value.
   - Example:
     ```java
     String str = "abc";
     int value = Integer.parseInt(str);  // Throws NumberFormatException
     ```

5. `IOException`:
   - This exception is the base class for exceptions related to input/output operations, such as file handling.
   - It includes subclasses like `FileNotFoundException`, `IOException`, etc., which represent specific I/O-related errors.
   - Example:
     ```java
     FileReader fileReader = new FileReader("file.txt");  // Throws FileNotFoundException
     ```

6. `ClassNotFoundException`:
   - This exception is thrown when an application tries to load a class dynamically, but the class with the specified name cannot be found.
   - Example:
     ```java
     Class<?> clazz = Class.forName("com.example.MyClass");  // Throws ClassNotFoundException
     ```
