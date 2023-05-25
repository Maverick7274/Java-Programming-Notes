# IT201 Java Programming

## Module 5

### Java Annotations

In Java, annotations provide a way to add metadata or information about elements in your code, such as classes, methods, fields, or parameters. Annotations are defined using the `@interface` keyword and can be used to convey additional information to the compiler, runtime environment, or other tools. Here are some commonly used types of annotations in Java:

1. Marker Annotations:
   Marker annotations do not have any elements. They simply mark the annotated element with some information. Examples of marker annotations in Java include `@Override`, `@Deprecated`, and `@SuppressWarnings`.

2. Single-Value Annotations:
   Single-value annotations have a single element and require a value to be specified when used. The value can be assigned using the `value()` element. An example of a single-value annotation is `@SuppressWarnings`, which can suppress specific compiler warnings.

3. Multi-Value Annotations:
   Multi-value annotations have multiple elements and allow you to specify values for each element. Each element has a name and can be assigned a value using the syntax `elementName = value`. An example of a multi-value annotation is `@Author`, which can have elements like `name`, `date`, and `comments`.

4. Meta-Annotations:
   Meta-annotations are annotations that are used to annotate other annotations. They provide additional information or semantics about the annotated annotation. Examples of meta-annotations in Java include `@Retention`, `@Target`, and `@Documented`.

5. Retention Annotations:
   Retention annotations specify how long the annotated elements should be retained. The `@Retention` meta-annotation is used to annotate other annotations and can take values such as `SOURCE`, `CLASS`, or `RUNTIME`. The `RUNTIME` retention policy allows annotations to be accessible at runtime through reflection.

6. Target Annotations:
   Target annotations specify the types of elements to which the annotation can be applied. The `@Target` meta-annotation is used to specify the target elements and can include values like `TYPE`, `METHOD`, `FIELD`, `PARAMETER`, and more.

7. Documented Annotations:
   Documented annotations indicate that the annotated element's presence should be documented by tools like Javadoc. The `@Documented` meta-annotation is used to annotate other annotations.

These are just a few examples of Java annotations and their types. You can also create your own custom annotations by defining an annotation interface using the `@interface` keyword and specifying the desired elements. Annotations provide a flexible way to extend the Java language and enable developers to add and process metadata in their code.

### Annotations library & Create custom annotations

To create custom annotations in Java, you can define an annotation interface using the `@interface` keyword. Here's an example of how you can create a custom annotation using the Java Annotations library:

```java
import java.lang.annotation.*;

@Retention(RetentionPolicy.RUNTIME) // Specifies that the annotation should be accessible at runtime
@Target(ElementType.METHOD) // Specifies that the annotation can be applied to methods
public @interface CustomAnnotation {
    String value(); // A single element named "value" of type String
    int priority() default 0; // An optional element named "priority" of type int with a default value of 0
    boolean enabled() default true; // An optional element named "enabled" of type boolean with a default value of true
}
```

In the above example, we defined a custom annotation `CustomAnnotation`. It has three elements: `value()`, `priority()`, and `enabled()`. The `value()` element is a required element of type `String`, while `priority()` and `enabled()` are optional elements of type `int` and `boolean`, respectively, with default values.

To use this custom annotation, you can apply it to methods in your code as follows:

```java
public class MyClass {
    @CustomAnnotation(value = "Custom Annotation Example", priority = 2, enabled = false)
    public void myMethod() {
        // Method implementation
    }
}
```

In the example above, the `@CustomAnnotation` is applied to the `myMethod()` method of the `MyClass` class. The annotation is provided with values for its elements, such as the `value`, `priority`, and `enabled` attributes.

You can access and process this custom annotation at runtime using reflection. For example, you can retrieve the annotation and its values from the annotated method:

```java
import java.lang.reflect.Method;

public class Main {
    public static void main(String[] args) throws NoSuchMethodException {
        Method method = MyClass.class.getMethod("myMethod");
        CustomAnnotation annotation = method.getAnnotation(CustomAnnotation.class);

        if (annotation != null) {
            String value = annotation.value();
            int priority = annotation.priority();
            boolean enabled = annotation.enabled();

            System.out.println("Value: " + value);
            System.out.println("Priority: " + priority);
            System.out.println("Enabled: " + enabled);
        }
    }
}
```

In the above example, we retrieve the `myMethod()` method using reflection and then use the `getAnnotation()` method to obtain the `CustomAnnotation` object. Finally, we can access the values of the annotation's elements.

Remember to ensure that the custom annotation is retained at runtime by specifying `@Retention(RetentionPolicy.RUNTIME)` on the annotation declaration, as shown in the first code snippet. This allows you to access the annotation information at runtime.

### Maven

Maven is a powerful build automation and dependency management tool for Java projects. It provides a structured approach to managing project dependencies, building and packaging projects, and facilitating project management tasks. Maven uses a declarative approach and convention over configuration principles to simplify project setup and development.

Here are some key concepts and features of Maven:

1. Project Object Model (POM):
   At the heart of Maven is the Project Object Model (POM). The POM is an XML file that describes the project's configuration, dependencies, build settings, and other project-related information. It serves as the project's central configuration file.

2. Dependency Management:
   Maven simplifies dependency management by allowing you to declare project dependencies in the POM file. Maven can automatically download and manage the required dependencies from remote repositories. It resolves transitive dependencies (dependencies of dependencies) and ensures that the correct versions are used.

3. Build Lifecycle and Phases:
   Maven defines a standard build lifecycle that consists of phases. Each phase represents a specific stage in the project's lifecycle, such as compiling sources, running tests, packaging, and deploying. Maven provides a set of predefined plugins that perform these build tasks during the corresponding phases.

4. Plugins and Goals:
   Plugins are extensions to Maven that provide additional functionality and custom build tasks. Maven plugins are configured in the POM file and can be bound to specific build phases. Each plugin can define multiple goals, which represent specific tasks that can be executed.

5. Convention over Configuration:
   Maven follows a convention over configuration approach. It uses a standard project directory structure, where source code, resources, and other artifacts are placed in predefined directories. Maven automatically recognizes and configures the project based on these conventions, reducing the need for explicit configuration.

6. Repository Management:
   Maven works with repositories, which are locations that store and provide access to project dependencies and plugins. Maven supports both local repositories (stored on the developer's machine) and remote repositories (accessible over the internet). Maven can download dependencies from remote repositories and cache them in the local repository for future use.

7. Build Profiles:
   Maven allows you to define profiles in the POM file to customize the build process for different environments or build configurations. Profiles can define different sets of dependencies, build options, or plugin configurations. You can activate profiles based on conditions such as specific command-line arguments or environment variables.

8. Integration with IDEs:
   Maven integrates well with popular Integrated Development Environments (IDEs) such as Eclipse, IntelliJ IDEA, and NetBeans. IDEs can import Maven projects, understand the POM file structure, and provide features like automatic dependency management, build support, and code assistance.

Maven simplifies the management of complex Java projects by providing a consistent and standardized approach to building, testing, and packaging. It promotes code reusability, collaboration, and automation, making it a popular choice for Java developers and organizations.


### Repositories in Maven

In Maven, repositories play a crucial role in managing dependencies and plugins for your projects. A repository is a location where Maven looks for and downloads dependencies and plugins. There are two types of repositories in Maven:

1. Local Repository:
   The local repository is a directory located on your machine where Maven stores downloaded artifacts (dependencies and plugins). By default, the local repository is located in the `.m2` directory in your user's home directory (`~/.m2/repository` on Unix-based systems or `C:\Users\{username}\.m2\repository` on Windows). When you build a project, Maven first checks the local repository for the required artifacts. If they are not found, it downloads them from remote repositories and caches them locally for future use.

2. Remote Repository:
   A remote repository is a repository hosted on a remote server that provides access to dependencies and plugins over the internet. When Maven needs to download an artifact, it searches for it in the local repository first. If the artifact is not found locally, Maven looks in the remote repositories configured for the project. If the artifact is found, it is downloaded and stored in the local repository for future use. Maven supports various remote repository formats, such as Maven Central Repository, JCenter, and custom repositories.

Configuring Repositories:
To configure repositories in Maven, you need to modify the `<repositories>` section in the project's POM (Project Object Model) file. The POM file typically resides in the root directory of your project. Here's an example of how to configure repositories in the POM file:

```xml
<project>
    <!-- Other project configuration -->

    <repositories>
        <repository>
            <id>central</id>
            <url>https://repo.maven.apache.org/maven2</url>
        </repository>
        <!-- Additional repositories can be added here -->
    </repositories>

    <!-- Other project configuration -->
</project>
```

In the example above, the `<repositories>` section is used to define repositories. Each `<repository>` element represents a remote repository and contains two sub-elements: `<id>` and `<url>`. The `<id>` element provides a unique identifier for the repository, while the `<url>` element specifies the URL or location of the repository.

Maven Central Repository is the default and most commonly used repository for Maven artifacts. It is pre-configured in Maven by default, so you do not need to explicitly add it to your POM file. However, you can define additional repositories to access artifacts not available in the central repository or to configure custom repositories.

Additionally, Maven allows you to configure repositories at the user level by modifying the `settings.xml` file located in the `.m2` directory. This allows you to define repositories globally that can be used across multiple projects.

By configuring repositories properly in Maven, you ensure that the required dependencies and plugins can be resolved and downloaded during the build process, enabling a smooth and automated development workflow.

### Plugins in Maven

In Maven, plugins are key components that extend the functionality of the build process. They provide additional goals (tasks) that can be executed during different phases of the build lifecycle. Plugins enable you to perform various tasks such as compiling code, running tests, generating documentation, deploying artifacts, and more. Here's an overview of plugins in Maven:

1. Built-in Plugins:
   Maven comes with a set of built-in plugins that provide essential functionality out of the box. These plugins are automatically available in your Maven projects without requiring any additional configuration. Some common built-in plugins include:
   - `maven-compiler-plugin`: Compiles Java source code.
   - `maven-surefire-plugin`: Runs unit tests.
   - `maven-jar-plugin`: Creates a JAR file from the project's compiled classes.
   - `maven-install-plugin`: Installs artifacts into the local repository.
   - `maven-deploy-plugin`: Deploys artifacts to a remote repository.

2. Plugin Configuration:
   Plugins are configured in the project's POM (Project Object Model) file. The `<build>` section of the POM is used to specify plugin configurations. Each plugin can have multiple goals, and each goal can be bound to specific build phases. You can customize the behavior of a plugin by providing configuration parameters within the `<configuration>` element. For example:
   ```xml
   <build>
       <plugins>
           <plugin>
               <groupId>org.apache.maven.plugins</groupId>
               <artifactId>maven-compiler-plugin</artifactId>
               <version>3.8.1</version>
               <configuration>
                   <source>1.8</source>
                   <target>1.8</target>
               </configuration>
           </plugin>
       </plugins>
   </build>
   ```
   In the above example, the `maven-compiler-plugin` is configured to set the Java source and target version to 1.8.

3. Plugin Execution:
   Plugins are executed during specific build phases or can be invoked manually from the command line using the `mvn pluginName:goal` syntax. For example, to execute the `test` goal of the `maven-surefire-plugin`, you can run `mvn surefire:test`. The order of plugin execution is determined by the predefined build lifecycle, but you can customize the execution order by binding goals to different phases.

4. Plugin Management:
   Maven allows you to manage plugin versions and dependencies in the `<build>` section of the POM file. The `<pluginManagement>` element is used to specify default configurations and versions for plugins. By defining plugin configurations in the `<pluginManagement>` section, you can apply them consistently across multiple projects without repeating the configuration in each project's POM.

5. Custom Plugins:
   Besides the built-in plugins, you can create your own custom Maven plugins to cater to specific project requirements. Custom plugins are typically packaged as JAR files and can be developed using tools such as Apache Maven Plugin Tools or Apache Maven Archetype. Custom plugins enable you to extend Maven's capabilities and automate project-specific tasks.

Maven's plugin architecture provides a flexible and extensible way to customize the build process. By leveraging built-in plugins and creating custom plugins, you can automate various development tasks and integrate them seamlessly into your project's build lifecycle.

### Goal & Lifecycle in Maven

In Maven, a goal represents a specific task that can be executed by a plugin during the build process. Goals are associated with plugins and can be bound to different build phases. When you run a Maven command, you specify the plugin and the goal to execute.

Build Lifecycle:
The build lifecycle in Maven consists of a predefined sequence of phases. Each phase represents a stage in the build process, such as compiling code, running tests, packaging, and deploying artifacts. The build lifecycle is organized into three built-in lifecycles:

1. Clean Lifecycle:
   The Clean lifecycle is responsible for cleaning the project by removing any generated output from previous builds. It includes the following phases:
   - `pre-clean`: Executes tasks before the project is cleaned.
   - `clean`: Deletes the build output directory.

2. Default Lifecycle:
   The Default lifecycle is the primary lifecycle used for most projects. It includes the following phases:
   - `validate`: Validates the project's configuration.
   - `compile`: Compiles the project's source code.
   - `test`: Runs unit tests against the compiled source code.
   - `package`: Packages the compiled code into a distributable format, such as a JAR or WAR file.
   - `verify`: Runs additional checks to verify the package.
   - `install`: Installs the package into the local repository for use by other projects.
   - `deploy`: Deploys the package to a remote repository or server.

3. Site Lifecycle:
   The Site lifecycle is used for generating project documentation and reports. It includes the following phases:
   - `pre-site`: Executes tasks before the project documentation is generated.
   - `site`: Generates project documentation.
   - `post-site`: Executes tasks after the project documentation is generated.
   - `site-deploy`: Deploys the generated documentation to a remote server.

When you run a Maven command, you specify a build phase, and Maven executes all the phases up to and including the specified phase. For example, running `mvn compile` will execute all the phases up to and including the `compile` phase in the default lifecycle.

Binding Goals to Phases:
Plugins are bound to specific build phases, and their goals are executed when the associated phase is reached. The plugin configuration in the POM file specifies which goals are bound to which phases. By default, plugins are bound to phases based on naming conventions. For example, the `maven-compiler-plugin` is bound to the `compile` phase, and the `maven-surefire-plugin` is bound to the `test` phase.

You can customize the binding of goals to phases by specifying the `<executions>` element in the plugin configuration. This allows you to execute plugin goals at specific points in the build process, in addition to their default bindings. Multiple executions can be defined for a single plugin, each with its own set of goals and phase bindings.

For example, you can bind the `clean` goal of the `maven-clean-plugin` to the `clean` phase by adding the following configuration in your POM file:

```xml
<build>
    <plugins>
        <plugin>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-clean-plugin</artifactId>
            <version>3.1.0</version>
            <executions>
                <execution>
                    <phase>clean</phase>
                    <goals>
                        <goal>clean</goal>
                    </goals>
                </execution>
            </executions>
        </plugin>
    </plugins>
</build>
```

In the above example, the `maven-clean-plugin` is bound to the `clean` phase, and its `clean` goal will be executed when the `clean` phase is reached

.

By binding goals to different phases, you can customize the build process and control when specific tasks are executed during the build lifecycle.

### GAV – Maven coordinates

GAV (Group, Artifact, Version) coordinates, also known as Maven coordinates, are a standardized way to identify and locate artifacts in Maven. These coordinates are used to uniquely identify a specific library or module within a Maven repository. The GAV coordinates consist of the following components:

1. Group ID (G):
   The Group ID represents the organization or group that is responsible for the artifact. It is typically based on the reverse domain name convention. For example, `com.example` or `org.openai`.

2. Artifact ID (A):
   The Artifact ID identifies the specific artifact or module within the group. It is typically the name of the project or library. For example, `my-library` or `common-utils`.

3. Version (V):
   The Version indicates the specific version of the artifact. It can be a numeric version, such as `1.0` or `2.3.1`, or include additional qualifiers like `SNAPSHOT`, `alpha`, `beta`, etc., to denote different stages of development.

By combining these three components, Maven coordinates uniquely identify an artifact in a Maven repository. Here is an example of Maven coordinates for a library:

```
<groupId>com.example</groupId>
<artifactId>my-library</artifactId>
<version>1.0.0</version>
```

Maven uses these coordinates to resolve dependencies and retrieve the required artifacts from remote repositories. When you declare a dependency in your project's POM file, you specify the GAV coordinates of the required library. Maven then searches the configured repositories for the matching artifact based on these coordinates and downloads it to the local repository for use in your project.

Maven coordinates provide a consistent and standardized way to identify and manage dependencies in Maven projects. They simplify dependency management and ensure that the correct versions of artifacts are used in your project, promoting build reproducibility and ease of collaboration.

## Creating a `pom.xml` and installing a core java application

To create a `pom.xml` file and install a core Java application using Maven, follow these steps:

Step 1: Create Project Directory
Create a new directory for your project. You can choose any name for the directory.

Step 2: Create `pom.xml` File
Inside the project directory, create a file named `pom.xml`. This file will contain the project configuration and dependencies.

Open the `pom.xml` file in a text editor and add the following content as a starting point:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0
                             http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>
    
    <groupId>com.example</groupId>
    <artifactId>my-application</artifactId>
    <version>1.0.0</version>
    
    <properties>
        <maven.compiler.source>1.8</maven.compiler.source>
        <maven.compiler.target>1.8</maven.compiler.target>
    </properties>
    
    <dependencies>
        <!-- Add your dependencies here -->
    </dependencies>
</project>
```

In the above `pom.xml` snippet, replace the values of `<groupId>`, `<artifactId>`, and `<version>` with your desired values. These values will be used as the Maven coordinates for your project.

Step 3: Add Dependencies (Optional)
If your core Java application requires any external libraries, you can add the dependencies within the `<dependencies>` section of the `pom.xml` file. Specify the group ID, artifact ID, and version of the dependencies you need. For example:

```xml
<dependencies>
    <dependency>
        <groupId>org.example</groupId>
        <artifactId>library1</artifactId>
        <version>1.0.0</version>
    </dependency>
    <dependency>
        <groupId>org.example</groupId>
        <artifactId>library2</artifactId>
        <version>2.0.0</version>
    </dependency>
</dependencies>
```

Step 4: Build and Install the Application
Open a command prompt or terminal, navigate to the project directory (where the `pom.xml` file is located), and run the following command:

```
mvn install
```

Maven will read the `pom.xml` file, download the required dependencies (if any), compile your Java source code, and package it into a JAR file. The JAR file will be installed in the local Maven repository (`~/.m2/repository`) for use in other projects.

Once the installation is complete, you can use the application JAR file and its dependencies in other projects by specifying the appropriate Maven coordinates.

That's it! You have created a `pom.xml` file and installed a core Java application using Maven.

## Project Object Model

The Project Object Model (POM) is an XML file that serves as the fundamental configuration file for a Maven project. It defines the structure, dependencies, plugins, and various other aspects of the project. The POM file, named `pom.xml`, resides in the root directory of the project.

The POM file contains the following key elements:

1. Project Information:
   - `<modelVersion>`: Specifies the version of the POM model. The current version is typically set to `4.0.0`.
   - `<groupId>`: Identifies the group or organization to which the project belongs.
   - `<artifactId>`: Specifies the unique identifier for the project.
   - `<version>`: Defines the version of the project.

2. Project Dependencies:
   - `<dependencies>`: Contains a list of dependencies required by the project. Each dependency is defined within a `<dependency>` block, specifying the group ID, artifact ID, and version.

3. Build Configuration:
   - `<build>`: Contains configuration related to the build process.
   - `<plugins>`: Specifies the plugins used in the project. Each plugin is defined within a `<plugin>` block, specifying the group ID, artifact ID, and version. Additional plugin configuration, such as goals and executions, can be specified within the `<configuration>` element.

4. Project Properties:
   - `<properties>`: Defines project-specific properties that can be referenced throughout the POM file. Properties are specified as key-value pairs and can be used for version numbers, paths, or any other project-specific values.

5. Project Reporting:
   - `<reporting>`: Contains configuration for generating reports and documentation for the project.

The POM file provides a declarative way to define the project's configuration and dependencies. It forms the basis for Maven to perform various build tasks and manage dependencies automatically. By customizing the POM file, you can define project-specific settings, add dependencies, configure plugins, and control the build process.

Maven uses the information specified in the POM file to resolve dependencies, compile source code, run tests, generate documentation, package artifacts, and perform other build-related tasks. It provides a standardized structure and configuration model, allowing for consistent project management and build automation across different Maven projects.