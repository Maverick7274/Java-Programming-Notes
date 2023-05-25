# IT201 Question Paper 2018(Supplementary)

## Section A

### 1. (a) What is Object Oriented Programming? How is it different from Procedural Oriented Programming?

### (b) Describe how data hiding is achieved in Java. Does data encapsulation and data abstraction mean the same?

### Answer:

(a)
In Object-Oriented Programming (OOP), programs are structured around objects, which encapsulate data and behavior. Objects are instances of classes, which define the structure and behavior of the objects. OOP focuses on concepts like encapsulation, inheritance, and polymorphism, enabling modular and reusable code.

Procedural Programming, on the other hand, focuses on procedures or functions that manipulate data. Data and functions are separate entities, and the flow of control is determined by function calls. Procedural programming is often linear and sequential, organizing code around procedures.

OOP provides advantages such as improved code organization, modularity, code reusability, and easier maintenance. It allows for better modeling of real-world entities and relationships. Procedural programming is simpler and more straightforward for smaller programs or tasks that don't require complex object interactions.

The choice between OOP and procedural programming depends on the requirements and complexity of the project. OOP is commonly used in larger software projects and applications where modularity, code reusability, and extensibility are important, while procedural programming is often used for smaller programs or tasks where simplicity and direct control over data flow are sufficient.



|                | Object-Oriented Programming (OOP)                            | Procedural Programming                                |
|----------------|------------------------------------------------------------|------------------------------------------------------|
| Focus          | Emphasizes objects as the key building blocks of a program  | Emphasizes procedures (functions/methods)             |
| Data Handling  | Data and the methods that operate on it are encapsulated in objects  | Data and functions are separate entities                    |
| Modularity     | Provides better modularity and code organization            | Organizes code around procedures or functions         |
| Data Flow      | Emphasizes message passing and communication between objects | Data flows between functions and variables           |
| Code Reusability | Supports code reusability through inheritance and polymorphism | Functions are reusable, but code sharing is limited |
| Encapsulation  | Encapsulates data and methods, hiding implementation details | Data and functions are exposed and can be accessed directly |
| Inheritance    | Supports inheritance, allowing classes to inherit properties and behaviors from parent classes | Inheritance is not a primary feature |
| Polymorphism   | Supports polymorphism, where objects can have multiple forms and behave differently based on their types | Polymorphism is not a primary feature |
| Example        | Java, C++, Python                                          | C, Pascal, Fortran                                    |


(b)
In Java, data hiding is achieved through the concept of encapsulation. Encapsulation is one of the fundamental principles of object-oriented programming and involves bundling data (attributes) and methods (behaviors) together within a class, and controlling access to them through access modifiers.

Access modifiers in Java, such as private, protected, and public, determine the visibility and accessibility of class members (attributes and methods) from outside the class. By using access modifiers appropriately, we can hide internal data and implementation details of a class from external access, ensuring that the class's internal state is not directly manipulated by other classes.

Here are the access modifiers and their implications on data hiding:

1. **Private:** Members declared as private are only accessible within the same class. They are not visible or accessible from any other class. This provides the highest level of data hiding, as the members are completely encapsulated within the class.

2. **Default (No Modifier):** Members with no explicit access modifier are accessible within the same package. They are not visible or accessible outside the package. This provides a limited form of data hiding within the package.

3. **Protected:** Members declared as protected are accessible within the same package and from subclasses (even if they are in a different package). They are not directly accessible from unrelated classes outside the package.

4. **Public:** Members declared as public are accessible from anywhere in the program. They have no restrictions on access. This provides no data hiding, as the members are fully exposed.

Regarding the second part of your question, data encapsulation and data abstraction are related concepts but are not exactly the same.

**Data Encapsulation:** Data encapsulation is the practice of combining data (attributes) and methods (behaviors) within a class and controlling access to them. It is achieved through the use of access modifiers, as discussed above. Encapsulation allows for bundling related data and behaviors together, promoting modular and organized code.

**Data Abstraction:** Data abstraction is a broader concept that involves the representation of complex systems or entities by focusing on their essential characteristics and hiding unnecessary details. In the context of object-oriented programming, data abstraction is achieved through the use of classes, interfaces, and abstract classes. It allows for creating abstract data types that define the behavior and properties of objects without exposing their internal implementation.

In summary, data hiding is achieved through encapsulation in Java, where access modifiers control the visibility and accessibility of class members. Data abstraction, on the other hand, is a broader concept that involves representing entities at a higher level of abstraction, focusing on essential characteristics and hiding implementation details. Encapsulation is one of the techniques used to achieve data abstraction.




---

### 2. (a) Write a java program to check whether a given number is a palindrome or not.

### (b) Java API package provide a large number of classes group into different packages explain any three with their functionality.

### Answer:

(a)
Input :
```java

public class PalindromeNumber {
    public static boolean isPalindrome(int number) {
        int originalNumber = number;
        int reversedNumber = 0;

        while (number != 0) {
            int digit = number % 10;
            reversedNumber = reversedNumber * 10 + digit;
            number /= 10;
        }

        return originalNumber == reversedNumber;
    }

    public static void main(String[] args) {
        int number = 12321;

        if (isPalindrome(number)) {
            System.out.println(number + " is a palindrome.");
        } else {
            System.out.println(number + " is not a palindrome.");
        }
    }
}

```

Output :
```bash
12321 is a palindrome.
```
```bash
12321 is not a palindrome.
```

(b)

Java API provides a vast collection of classes and packages that offer various functionalities for building Java applications. Here are three examples of Java API packages and their functionalities:

1. **java.util Package:** The `java.util` package provides utility classes and data structures to handle common programming tasks. Some key classes in this package include:

   - `ArrayList`: Implements a dynamic array that can grow or shrink in size as needed. It provides methods to add, remove, and modify elements.
   
   - `HashMap`: Implements a hash table-based map that stores key-value pairs. It provides efficient lookup, insertion, and deletion operations based on the keys.
   
   - `Date`: Represents a specific moment in time with date and time components. It provides methods for manipulating and formatting dates.
   
   The `java.util` package also contains classes for handling collections, sorting, input/output, date and time, random number generation, and more.

2. **java.io Package:** The `java.io` package provides classes for input and output operations in Java. It offers functionalities for reading from and writing to various data sources and destinations. Some key classes in this package include:

   - `File`: Represents a file or directory on the file system. It provides methods to query file information, create, delete, or rename files, and more.
   
   - `InputStream` and `OutputStream`: These abstract classes serve as the base classes for all input and output streams. They provide methods for reading from and writing to different data sources, such as files, network connections, and in-memory buffers.
   
   - `BufferedReader` and `BufferedWriter`: These classes provide buffering capabilities to enhance the performance of reading and writing operations by reducing the number of disk or network accesses.
   
   The `java.io` package is essential for handling file I/O, network communication, and working with streams of data.

3. **java.net Package:** The `java.net` package provides classes for networking operations in Java. It offers functionalities for establishing network connections, sending and receiving data over various network protocols. Some key classes in this package include:

   - `URL`: Represents a Uniform Resource Locator and provides methods for working with URLs, such as opening connections, reading from URLs, and retrieving information about the resource.
   
   - `URLConnection`: Represents a connection to a URL resource and provides methods for connecting, reading from, and writing to the resource.
   
   - `Socket` and `ServerSocket`: These classes are used for client-server communication over TCP/IP networks. `Socket` represents a client-side socket, and `ServerSocket` represents a server-side socket that listens for incoming connections.
   
   The `java.net` package is essential for developing networked applications, communicating with servers, fetching data from URLs, and working with network protocols like HTTP, FTP, and more.

These are just a few examples of the numerous packages and classes provided by the Java API. Each package offers a set of classes and functionalities tailored to specific domains and requirements, making Java a versatile and powerful programming language.


---

### 3. Write a program to create two threads, one thread will print odd numbers and second thread will print even numbers between 1 to 10.

### Answer:

Input :

```java

public class OddEvenThreadExample {
    public static void main(String[] args) {
        // Create two instances of the OddThread and EvenThread classes
        Thread oddThread = new Thread(new OddThread());
        Thread evenThread = new Thread(new EvenThread());

        // Start both threads
        oddThread.start();
        evenThread.start();
    }
}

// Runnable implementation for printing odd numbers
class OddThread implements Runnable {
    @Override
    public void run() {
        for (int i = 1; i <= 10; i += 2) {
            System.out.println("Odd Thread: " + i);
        }
    }
}

// Runnable implementation for printing even numbers
class EvenThread implements Runnable {
    @Override
    public void run() {
        for (int i = 2; i <= 10; i += 2) {
            System.out.println("Even Thread: " + i);
        }
    }
}
```

Output :
```bash
Odd Thread: 1
Even Thread: 2
Odd Thread: 3
Even Thread: 4
Odd Thread: 5
Even Thread: 6
Odd Thread: 7
Even Thread: 8
Odd Thread: 9
Even Thread: 10
```

---

### 4. How Applet is different from Application? Also explain various stages in the life cycle of an Applet.

### Answer:

**Difference between Applet and Application:**

An applet and an application are both types of programs in Java, but they have distinct differences in their purpose, deployment, and execution:

|       | Applet                              | Application                          |
|-------|-------------------------------------|--------------------------------------|
| Purpose | Designed to be embedded in a web page and run within a browser. | Standalone program that runs independently on a computer. |
| Deployment | Loaded and executed by a web browser with a Java plugin. | Executed directly by the Java Virtual Machine (JVM). |
| GUI | Typically has a graphical user interface (GUI) created using AWT or Swing. | Can have a GUI, command-line interface, or no interface at all. |
| Security | Subject to certain security restrictions imposed by the browser and JVM. | Has more flexibility in terms of system access and resource usage. |
| Accessibility | Can be accessed and run by anyone with a web browser and Java plugin. | Requires installation or execution by the user on their system. |
| Interaction | Can interact with the HTML page and browser environment using JavaScript. | Limited interaction with the external environment, mostly through input/output streams. |

**Life Cycle of an Applet:**

The life cycle of an applet in Java consists of several stages, each representing a specific phase in its execution:

1. **Initialization (init):** This stage is the initialization phase where the applet is set up and resources are allocated. The `init` method is called only once during the applet's lifetime. It is typically used to perform one-time initialization tasks, such as initializing variables, creating GUI components, or setting up resources.

2. **Start (start):** The `start` method is called after the `init` method and signifies the start of the applet's execution. It is called every time the applet is about to begin or resume running. This method is often used to start any background threads or timers necessary for the applet's functioning.

3. **Running (paint/update):** The applet enters the running phase, where it executes its main functionality. The `paint` method is called to render the visual output on the applet's canvas. The `update` method, if overridden, can be used to perform additional operations before the `paint` method is called. The `paint` method is called automatically by the applet's rendering system whenever a repaint is requested.

4. **Stop (stop):** The `stop` method is called when the applet is interrupted or paused. It signifies a temporary suspension of the applet's execution. This method is typically used to stop any background processes, timers, or animations that were started in the `start` method.

5. **Shutdown (destroy):** The `destroy` method is called when the applet is about to be terminated or removed from the browser window. It is used to perform cleanup tasks, release resources, and free any allocated memory. This method is called only once during the lifetime of the applet.

6. **Termination:** The applet is terminated and removed from memory either when the web page is closed or when the browser decides to unload the applet.

The life cycle of an applet is managed by the browser and the JVM, which handle the initialization, execution, and termination of the applet. The applet developer can override the appropriate methods (`init`, `start`, `stop`, `destroy`, `paint`, `update`) to add custom functionality and control the behavior of the applet at each stage.

---

### 5. Write short notes on the following:

#### (a) Layout Manager

#### (b) Swing Components

#### (c) Event-Handling-Model in Java

### Answer:

(a)

In Java, a layout manager is responsible for arranging and positioning the components within a container. It determines how the components will be displayed and how they will adjust their positions when the container is resized. Layout managers play a crucial role in creating visually appealing and responsive user interfaces.

Java provides several built-in layout managers that offer different strategies for component arrangement. Some of the commonly used layout managers are:

1. **FlowLayout:** It arranges components in a left-to-right flow, wrapping them to the next line when the container's width is insufficient. This layout is simple and suitable for situations where components need to be placed one after another.

2. **BorderLayout:** It divides the container into five regions: north, south, east, west, and center. Each region can hold only one component, and they are positioned accordingly. This layout is commonly used for creating a basic structure with header, footer, side panels, and a central content area.

3. **GridLayout:** It arranges components in a grid with specified rows and columns. Each component takes an equal amount of space in the grid, ensuring uniform distribution. This layout is useful when components need to be organized in a grid-like structure.

4. **GridBagLayout:** It provides the most flexible and powerful arrangement capabilities. It allows components to be positioned in rows and columns with adjustable sizes and alignments. This layout is suitable for complex UI designs that require precise control over component positioning.

5. **BoxLayout:** It arranges components in either a horizontal or vertical line. Components are placed one after another, and their sizes can be adjusted based on the container's dimensions. This layout is useful when components need to be aligned in a single line.

6. **CardLayout:** It allows multiple components to be stacked on top of each other, and only one component is visible at a time. Components can be switched dynamically, providing a way to display different views or panels within a single container.

Layout managers simplify the process of creating user interfaces by handling the automatic positioning and resizing of components. They ensure that the components are displayed properly on different platforms and with various window sizes. By choosing an appropriate layout manager and adjusting its settings, developers can achieve responsive and visually pleasing layouts for their Java applications.

(b)
Swing is a Java GUI toolkit that provides a rich set of components for building graphical user interfaces. Swing components are lightweight, customizable, and platform-independent, making them widely used in Java desktop applications. Here's a brief overview of some commonly used Swing components:

1. **JFrame:** It is the main window container for a Swing application. It provides a title bar, border, and other window controls. Developers can add other Swing components to a JFrame to create the application's user interface.

2. **JPanel:** It is a lightweight container used to group and organize other components. JPanels are often used to divide the main content area of a JFrame into sections or panels, allowing for better organization and layout.

3. **JButton:** It represents a clickable button. JButton components are commonly used for triggering actions or handling user interactions. They can display text, icons, or both.

4. **JLabel:** It is used to display a static text or an image. JLabels are often used to provide descriptions, captions, or status information in a user interface.

5. **JTextField:** It is an input component that allows the user to enter and edit single-line text. JTextField components are used for accepting user input, such as names, addresses, or search queries.

6. **JTextArea:** It is a multi-line text area that can display and edit multiple lines of text. JTextArea components are suitable for handling large amounts of text, such as comments, messages, or notes.

7. **JComboBox:** It provides a drop-down list of items, allowing the user to select one option from the list. JComboBox components are commonly used for presenting a selection of choices, such as a list of categories or options.

8. **JCheckBox:** It represents a checkable box that can be selected or deselected by the user. JCheckBox components are often used for presenting binary choices or for allowing the user to toggle certain options on or off.

9. **JRadioButton:** It represents a mutually exclusive selection from a set of options. JRadioButton components are typically used in groups, where only one option can be selected at a time.

10. **JScrollPane:** It provides a scrollable view for other components that exceed the available space. JScrollPanes are commonly used with JTextAreas or JTables to handle large amounts of text or data.

These are just a few examples of Swing components. Swing provides a wide range of components for various purposes, including menus, dialog boxes, tables, sliders, progress bars, and more. By combining and customizing these components, developers can create interactive and visually appealing user interfaces for their Java applications.

(c)
The event handling model in Java provides a mechanism for handling user interactions, such as button clicks, mouse movements, and keyboard inputs, in graphical user interfaces (GUIs). It allows developers to define actions or behaviors that should be executed in response to specific events.

Here's a brief overview of the event handling model in Java:

1. **Event Sources:** GUI components, such as buttons, text fields, or menus, are considered event sources. They generate events when certain user interactions occur.

2. **Event Listeners:** Event listeners are objects that are registered with an event source to receive and handle specific types of events. They implement interfaces that define event handler methods.

3. **Event Handlers:** Event handlers are methods defined in event listener interfaces. They contain the code that should be executed when a specific event occurs.

4. **Event Object:** When an event occurs, an event object is created. It encapsulates information about the event, such as the source component, event type, and any relevant data associated with the event.

5. **Event Dispatching:** When an event occurs, the event source dispatches the event to all registered event listeners. Each listener's corresponding event handler method is invoked to handle the event.

The event handling model in Java follows a callback mechanism. Developers define the desired behavior for specific events by implementing event listener interfaces and overriding their event handler methods. They then register the listener objects with the appropriate event sources, establishing the connection between the events and their corresponding handlers.

Java provides a rich set of event listener interfaces and corresponding event classes for different types of events, such as ActionListener for button clicks, MouseListener for mouse-related events, KeyListener for keyboard events, and many more. Developers can choose the relevant listener interfaces based on the types of events they want to handle.

By utilizing the event handling model, developers can create interactive GUI applications that respond to user actions and provide dynamic behaviors. It allows for separation of concerns, enabling different components of the application to handle events independently and maintain clean and modular code.

---

### 6. (a) Differentiate between default and parameterized constructors with example.

### (b) Define `swing` in Java. Also write some features of `swings`.

### Answer:

(a)

|                | Default Constructor                         | Parameterized Constructor                              |
|----------------|---------------------------------------------|-------------------------------------------------------|
| Definition     | Provided by the compiler if no constructor is defined explicitly. | Defined by the programmer with one or more parameters. |
| Parameters     | No parameters                                | Can have one or more parameters.                       |
| Initialization | Performs default initialization of instance variables (e.g., assigns default values). | Allows custom initialization of instance variables based on the provided arguments. |
| Usage          | Used when no specific initialization is required or when default values are sufficient. | Used when specific initialization is required based on the provided arguments. |
| Overriding     | Default constructors cannot be overridden.   | Parameterized constructors can be overridden in subclasses. |
| Automatic Call | Automatically called when an object is created using the `new` keyword and no arguments are passed. | Must be explicitly called by the programmer with the appropriate arguments. |
| Multiple        | It is possible to have multiple default constructors with different access modifiers (e.g., public, private). | It is possible to have multiple parameterized constructors with different argument combinations, allowing constructor overloading. |

In summary, default constructors are provided by the compiler if no constructor is explicitly defined. They are used for default initialization of instance variables and are automatically called when an object is created without any arguments. On the other hand, parameterized constructors are defined by the programmer and allow custom initialization of instance variables based on the provided arguments. They need to be explicitly called by the programmer with the appropriate arguments. Parameterized constructors can also be overloaded, providing flexibility to create objects with different argument combinations.

Example: 

1. Default Constructor:

```java
public class Person {
    private String name;
    private int age;
    
    // Default constructor
    public Person() {
        // Default initialization
        name = "John Doe";
        age = 0;
    }
    
    // Other methods and code...
}
```

In the above example, the `Person` class has a default constructor. It initializes the `name` variable with the default value "John Doe" and the `age` variable with the default value of 0. This constructor will be automatically called when an object of the `Person` class is created without passing any arguments.

2. Parameterized Constructor:

```java
public class Person {
    private String name;
    private int age;
    
    // Parameterized constructor
    public Person(String name, int age) {
        // Custom initialization based on provided arguments
        this.name = name;
        this.age = age;
    }
    
    // Other methods and code...
}
```

(b)
In Java, Swing is a GUI (Graphical User Interface) toolkit that provides a set of components and tools for building desktop applications with rich and interactive graphical interfaces. It is part of the Java Foundation Classes (JFC) and is built on top of the Abstract Window Toolkit (AWT).

Here are some features of Swing:

1. **Platform-Independent:** Swing components are written in pure Java, which makes them platform-independent. They can run on any system that supports Java, allowing developers to create applications that work consistently across different operating systems.

2. **Rich Set of Components:** Swing provides a wide range of components, including buttons, labels, text fields, combo boxes, tables, trees, and more. These components are highly customizable and can be tailored to suit the specific needs and aesthetics of the application.

3. **Look and Feel Customization:** Swing allows developers to customize the look and feel of their applications. It provides different look and feel options, such as the default Metal look and feel, Windows look and feel, or the system's native look and feel. Developers can choose the one that matches the desired appearance and behavior of their application.

4. **Layout Managers:** Swing offers various layout managers to handle component positioning and resizing. Layout managers help in creating flexible and responsive user interfaces by automatically adjusting the components' placement based on the container's size and user interactions.

5. **Event-Driven Programming:** Swing follows an event-driven programming model, where components generate events (e.g., button clicks, mouse movements) and listeners are used to handle these events. This model allows developers to define interactive behaviors and responses to user actions.

6. **Double Buffering:** Swing uses double buffering by default, which eliminates flickering and provides smooth rendering of graphical components. Double buffering reduces visual artifacts and improves the overall user experience.

7. **Accessibility:** Swing includes features for creating accessible applications. It provides support for assistive technologies, allowing users with disabilities to interact with the application effectively.

8. **Internationalization and Localization:** Swing supports internationalization and localization, making it easier to develop applications that can be adapted to different languages, regions, and cultural preferences.

Swing provides a powerful and flexible framework for building desktop applications with modern and responsive user interfaces. Its features make it a popular choice for Java developers when creating graphical applications across various industries and domains.

---

## Section B

### 7. (a) Write a Java program to implement multilevel inheritance.

### (b) Write a Java program to make calculator program by making use of `switch`, `case` and `break`.

### Answer:

(a)
Input :

```java
// Parent class
class Animal {
    void eat() {
        System.out.println("Animal is eating.");
    }
}

// Child class inheriting from Animal
class Dog extends Animal {
    void bark() {
        System.out.println("Dog is barking.");
    }
}

// Grandchild class inheriting from Dog
class Labrador extends Dog {
    void run() {
        System.out.println("Labrador is running.");
    }
}

// Main class
public class MultilevelInheritanceExample {
    public static void main(String[] args) {
        // Create an object of the grandchild class
        Labrador labrador = new Labrador();

        // Call methods from each class
        labrador.eat();  // Inherited from Animal class
        labrador.bark(); // Inherited from Dog class
        labrador.run();  // Defined in Labrador class
    }
}
```

Output :

```bash
Animal is eating.
Dog is barking.
Labrador is running.
```
(b)

```java
import java.util.Scanner;

public class Calculator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter the first number: ");
        double num1 = scanner.nextDouble();

        System.out.print("Enter the second number: ");
        double num2 = scanner.nextDouble();

        System.out.println("Select an operation:");
        System.out.println("1. Addition (+)");
        System.out.println("2. Subtraction (-)");
        System.out.println("3. Multiplication (*)");
        System.out.println("4. Division (/)");
        System.out.print("Enter your choice (1-4): ");
        int choice = scanner.nextInt();

        double result;

        switch (choice) {
            case 1:
                result = num1 + num2;
                System.out.println("Result: " + result);
                break;
            case 2:
                result = num1 - num2;
                System.out.println("Result: " + result);
                break;
            case 3:
                result = num1 * num2;
                System.out.println("Result: " + result);
                break;
            case 4:
                if (num2 == 0) {
                    System.out.println("Error: Division by zero");
                } else {
                    result = num1 / num2;
                    System.out.println("Result: " + result);
                }
                break;
            default:
                System.out.println("Invalid choice");
                break;
        }

        scanner.close();
    }
}

```



---

### 8. (a) Why interface is required in Java? Which kind of data member and member functions are there in interface? Also write the benefits of interface.

### (b) Write a Java program implementing multiple inheritance.

### Answer:

(a)
Interfaces are an essential part of the Java programming language and are used for defining contracts or blueprints for classes. They provide a way to achieve abstraction and enable the implementation of multiple inheritance-like behavior.

In an interface, you can declare:

1. **Data Members**: Interfaces can declare constant variables, also known as "constants" or "static final" variables. These variables are implicitly public, static, and final, and their values cannot be changed once assigned. By convention, constant variable names are written in uppercase.

2. **Member Functions**: Interfaces can declare abstract methods, which are methods without any implementation. These methods are implicitly public and abstract, meaning they do not have a method body. Classes that implement an interface must provide an implementation for all the abstract methods defined in the interface.

Benefits of using interfaces in Java include:

1. **Abstraction**: Interfaces provide a way to achieve abstraction by defining a contract without specifying the implementation details. They allow you to define the behavior that classes implementing the interface must follow, without exposing the internal implementation.

2. **Multiple Inheritance-like Behavior**: Unlike classes, which can only extend one superclass, a class in Java can implement multiple interfaces. This allows for achieving multiple inheritance-like behavior, where a class can inherit the functionality of multiple interfaces.

3. **Contract Enforcement**: Interfaces allow you to enforce a contract on classes that implement them. By implementing an interface, a class agrees to adhere to the defined contract and provide implementations for the abstract methods declared in the interface.

4. **Code Reusability**: Interfaces promote code reusability by providing a standardized way to define and share behavior across multiple classes. Classes that implement the same interface can be treated interchangeably, allowing for code modularity and flexibility.

5. **Polymorphism**: Interfaces enable polymorphism, which means that an object can take on many forms. By programming to interfaces, rather than concrete classes, you can write code that is more flexible and adaptable to different implementations.

Overall, interfaces play a crucial role in Java programming by providing a mechanism for defining contracts, achieving abstraction, and facilitating code reuse and flexibility. They promote good software design principles such as loose coupling, modularity, and polymorphism.

(b)

Input :

```java
// Interface for the first behavior
interface FirstInterface {
    void firstMethod();
}

// Interface for the second behavior
interface SecondInterface {
    void secondMethod();
}

// Class implementing both interfaces
class MyClass implements FirstInterface, SecondInterface {
    public void firstMethod() {
        System.out.println("Executing firstMethod()");
    }

    public void secondMethod() {
        System.out.println("Executing secondMethod()");
    }
}

// Main class
public class MultipleInheritanceExample {
    public static void main(String[] args) {
        MyClass myClass = new MyClass();
        myClass.firstMethod();
        myClass.secondMethod();
    }
}

```

Output :

```bash
Executing firstMethod()
Executing secondMethod()
```

---

### 9. Discuss the following :

#### (a) FocusEvent & FocusListener

#### (b) MouseEvent & MouseListener

#### (c) WindowEvent & WindowListener

#### (d) KeyEvent & KeyListener

#### (e) ActionEvent & ActionListener

### Answer:

(a)
`FocusEvent` and `FocusListener` are part of the Java AWT (Abstract Window Toolkit) package and are used to handle focus-related events in graphical user interfaces.

**FocusEvent:**
`FocusEvent` is an event class that represents a low-level focus event. It is generated when a component gains or loses focus. This event provides information about the source component, the type of focus change (gain or loss), and the cause of the focus change (such as mouse click or keyboard action).

Key properties of the `FocusEvent` class include:

- `id`: Represents the type of focus event (`FOCUS_GAINED` or `FOCUS_LOST`).
- `source`: Represents the component that generated the event.
- `temporary`: Indicates whether the focus change is temporary or permanent.

**FocusListener:**
`FocusListener` is an interface that provides a way to handle focus events. It contains two methods: `focusGained()` and `focusLost()`. A class can implement the `FocusListener` interface to receive and handle focus events on the registered components.

The `FocusListener` interface includes the following methods:

- `void focusGained(FocusEvent e)`: This method is invoked when a component gains focus. It is called when the component becomes the active component.
- `void focusLost(FocusEvent e)`: This method is invoked when a component loses focus. It is called when the component is no longer the active component.

By implementing the `FocusListener` interface and overriding these methods, you can define custom behavior to be executed when a component gains or loses focus.

Here's a simple example that demonstrates the usage of `FocusEvent` and `FocusListener`:

```java
import java.awt.*;
import java.awt.event.*;

public class FocusEventExample {
    public static void main(String[] args) {
        Frame frame = new Frame("Focus Event Example");

        TextField textField = new TextField();
        textField.addFocusListener(new CustomFocusListener());

        frame.add(textField);
        frame.setSize(300, 200);
        frame.setVisible(true);
    }
}

class CustomFocusListener implements FocusListener {
    public void focusGained(FocusEvent e) {
        System.out.println("Component gained focus");
    }

    public void focusLost(FocusEvent e) {
        System.out.println("Component lost focus");
    }
}
```

In this example, a `Frame` is created, and a `TextField` is added to the frame. An instance of the `CustomFocusListener` class, which implements the `FocusListener` interface, is registered as the focus listener for the text field. When the text field gains or loses focus, the respective methods in the `CustomFocusListener` class are called, and a message is printed to the console.

By using `FocusEvent` and implementing `FocusListener`, you can perform specific actions or behaviors when components gain or lose focus, providing better interactivity and control in your Java GUI applications.

(b)

`MouseEvent` and `MouseListener` are part of the Java AWT (Abstract Window Toolkit) package and are used to handle mouse-related events in graphical user interfaces.

**MouseEvent:**
`MouseEvent` is an event class that represents a mouse event. It is generated when a mouse-related action occurs, such as clicking a mouse button, moving the mouse, or dragging the mouse. This event provides information about the source component, the type of mouse action, the position of the mouse, and the state of the mouse buttons.

Key properties of the `MouseEvent` class include:

- `id`: Represents the type of mouse event (`MOUSE_CLICKED`, `MOUSE_PRESSED`, `MOUSE_RELEASED`, `MOUSE_MOVED`, etc.).
- `source`: Represents the component that generated the event.
- `x` and `y`: Represent the coordinates of the mouse pointer relative to the source component.
- `button`: Represents the button involved in the mouse event (`BUTTON1`, `BUTTON2`, `BUTTON3`, etc.).
- `clickCount`: Indicates the number of quick consecutive clicks for the event.

**MouseListener:**
`MouseListener` is an interface that provides a way to handle mouse events. It contains five methods: `mouseClicked()`, `mousePressed()`, `mouseReleased()`, `mouseEntered()`, and `mouseExited()`. A class can implement the `MouseListener` interface to receive and handle mouse events on the registered components.

The `MouseListener` interface includes the following methods:

- `void mouseClicked(MouseEvent e)`: This method is invoked when the mouse button is clicked (pressed and released) on a component.
- `void mousePressed(MouseEvent e)`: This method is invoked when the mouse button is pressed down on a component.
- `void mouseReleased(MouseEvent e)`: This method is invoked when the mouse button is released on a component.
- `void mouseEntered(MouseEvent e)`: This method is invoked when the mouse enters a component.
- `void mouseExited(MouseEvent e)`: This method is invoked when the mouse exits a component.

By implementing the `MouseListener` interface and overriding these methods, you can define custom behavior to be executed when mouse events occur on the registered components.

Here's a simple example that demonstrates the usage of `MouseEvent` and `MouseListener`:

```java
import java.awt.*;
import java.awt.event.*;

public class MouseEventExample {
    public static void main(String[] args) {
        Frame frame = new Frame("Mouse Event Example");

        Button button = new Button("Click Me");
        button.addMouseListener(new CustomMouseListener());

        frame.add(button);
        frame.setSize(300, 200);
        frame.setVisible(true);
    }
}

class CustomMouseListener implements MouseListener {
    public void mouseClicked(MouseEvent e) {
        System.out.println("Mouse Clicked");
    }

    public void mousePressed(MouseEvent e) {
        System.out.println("Mouse Pressed");
    }

    public void mouseReleased(MouseEvent e) {
        System.out.println("Mouse Released");
    }

    public void mouseEntered(MouseEvent e) {
        System.out.println("Mouse Entered");
    }

    public void mouseExited(MouseEvent e) {
        System.out.println("Mouse Exited");
    }
}
```

In this example, a `Frame` is created, and a `Button` is added to the frame. An instance of the `CustomMouseListener` class, which implements the `MouseListener` interface, is registered as the mouse listener for the button. When mouse events occur on the button, the respective methods in the `CustomMouseListener` class are called, and a message is printed to the console.

By using `MouseEvent` and implementing `MouseListener`, you can perform specific actions or behaviors in response to mouse events, providing interactivity and responsiveness in your Java GUI applications.

(c)
`WindowEvent` and `WindowListener` are part of the Java AWT (Abstract Window Toolkit) package and are used to handle window-related events in graphical user interfaces.

**WindowEvent:**
`WindowEvent` is an event class that represents a window-related event. It is generated when a window-related action occurs, such as opening, closing, activating, deactivating, or resizing a window. This event provides information about the source window and the type of window action.

Key properties of the `WindowEvent` class include:

- `id`: Represents the type of window event (`WINDOW_OPENED`, `WINDOW_CLOSED`, `WINDOW_ACTIVATED`, `WINDOW_DEACTIVATED`, etc.).
- `source`: Represents the window that generated the event.

**WindowListener:**
`WindowListener` is an interface that provides a way to handle window events. It contains seven methods: `windowOpened()`, `windowClosing()`, `windowClosed()`, `windowIconified()`, `windowDeiconified()`, `windowActivated()`, and `windowDeactivated()`. A class can implement the `WindowListener` interface to receive and handle window events on the registered windows.

The `WindowListener` interface includes the following methods:

- `void windowOpened(WindowEvent e)`: This method is invoked when a window is opened (made visible).
- `void windowClosing(WindowEvent e)`: This method is invoked when a window is in the process of being closed by the user.
- `void windowClosed(WindowEvent e)`: This method is invoked after a window has been closed.
- `void windowIconified(WindowEvent e)`: This method is invoked when a window is minimized (iconified).
- `void windowDeiconified(WindowEvent e)`: This method is invoked when a window is restored from a minimized state.
- `void windowActivated(WindowEvent e)`: This method is invoked when a window becomes the active window.
- `void windowDeactivated(WindowEvent e)`: This method is invoked when a window is no longer the active window.

By implementing the `WindowListener` interface and overriding these methods, you can define custom behavior to be executed when window events occur on the registered windows.

Here's a simple example that demonstrates the usage of `WindowEvent` and `WindowListener`:

```java
import java.awt.*;
import java.awt.event.*;

public class WindowEventExample {
    public static void main(String[] args) {
        Frame frame = new Frame("Window Event Example");

        frame.addWindowListener(new CustomWindowListener());

        frame.setSize(300, 200);
        frame.setVisible(true);
    }
}

class CustomWindowListener implements WindowListener {
    public void windowOpened(WindowEvent e) {
        System.out.println("Window Opened");
    }

    public void windowClosing(WindowEvent e) {
        System.out.println("Window Closing");
    }

    public void windowClosed(WindowEvent e) {
        System.out.println("Window Closed");
    }

    public void windowIconified(WindowEvent e) {
        System.out.println("Window Iconified");
    }

    public void windowDeiconified(WindowEvent e) {
        System.out.println("Window Deiconified");
    }

    public void windowActivated(WindowEvent e) {
        System.out.println("Window Activated");
    }

    public void windowDeactivated(WindowEvent e) {
        System.out.println("Window Deactivated");
    }
}
```

In this example, a `Frame` is created, and a `CustomWindowListener` object, which implements the `WindowListener` interface, is registered as the window listener for the frame. When window events occur on the frame, the respective methods in the `CustomWindowListener` class are called, and a message is printed to the console

.

By using `WindowEvent` and implementing `WindowListener`, you can perform specific actions or behaviors in response to window events, such as managing the opening and closing of windows, handling window activation or deactivation, and responding to window iconification or deiconification in your Java GUI applications.

(d)
`KeyEvent` and `KeyListener` are part of the Java AWT (Abstract Window Toolkit) package and are used to handle keyboard-related events in graphical user interfaces.

**KeyEvent:**
`KeyEvent` is an event class that represents a keyboard-related event. It is generated when a key on the keyboard is pressed, released, or typed. This event provides information about the source component, the type of key action, the key code, and the key modifiers.

Key properties of the `KeyEvent` class include:

- `id`: Represents the type of key event (`KEY_PRESSED`, `KEY_RELEASED`, `KEY_TYPED`).
- `source`: Represents the component that generated the event.
- `keyCode`: Represents the integer key code of the pressed or released key.
- `keyChar`: Represents the character associated with the key if the event is a `KEY_TYPED` event.
- `modifiers`: Represents the modifiers keys (Ctrl, Shift, Alt, etc.) held down during the key event.

**KeyListener:**
`KeyListener` is an interface that provides a way to handle keyboard events. It contains three methods: `keyPressed()`, `keyReleased()`, and `keyTyped()`. A class can implement the `KeyListener` interface to receive and handle keyboard events on the registered components.

The `KeyListener` interface includes the following methods:

- `void keyPressed(KeyEvent e)`: This method is invoked when a key is pressed down.
- `void keyReleased(KeyEvent e)`: This method is invoked when a key is released.
- `void keyTyped(KeyEvent e)`: This method is invoked when a key is typed (pressed and released).

By implementing the `KeyListener` interface and overriding these methods, you can define custom behavior to be executed when keyboard events occur on the registered components.

Here's a simple example that demonstrates the usage of `KeyEvent` and `KeyListener`:

```java
import java.awt.*;
import java.awt.event.*;

public class KeyEventExample {
    public static void main(String[] args) {
        Frame frame = new Frame("Key Event Example");

        TextField textField = new TextField(20);
        textField.addKeyListener(new CustomKeyListener());

        frame.add(textField);
        frame.setSize(300, 200);
        frame.setVisible(true);
    }
}

class CustomKeyListener implements KeyListener {
    public void keyPressed(KeyEvent e) {
        System.out.println("Key Pressed: " + e.getKeyChar());
    }

    public void keyReleased(KeyEvent e) {
        System.out.println("Key Released: " + e.getKeyChar());
    }

    public void keyTyped(KeyEvent e) {
        System.out.println("Key Typed: " + e.getKeyChar());
    }
}
```

In this example, a `Frame` is created, and a `TextField` is added to the frame. An instance of the `CustomKeyListener` class, which implements the `KeyListener` interface, is registered as the key listener for the text field. When keyboard events occur in the text field, the respective methods in the `CustomKeyListener` class are called, and a message is printed to the console.

By using `KeyEvent` and implementing `KeyListener`, you can capture and respond to keyboard events in your Java GUI applications, allowing users to interact with the application using the keyboard.

(e)
`ActionEvent` and `ActionListener` are part of the Java AWT (Abstract Window Toolkit) package and are used to handle action-related events in graphical user interfaces.

**ActionEvent:**
`ActionEvent` is an event class that represents an action-related event. It is generated when an action occurs, such as clicking a button, selecting a menu item, or pressing the Enter key in a text field. This event provides information about the source component and the type of action.

Key properties of the `ActionEvent` class include:

- `id`: Represents the type of action event (`ACTION_PERFORMED`).
- `source`: Represents the component that generated the event.

**ActionListener:**
`ActionListener` is an interface that provides a way to handle action events. It contains a single method, `actionPerformed()`. A class can implement the `ActionListener` interface to receive and handle action events on the registered components.

The `ActionListener` interface includes the following method:

- `void actionPerformed(ActionEvent e)`: This method is invoked when an action event occurs on a registered component.

By implementing the `ActionListener` interface and overriding the `actionPerformed()` method, you can define custom behavior to be executed when action events occur on the registered components.

Here's a simple example that demonstrates the usage of `ActionEvent` and `ActionListener`:

```java
import java.awt.*;
import java.awt.event.*;

public class ActionEventExample {
    public static void main(String[] args) {
        Frame frame = new Frame("Action Event Example");

        Button button = new Button("Click Me");
        button.addActionListener(new CustomActionListener());

        frame.add(button);
        frame.setSize(300, 200);
        frame.setVisible(true);
    }
}

class CustomActionListener implements ActionListener {
    public void actionPerformed(ActionEvent e) {
        System.out.println("Button Clicked");
    }
}
```

In this example, a `Frame` is created, and a `Button` is added to the frame. An instance of the `CustomActionListener` class, which implements the `ActionListener` interface, is registered as the action listener for the button. When the button is clicked, the `actionPerformed()` method in the `CustomActionListener` class is called, and a message is printed to the console.

By using `ActionEvent` and implementing `ActionListener`, you can capture and respond to action events in your Java GUI applications, allowing users to interact with the application by performing various actions, such as clicking buttons or selecting menu items.


---

## Section C

### 10. (a) What is the importance of thread synchronization in multi-threading? Explain with an example.

#### (i) Give some examples of resource corruption when multiple thread conflicts.

#### (ii) How do you synchronize Conflicting threads?

### (b) Write an Applet program to draw human face.

### (c) Develop an applet that recieves two numeric values as an input from the users and then displays the sum of the two on the screen. Write the HTML page and test the applet.


### Answer:

(a)
Thread synchronization is important in multi-threading to ensure that multiple threads can safely access shared resources or perform critical sections of code without interfering with each other. It helps in maintaining consistency and preventing race conditions, where the final outcome of the program depends on the timing and interleaving of thread execution.

Consider an example where multiple threads are accessing and modifying a shared counter variable concurrently:

```java
class Counter {
    private int count = 0;

    public void increment() {
        count++;
    }

    public int getCount() {
        return count;
    }
}

class IncrementThread extends Thread {
    private Counter counter;

    public IncrementThread(Counter counter) {
        this.counter = counter;
    }

    public void run() {
        for (int i = 0; i < 1000; i++) {
            counter.increment();
        }
    }
}

public class ThreadSynchronizationExample {
    public static void main(String[] args) throws InterruptedException {
        Counter counter = new Counter();
        IncrementThread thread1 = new IncrementThread(counter);
        IncrementThread thread2 = new IncrementThread(counter);

        thread1.start();
        thread2.start();

        thread1.join();
        thread2.join();

        System.out.println("Final Count: " + counter.getCount());
    }
}
```

In this example, two `IncrementThread` objects are created, both of which share the same `Counter` object. Each thread increments the counter variable 1000 times in its `run()` method. The `main()` method starts both threads and waits for them to complete using `join()`. Finally, it prints the final count value.

However, without synchronization, there is a chance of race condition occurring. Race conditions can lead to inconsistent or incorrect results because the threads can interrupt each other, resulting in an incorrect final count.

To ensure the correctness of the program, you can use synchronization mechanisms such as the `synchronized` keyword or `Lock` objects to protect the critical section of code. Here's an example with synchronization:

```java
class Counter {
    private int count = 0;

    public synchronized void increment() {
        count++;
    }

    public synchronized int getCount() {
        return count;
    }
}

// Rest of the code remains the same
```

In this updated example, the `increment()` and `getCount()` methods are synchronized using the `synchronized` keyword. This ensures that only one thread can execute these methods at a time, preventing any race conditions. As a result, the final count will always be the expected value of 2000.

Thread synchronization is crucial in multi-threaded applications to maintain data integrity, avoid race conditions, and ensure that shared resources are accessed safely. By using synchronization mechanisms, you can coordinate the execution of threads and prevent conflicts, allowing for correct and predictable results.

(i)
Thread synchronization is important in multi-threading to ensure that multiple threads can safely access shared resources or perform critical sections of code without interfering with each other. It helps in maintaining consistency and preventing race conditions, where the final outcome of the program depends on the timing and interleaving of thread execution.

Consider an example where multiple threads are accessing and modifying a shared counter variable concurrently:

```java
class Counter {
    private int count = 0;

    public void increment() {
        count++;
    }

    public int getCount() {
        return count;
    }
}

class IncrementThread extends Thread {
    private Counter counter;

    public IncrementThread(Counter counter) {
        this.counter = counter;
    }

    public void run() {
        for (int i = 0; i < 1000; i++) {
            counter.increment();
        }
    }
}

public class ThreadSynchronizationExample {
    public static void main(String[] args) throws InterruptedException {
        Counter counter = new Counter();
        IncrementThread thread1 = new IncrementThread(counter);
        IncrementThread thread2 = new IncrementThread(counter);

        thread1.start();
        thread2.start();

        thread1.join();
        thread2.join();

        System.out.println("Final Count: " + counter.getCount());
    }
}
```

In this example, two `IncrementThread` objects are created, both of which share the same `Counter` object. Each thread increments the counter variable 1000 times in its `run()` method. The `main()` method starts both threads and waits for them to complete using `join()`. Finally, it prints the final count value.

However, without synchronization, there is a chance of race condition occurring. Race conditions can lead to inconsistent or incorrect results because the threads can interrupt each other, resulting in an incorrect final count.

To ensure the correctness of the program, you can use synchronization mechanisms such as the `synchronized` keyword or `Lock` objects to protect the critical section of code. Here's an example with synchronization:

```java
class Counter {
    private int count = 0;

    public synchronized void increment() {
        count++;
    }

    public synchronized int getCount() {
        return count;
    }
}

// Rest of the code remains the same
```

In this updated example, the `increment()` and `getCount()` methods are synchronized using the `synchronized` keyword. This ensures that only one thread can execute these methods at a time, preventing any race conditions. As a result, the final count will always be the expected value of 2000.

Thread synchronization is crucial in multi-threaded applications to maintain data integrity, avoid race conditions, and ensure that shared resources are accessed safely. By using synchronization mechanisms, you can coordinate the execution of threads and prevent conflicts, allowing for correct and predictable results.

(ii)
Conflicting threads can be synchronized using various synchronization mechanisms provided by Java. These mechanisms ensure that only one thread can access a shared resource or critical section of code at a time, preventing conflicts and maintaining data integrity. Here are some ways to synchronize conflicting threads:

1. Synchronized Methods:
   You can use the `synchronized` keyword to declare a method as synchronized. This allows only one thread to execute the synchronized method at a time. Other threads that try to access the method will be blocked until the executing thread completes. For example:
   
   ```java
   public synchronized void myMethod() {
       // Synchronized code block
   }
   ```

2. Synchronized Blocks:
   Synchronized blocks allow you to specify a specific block of code that should be executed by only one thread at a time. This gives more flexibility compared to synchronized methods, as you can synchronize on different objects or variables. For example:

   ```java
   synchronized (sharedObject) {
       // Synchronized code block
   }
   ```

3. Locks and Conditions:
   Java's `Lock` interface and its implementations, such as `ReentrantLock`, provide more advanced synchronization mechanisms. Locks allow for finer control over thread synchronization and can handle more complex scenarios compared to synchronized methods and blocks. For example:

   ```java
   Lock lock = new ReentrantLock();
   lock.lock();
   try {
       // Synchronized code block
   } finally {
       lock.unlock();
   }
   ```

4. Volatile Variables:
   The `volatile` keyword can be used to mark variables that are shared among multiple threads. It ensures that the variable's value is always read from and written to main memory, rather than a thread's local cache. This helps in synchronizing the visibility of the variable's value across threads.

5. Thread Synchronization Utilities:
   Java provides several synchronization utilities in the `java.util.concurrent` package, such as `Semaphore`, `CountDownLatch`, and `CyclicBarrier`. These utilities offer more advanced synchronization mechanisms to coordinate the execution of multiple threads and handle complex synchronization requirements.

It's important to note that synchronization mechanisms should be used judiciously and applied only where necessary to avoid unnecessary locking and potential performance issues. The choice of synchronization mechanism depends on the specific requirements and characteristics of the multi-threaded application.

(b)

```java
import java.applet.Applet;
import java.awt.Color;
import java.awt.Graphics;

public class HumanFaceApplet extends Applet {
    public void paint(Graphics g) {
        // Set the background color
        setBackground(Color.WHITE);

        // Set the face color
        g.setColor(Color.YELLOW);

        // Draw the face (a circle)
        int faceRadius = 100;
        int faceX = getWidth() / 2 - faceRadius;
        int faceY = getHeight() / 2 - faceRadius;
        g.fillOval(faceX, faceY, faceRadius * 2, faceRadius * 2);

        // Set the eye color
        g.setColor(Color.BLACK);

        // Draw the eyes (two circles)
        int eyeRadius = 15;
        int leftEyeX = faceX + 40;
        int rightEyeX = faceX + faceRadius * 2 - 40;
        int eyeY = faceY + 50;
        g.fillOval(leftEyeX, eyeY, eyeRadius * 2, eyeRadius * 2);
        g.fillOval(rightEyeX, eyeY, eyeRadius * 2, eyeRadius * 2);

        // Set the mouth color
        g.setColor(Color.RED);

        // Draw the mouth (an arc)
        int mouthX = faceX + 20;
        int mouthY = faceY + 80;
        int mouthWidth = faceRadius * 2 - 40;
        int mouthHeight = 60;
        int startAngle = 180;
        int arcAngle = 180;
        g.fillArc(mouthX, mouthY, mouthWidth, mouthHeight, startAngle, arcAngle);
    }
}
```

(c)

```java
import java.applet.Applet;
import java.awt.Button;
import java.awt.FlowLayout;
import java.awt.Label;
import java.awt.TextField;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class SumApplet extends Applet {
    private TextField num1TextField;
    private TextField num2TextField;
    private Button calculateButton;
    private Label resultLabel;

    public void init() {
        setLayout(new FlowLayout());

        // Create and add the input fields
        num1TextField = new TextField(10);
        num2TextField = new TextField(10);
        add(new Label("Number 1:"));
        add(num1TextField);
        add(new Label("Number 2:"));
        add(num2TextField);

        // Create and add the calculate button
        calculateButton = new Button("Calculate Sum");
        add(calculateButton);

        // Create and add the result label
        resultLabel = new Label();
        add(resultLabel);

        // Add ActionListener to the calculate button
        calculateButton.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                calculateSum();
            }
        });
    }

    private void calculateSum() {
        try {
            // Parse the input values
            int num1 = Integer.parseInt(num1TextField.getText());
            int num2 = Integer.parseInt(num2TextField.getText());

            // Calculate the sum
            int sum = num1 + num2;

            // Display the result
            resultLabel.setText("Sum: " + sum);
        } catch (NumberFormatException e) {
            resultLabel.setText("Invalid input. Please enter valid numbers.");
        }
    }
}
```

To test the applet, you need to embed it into an HTML page. Here's an example HTML code to embed the applet:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Sum Applet Test</title>
</head>
<body>
    <h1>Sum Applet Test</h1>
    <applet code="SumApplet.class" width="300" height="200"></applet>
</body>
</html>
```

Save the applet code in a file named `SumApplet.java` and the HTML code in a file named `test.html`. Compile the Java applet code using the `javac` command, and then open the `test.html` file in a web browser. You should see an applet embedded in the web page, with input fields to enter two numbers and a button to calculate their sum. The result will be displayed below the button.

>Please note that running Java applets in modern browsers may require additional configurations and security settings.

---