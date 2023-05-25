# IT201 Java Programming

## Module 3

### What are Threads in Java?

Threads in Java are lightweight, independent units of execution that allow concurrent and parallel execution of multiple tasks within a single program. A thread represents a sequence of instructions that can be scheduled and executed independently by the operating system. Java provides built-in support for multithreading, allowing developers to create and manage threads easily.

Here are some key points about threads in Java:

1. Thread Creation:
   - Threads in Java can be created by either extending the `Thread` class or implementing the `Runnable` interface.
   - Extending the `Thread` class:
     ```java
     public class MyThread extends Thread {
         public void run() {
             // Thread's code here
         }
     }
     ```
   - Implementing the `Runnable` interface:
     ```java
     public class MyRunnable implements Runnable {
         public void run() {
             // Thread's code here
         }
     }
     ```

2. Thread Lifecycle:
   - Threads in Java go through different states, including new, runnable, blocked, waiting, timed waiting, and terminated.
   - The `start()` method is used to start the execution of a thread, and the `run()` method contains the code to be executed by the thread.
   - The thread can be stopped using the `stop()` method (deprecated) or by allowing the `run()` method to complete naturally.

3. Thread Synchronization:
   - When multiple threads access shared resources concurrently, synchronization is needed to ensure thread safety and prevent data corruption.
   - Java provides synchronization mechanisms, such as the `synchronized` keyword, locks, and semaphores, to control the access to shared resources among multiple threads.

4. Thread Interactions:
   - Threads can communicate and coordinate with each other using techniques like thread signaling, waiting, and notifying.
   - The `wait()`, `notify()`, and `notifyAll()` methods are used for inter-thread communication and coordination.

5. Thread Management:
   - Java provides methods to manage threads, such as setting thread priorities, interrupting threads, and waiting for threads to complete using the `join()` method.
   - The `Thread.sleep()` method is used to pause the execution of a thread for a specified period.

6. Thread Pooling:
   - Java includes the `Executor` framework, which allows for efficient management and reuse of threads through thread pooling.
   - Thread pools provide a pool of pre-initialized threads, reducing the overhead of thread creation and improving performance.

Threads in Java enable concurrent execution, allowing different tasks to be performed simultaneously and improving the overall efficiency of the program. By effectively utilizing threads, you can achieve parallelism, responsiveness, and better resource utilization in your Java applications. However, proper synchronization and coordination are crucial to ensure thread safety and prevent race conditions or data inconsistencies when multiple threads access shared resources.

### Creating Threads

In Java, threads can be created by either extending the `Thread` class or implementing the `Runnable` interface. Here's a detailed explanation of both approaches:

1. Extending the `Thread` class:
   - To create a thread by extending the `Thread` class, follow these steps:
     - Create a new class that extends the `Thread` class and override the `run()` method.
       ```java
       public class MyThread extends Thread {
           public void run() {
               // Thread's code here
           }
       }
       ```
     - Implement the desired logic of the thread within the `run()` method. This method will be executed when the thread starts.
     - Create an instance of the custom thread class and call the `start()` method to start the execution of the thread.
       ```java
       MyThread thread = new MyThread();
       thread.start();
       ```
     - The `start()` method internally calls the `run()` method, so you should not directly invoke the `run()` method.

2. Implementing the `Runnable` interface:
   - To create a thread by implementing the `Runnable` interface, follow these steps:
     - Create a new class that implements the `Runnable` interface and implement the `run()` method.
       ```java
       public class MyRunnable implements Runnable {
           public void run() {
               // Thread's code here
           }
       }
       ```
     - Implement the desired logic of the thread within the `run()` method. This method will be executed when the thread starts.
     - Create an instance of the class that implements `Runnable` and pass it as a parameter to the `Thread` class constructor.
       ```java
       MyRunnable runnable = new MyRunnable();
       Thread thread = new Thread(runnable);
       ```
     - Call the `start()` method on the `Thread` instance to start the execution of the thread.
       ```java
       thread.start();
       ```

3. Overriding the `run()` method:
   - In both approaches, you need to override the `run()` method to define the behavior of the thread.
   - The `run()` method contains the actual code that will be executed when the thread starts.
   - It's important to note that you should not call the `run()` method directly. Instead, call the `start()` method, which internally invokes the `run()` method.

Here's an example that demonstrates both approaches:

```java
// Approach 1: Extending the Thread class
public class MyThread extends Thread {
    public void run() {
        System.out.println("Thread is running (Approach 1)");
    }
}

// Approach 2: Implementing the Runnable interface
public class MyRunnable implements Runnable {
    public void run() {
        System.out.println("Thread is running (Approach 2)");
    }
}

public class Main {
    public static void main(String[] args) {
        // Creating and starting a thread using approach 1
        MyThread thread1 = new MyThread();
        thread1.start();

        // Creating and starting a thread using approach 2
        MyRunnable runnable = new MyRunnable();
        Thread thread2 = new Thread(runnable);
        thread2.start();
    }
}
```

In the above example, two threads are created: one by extending the `Thread` class (approach 1) and the other by implementing the `Runnable` interface (approach 2). The `run()` method is overridden in both cases to define the behavior of the threads. When the threads start, the corresponding `run()` method is executed, printing a message to the console.

Both approaches have their advantages. Extending the `Thread` class is simpler but restricts the ability to inherit from

 other classes, while implementing the `Runnable` interface allows for better code organization and flexibility by separating the thread behavior from the class hierarchy.


### Implementing Threads

Implementing threads in Java involves creating a class that implements the `Runnable` interface and defining the thread's behavior within the `run()` method. Here's a detailed explanation of implementing threads in Java:

1. Create a class that implements the `Runnable` interface:
   - Create a new class that implements the `Runnable` interface. The `Runnable` interface defines a single method called `run()`.
     ```java
     public class MyRunnable implements Runnable {
         public void run() {
             // Thread's code here
         }
     }
     ```
   - The `run()` method is where you define the logic that will be executed by the thread. This method represents the entry point of the thread.

2. Define the thread's behavior within the `run()` method:
   - Inside the `run()` method, implement the desired behavior of the thread. This can include any sequence of operations or tasks that the thread needs to perform.
   - For example, you can write a loop or invoke other methods to accomplish specific tasks within the thread.
   ```java
   public void run() {
       for (int i = 0; i < 5; i++) {
           System.out.println("Thread is running: " + i);
       }
   }
   ```

3. Create an instance of the class and wrap it in a `Thread` object:
   - To create a thread, create an instance of the class that implements `Runnable` and pass it as a parameter to the `Thread` class constructor.
   ```java
   MyRunnable runnable = new MyRunnable();
   Thread thread = new Thread(runnable);
   ```

4. Start the thread's execution:
   - Call the `start()` method on the `Thread` object to start the execution of the thread. This method will internally call the `run()` method defined in the `Runnable` implementation.
   ```java
   thread.start();
   ```

5. Thread execution:
   - Once the thread is started, the `run()` method defined in the `Runnable` implementation will be executed in a separate thread of execution.
   - The code inside the `run()` method will be executed concurrently with other threads, allowing for parallel execution of tasks.
   - The thread will continue executing until the `run()` method completes or until the thread is explicitly stopped.

Here's a complete example demonstrating the implementation of a thread using the `Runnable` interface:

```java
public class MyRunnable implements Runnable {
    public void run() {
        for (int i = 0; i < 5; i++) {
            System.out.println("Thread is running: " + i);
        }
    }
}

public class Main {
    public static void main(String[] args) {
        MyRunnable runnable = new MyRunnable();
        Thread thread = new Thread(runnable);
        thread.start();
    }
}
```

In the above example, a new thread is created by implementing the `Runnable` interface. The `run()` method is implemented to print numbers from 0 to 4. The `run()` method will be executed concurrently when the thread is started using the `start()` method.

Implementing threads using the `Runnable` interface provides more flexibility compared to extending the `Thread` class because it allows you to separate the thread's behavior from the class hierarchy. Additionally, multiple threads can share the same instance of the `Runnable` implementation, making it more efficient and reusable.

### Extending Threads

Extending threads in Java involves creating a class that extends the `Thread` class and overrides the `run()` method to define the thread's behavior. Here's a detailed explanation of extending threads in Java:

1. Create a class that extends the `Thread` class:
   - Create a new class that extends the `Thread` class. This class will serve as your custom thread implementation.
   ```java
   public class MyThread extends Thread {
       // Thread's code here
   }
   ```

2. Override the `run()` method:
   - Inside the class that extends `Thread`, override the `run()` method. The `run()` method represents the entry point of the thread where you define the behavior of the thread.
   ```java
   public class MyThread extends Thread {
       public void run() {
           // Thread's code here
       }
   }
   ```

3. Define the thread's behavior within the `run()` method:
   - Inside the `run()` method, implement the desired behavior of the thread. This can include any sequence of operations or tasks that the thread needs to perform.
   - For example, you can write a loop or invoke other methods to accomplish specific tasks within the thread.
   ```java
   public class MyThread extends Thread {
       public void run() {
           for (int i = 0; i < 5; i++) {
               System.out.println("Thread is running: " + i);
           }
       }
   }
   ```

4. Create an instance of the custom thread class:
   - Create an instance of the class that extends `Thread` to represent your custom thread.
   ```java
   MyThread thread = new MyThread();
   ```

5. Start the thread's execution:
   - Call the `start()` method on the thread instance to start the execution of the thread. This method will internally call the `run()` method that you have overridden.
   ```java
   thread.start();
   ```

6. Thread execution:
   - Once the thread is started, the `run()` method defined in the custom thread class will be executed in a separate thread of execution.
   - The code inside the `run()` method will be executed concurrently with other threads, allowing for parallel execution of tasks.
   - The thread will continue executing until the `run()` method completes or until the thread is explicitly stopped.

Here's a complete example demonstrating the extension of the `Thread` class:

```java
public class MyThread extends Thread {
    public void run() {
        for (int i = 0; i < 5; i++) {
            System.out.println("Thread is running: " + i);
        }
    }
}

public class Main {
    public static void main(String[] args) {
        MyThread thread = new MyThread();
        thread.start();
    }
}
```

In the above example, a new thread is created by extending the `Thread` class. The `run()` method is overridden to print numbers from 0 to 4. The `run()` method will be executed concurrently when the thread is started using the `start()` method.

Extending the `Thread` class provides a straightforward way to define and use threads in Java. However, it limits the ability to inherit from other classes since Java does not support multiple inheritance. In cases where you need more flexibility or want to separate the thread behavior from the class hierarchy, implementing the `Runnable` interface is a preferred approach.

### Thread Priorities

In Java, thread priorities are used to determine the relative importance or urgency of threads in concurrent execution. Thread priorities are represented by integer values ranging from 1 (lowest priority) to 10 (highest priority). The default priority for threads is 5.

Thread priorities are used by the Java runtime environment to allocate CPU time to threads. Higher priority threads are given preferential treatment in terms of CPU scheduling, but it's important to note that thread priorities are only hints and not guarantees of the exact order of execution.

Here's a detailed explanation of thread priorities in Java:

1. Setting Thread Priority:
   - You can set the priority of a thread using the `setPriority(int priority)` method, where `priority` is an integer value representing the desired priority.
   - Thread priorities are defined as static constants in the `Thread` class, such as `Thread.MIN_PRIORITY`, `Thread.NORM_PRIORITY`, and `Thread.MAX_PRIORITY`.
   - To set the priority of a thread, call the `setPriority()` method on the `Thread` instance.
   ```java
   Thread thread = new Thread();
   thread.setPriority(Thread.MAX_PRIORITY);
   ```

2. Getting Thread Priority:
   - You can retrieve the priority of a thread using the `getPriority()` method, which returns an integer representing the current priority of the thread.
   ```java
   int priority = thread.getPriority();
   ```

3. Thread Priority Levels:
   - Java defines thread priorities as integer values ranging from 1 to 10, with 1 being the lowest priority and 10 being the highest priority.
   - The constants `Thread.MIN_PRIORITY`, `Thread.NORM_PRIORITY`, and `Thread.MAX_PRIORITY` represent the minimum, default, and maximum priority values, respectively.
   - The actual mapping of thread priorities to system priorities is platform-dependent, and the JVM may adjust the priorities to match the underlying operating system's priority levels.

4. Thread Scheduling:
   - Thread priorities influence the order in which threads are scheduled for execution by the JVM's thread scheduler.
   - The JVM uses a preemptive priority-based scheduling algorithm to allocate CPU time to threads.
   - Higher priority threads have a better chance of being executed before lower priority threads, but it's not guaranteed.
   - The thread scheduler makes the final decision on thread execution based on factors such as thread priorities, CPU availability, and thread state.

It's important to use thread priorities judiciously and avoid excessive reliance on them for achieving precise control over thread execution. The behavior of thread scheduling can vary across different JVM implementations and operating systems.

Here's an example that demonstrates setting and getting thread priorities:

```java
public class MyRunnable implements Runnable {
    public void run() {
        System.out.println("Thread priority: " + Thread.currentThread().getPriority());
    }
}

public class Main {
    public static void main(String[] args) {
        Thread thread1 = new Thread(new MyRunnable());
        thread1.setPriority(Thread.MIN_PRIORITY);

        Thread thread2 = new Thread(new MyRunnable());
        thread2.setPriority(Thread.MAX_PRIORITY);

        thread1.start();
        thread2.start();
    }
}
```

In the above example, two threads are created using the `Runnable` interface. The priorities of the threads are set using the `setPriority()` method. The `run()` method in the `MyRunnable` class simply prints the priority of the current thread. When the threads start, their priorities are displayed. The thread with minimum priority will typically be scheduled to execute after the thread with maximum priority.

### Synchronisation Suspending

In Java, synchronization is used to control the concurrent access of multiple threads to shared resources, ensuring that only one thread can access the resource at a time. Synchronization is crucial to prevent data inconsistencies and race conditions that can occur when multiple threads access and modify shared data simultaneously.

When it comes to suspending threads in a synchronized context, there are two common scenarios to consider:

1. Suspending a Thread:
   - If you want to temporarily suspend the execution of a thread, you can use the `wait()` method provided by the `Object` class.
   - To suspend a thread, you need to acquire the intrinsic lock (also known as the monitor) of the object on which you're invoking the `wait()` method.
   - The `wait()` method causes the current thread to release the lock and enter a suspended state until it is notified by another thread.
   - Here's an example:
     ```java
     synchronized (sharedObject) {
         // Perform some operations
         sharedObject.wait(); // Suspend the thread
         // Thread resumes when notified
     }
     ```

2. Resuming a Suspended Thread:
   - To resume a suspended thread, you need to invoke the `notify()` or `notifyAll()` method on the same object from a different thread.
   - The `notify()` method wakes up one of the threads that are waiting on the object, allowing it to continue its execution.
   - The `notifyAll()` method wakes up all the threads that are waiting on the object.
   - The awakened thread(s) will compete for the lock and continue their execution from the point where they were suspended.
   - Here's an example:
     ```java
     synchronized (sharedObject) {
         // Perform some operations
         sharedObject.notify(); // Resume a single waiting thread
         // Or use sharedObject.notifyAll() to resume all waiting threads
     }
     ```

It's important to note that suspending and resuming threads using `wait()` and `notify()` should be used with caution, as improper use can lead to potential deadlocks or other synchronization issues. Care must be taken to ensure that threads are properly resumed and that the necessary conditions for thread resumption are met.

Additionally, the `wait()` and `notify()` methods should always be called within a synchronized context to ensure proper thread synchronization and avoid IllegalMonitorStateException.

Here's a complete example illustrating the usage of `wait()` and `notify()`:

```java
public class SharedObject {
    public synchronized void printMessage() {
        System.out.println("Thread " + Thread.currentThread().getName() + " is executing.");

        try {
            wait(); // Suspend the thread
        } catch (InterruptedException e) {
            e.printStackTrace();
        }

        System.out.println("Thread " + Thread.currentThread().getName() + " is resuming.");
    }

    public synchronized void resumeThread() {
        notify(); // Resume the waiting thread
    }
}

public class Main {
    public static void main(String[] args) {
        SharedObject sharedObject = new SharedObject();

        Thread thread1 = new Thread(() -> sharedObject.printMessage());
        Thread thread2 = new Thread(() -> sharedObject.resumeThread());

        thread1.start();

        try {
            Thread.sleep(2000); // Wait for some time
        } catch (InterruptedException e) {
            e.printStackTrace();
        }

        thread2.start();
    }
}
```

In the above example, `SharedObject` represents the shared resource. The `printMessage()` method is invoked by `thread1`, which acquires the lock and enters a suspended state using `wait()`. After a delay of 2 seconds, `thread2` invokes the `resumeThread()` method, which calls `notify()` to wake up `thread1` and allow it to resume execution.

### Resuming and Stopping threads

In Java, resuming and stopping threads involve managing their execution state and controlling their lifecycle. Let's delve into each aspect in detail:

1. Resuming Threads:
   - In Java, there is no direct mechanism to resume a suspended or paused thread. The `Thread` class provides methods such as `suspend()` and `resume()` for this purpose, but they are deprecated and not recommended for use due to potential thread deadlock issues.
   - Instead of explicitly resuming a thread, you can design your code to use synchronization mechanisms such as `wait()` and `notify()` or higher-level constructs like `Lock` and `Condition` to control the execution flow between threads.
   - By releasing locks or signaling conditions, you can enable suspended threads to continue their execution.

2. Stopping Threads:
   - Stopping threads in Java involves terminating their execution gracefully. It's essential to ensure that threads release resources and perform any necessary cleanup operations before they exit.
   - The `Thread` class provides a `stop()` method to force a thread to stop its execution. However, this method is deprecated and considered unsafe to use because it can leave resources in an inconsistent state.
   - A recommended approach to stop threads is to use cooperative cancellation, where the threads are designed to check a condition periodically and exit gracefully when the condition is met.
   - You can define a flag or a shared variable that indicates the cancellation condition, and the thread can periodically check this condition within its execution loop to determine if it should terminate.
   - Here's an example demonstrating cooperative cancellation:
     ```java
     public class MyRunnable implements Runnable {
         private volatile boolean isRunning = true;

         public void run() {
             while (isRunning) {
                 // Perform some work

                 if (Thread.currentThread().isInterrupted()) {
                     // Handle interruption, cleanup, and exit if needed
                     break;
                 }
             }
         }

         public void stopThread() {
             isRunning = false;
         }
     }

     public class Main {
         public static void main(String[] args) {
             MyRunnable runnable = new MyRunnable();
             Thread thread = new Thread(runnable);
             thread.start();

             // Let the thread run for some time

             thread.interrupt(); // Signal the thread to stop

             // Perform any necessary cleanup
         }
     }
     ```

   - In the above example, the `MyRunnable` class implements the `Runnable` interface and defines a `isRunning` flag to control the execution loop. The thread periodically checks this flag and exits when it's set to `false`.
   - The `stopThread()` method can be called to set the `isRunning` flag to `false`, signaling the thread to stop.
   - In the `Main` class, a `Thread` instance is created with the `MyRunnable` instance and started. After some time, the thread is interrupted using `thread.interrupt()` to signal it to stop. Finally, any necessary cleanup operations can be performed.

It's important to note that when stopping or interrupting threads, proper synchronization mechanisms and cooperation between threads are crucial to avoid data inconsistencies or resource leaks. Cooperative cancellation allows threads to clean up resources and exit gracefully, promoting thread safety and integrity of the application.


### Constructors

In Java, a constructor is a special method used to initialize objects of a class. It is called automatically when an instance of a class is created using the `new` keyword. Constructors have the same name as the class they belong to and do not have a return type, not even `void`.

Here are some key points about constructors in Java:

1. Purpose of Constructors:
   - Constructors are used to initialize the state of an object by assigning initial values to its instance variables.
   - They ensure that an object is properly set up and in a valid state before it can be used.

2. Default Constructor:
   - If a class does not explicitly define any constructors, Java provides a default constructor automatically.
   - The default constructor has no arguments and initializes the object with default values (e.g., `0` for numeric types, `false` for booleans, `null` for object references).
   - It can be explicitly defined in the class if needed.

3. Parameterized Constructors:
   - A class can have one or more parameterized constructors, which accept arguments to initialize the object with specific values.
   - By providing different sets of arguments, you can create objects with different initial states.
   - Multiple constructors can be defined in a class with different parameter lists (known as constructor overloading).

4. Constructor Overloading:
   - Constructor overloading allows a class to have multiple constructors with different parameter lists.
   - The constructors should have unique parameter combinations to distinguish them from one another.
   - Overloaded constructors provide flexibility in creating objects with varying initializations.

5. Calling One Constructor from Another (Constructor Chaining):
   - In Java, constructors can call other constructors in the same class using the `this()` keyword.
   - This enables reusability and avoids code duplication when multiple constructors need to perform similar initialization tasks.
   - The `this()` call should be the first statement in the constructor body.

Here's an example illustrating the usage of constructors in Java:

```java
public class Person {
    private String name;
    private int age;

    // Default constructor
    public Person() {
        name = "John Doe";
        age = 30;
    }

    // Parameterized constructor
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // Getter methods for name and age

    public String getName() {
        return name;
    }

    public int getAge() {
        return age;
    }
}

public class Main {
    public static void main(String[] args) {
        Person person1 = new Person(); // Using default constructor
        System.out.println(person1.getName()); // Output: John Doe
        System.out.println(person1.getAge()); // Output: 30

        Person person2 = new Person("Alice", 25); // Using parameterized constructor
        System.out.println(person2.getName()); // Output: Alice
        System.out.println(person2.getAge()); // Output: 25
    }
}
```

In the above example, the `Person` class has a default constructor that initializes the `name` and `age` variables with default values. It also has a parameterized constructor that accepts arguments to set the `name` and `age` variables.

In the `Main` class, we create two `Person` objects using different constructors. The first object `person1` is created using the default constructor, while the second object `person2` is created using the parameterized constructor. We then access the `name` and `age` properties of both objects using the getter methods.

Constructors are essential for initializing objects with specific values and ensuring that objects are properly set up before use. They play a crucial role in object-oriented programming and

 help in creating robust and reliable code.


 ### Various types of String Operations

 In Java, the `String` class provides various methods to perform operations on strings. Here are some commonly used string operations in Java:

1. Concatenation:
   - The `concat()` method is used to concatenate two strings together.
   - Alternatively, you can use the `+` operator to concatenate strings.
   - Example:
     ```java
     String str1 = "Hello";
     String str2 = "World";
     String result = str1.concat(str2); // "HelloWorld"
     // or
     String result = str1 + str2; // "HelloWorld"
     ```

2. Length:
   - The `length()` method returns the length of the string.
   - Example:
     ```java
     String str = "Hello";
     int length = str.length(); // 5
     ```

3. Substring:
   - The `substring()` method returns a portion of the string.
   - It can be used with a starting index and an optional ending index.
   - Example:
     ```java
     String str = "HelloWorld";
     String sub = str.substring(5); // "World"
     String sub2 = str.substring(0, 5); // "Hello"
     ```

4. Comparison:
   - The `equals()` method compares two strings for equality.
   - The `equalsIgnoreCase()` method performs a case-insensitive comparison.
   - Example:
     ```java
     String str1 = "Hello";
     String str2 = "Hello";
     boolean isEqual = str1.equals(str2); // true
     boolean isEqualIgnoreCase = str1.equalsIgnoreCase("hello"); // true
     ```

5. Searching:
   - The `indexOf()` method returns the index of the first occurrence of a specified substring.
   - The `lastIndexOf()` method returns the index of the last occurrence of a specified substring.
   - Example:
     ```java
     String str = "HelloWorld";
     int index = str.indexOf("l"); // 2
     int lastIndex = str.lastIndexOf("l"); // 9
     ```

6. Case Conversion:
   - The `toUpperCase()` method converts the string to uppercase.
   - The `toLowerCase()` method converts the string to lowercase.
   - Example:
     ```java
     String str = "Hello";
     String upperCase = str.toUpperCase(); // "HELLO"
     String lowerCase = str.toLowerCase(); // "hello"
     ```

7. Splitting:
   - The `split()` method splits the string into an array of substrings based on a delimiter.
   - Example:
     ```java
     String str = "Hello,World";
     String[] parts = str.split(","); // ["Hello", "World"]
     ```

8. Formatting:
   - The `format()` method formats a string using placeholders and specified arguments.
   - Example:
     ```java
     String str = String.format("The value is %d", 42); // "The value is 42"
     ```

These are just a few examples of the string operations available in Java. The `String` class offers many more methods for manipulating and working with strings. It's important to consult the Java documentation for a comprehensive list of available methods and their usages.

### I/O using java.io package

In Java, the `java.io` package provides classes for performing Input/Output (I/O) operations. It offers various classes and interfaces to read from and write to different sources such as files, streams, and consoles. Here's an overview of the key classes in the `java.io` package:

1. `InputStream` and `OutputStream`:
   - These abstract classes are the foundation for reading from and writing to byte streams.
   - `InputStream` is used for reading bytes from a source, while `OutputStream` is used for writing bytes to a destination.
   - Examples of subclasses include `FileInputStream`, `ByteArrayInputStream`, `FileOutputStream`, and `ByteArrayOutputStream`.

2. `Reader` and `Writer`:
   - These abstract classes provide functionality for reading and writing characters from/to character streams.
   - `Reader` is used for reading characters, while `Writer` is used for writing characters.
   - Examples of subclasses include `FileReader`, `StringReader`, `FileWriter`, and `StringWriter`.

3. `File`:
   - The `File` class represents a file or directory in the file system.
   - It provides methods to perform operations such as creating, deleting, renaming, and querying file properties.
   - Examples of file-related operations include `createNewFile()`, `delete()`, `renameTo()`, and `exists()`.

4. `BufferedReader` and `BufferedWriter`:
   - These classes provide buffering functionality, which improves I/O performance.
   - `BufferedReader` reads text from a character input stream with an internal buffer, reducing the number of actual reads from the underlying stream.
   - `BufferedWriter` writes text to a character output stream with an internal buffer, reducing the number of actual writes to the underlying stream.

Now, let's see an example that demonstrates reading from a file using `FileInputStream` and `BufferedReader`:

```java
import java.io.BufferedReader;
import java.io.FileInputStream;
import java.io.IOException;
import java.io.InputStreamReader;

public class FileReaderExample {
    public static void main(String[] args) {
        try (FileInputStream fileInputStream = new FileInputStream("input.txt");
             InputStreamReader inputStreamReader = new InputStreamReader(fileInputStream);
             BufferedReader bufferedReader = new BufferedReader(inputStreamReader)) {

            String line;
            while ((line = bufferedReader.readLine()) != null) {
                System.out.println(line);
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

In the above example:
- We create a `FileInputStream` to open the file `input.txt` for reading.
- We create an `InputStreamReader` to convert the bytes from the `FileInputStream` into characters.
- We create a `BufferedReader` to read text from the `InputStreamReader` with buffering capabilities.
- Inside the `try` block, we use a `while` loop to read each line from the file using the `readLine()` method of `BufferedReader`.
- The loop continues until `readLine()` returns `null`, indicating the end of the file.
- Each line is then printed to the console.

It's important to handle exceptions properly when working with I/O operations to ensure proper resource management and error handling. In the example above, we use a try-with-resources statement to automatically close the resources after usage, using the `AutoCloseable` interface implemented by the classes involved in the I/O operations.

