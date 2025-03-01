# Java Tutorials

Welcome to the **Java Tutorials** section. This guide will help you get started with Java, from setting up your environment to exploring key concepts like OOP and working with APIs.

---

## 1. Getting Started with Java ##:

### 1.1 Installing Java ##:

1. Go to the official [Java website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Download the latest **JDK (Java Development Kit)** for your operating system (Windows, macOS, or Linux).
3. Follow the installation instructions for your system.
4. **Set up the JAVA_HOME environment variable**:
   - **Windows**: 
     - Go to **System Properties** > **Advanced** > **Environment Variables**.
     - Under "System Variables", click **New** and set the variable name as `JAVA_HOME` and the value to your JDK installation path (e.g., `C:\Program Files\Java\jdk-11`).
     - Add `;%JAVA_HOME%\bin` to the **Path** variable.

   - **macOS/Linux**: 
     - Open your terminal and run:
       ```bash
       export JAVA_HOME=/usr/lib/jvm/java-11-openjdk
       export PATH=$PATH:$JAVA_HOME/bin
       ```

### 1.2 Setting Up a Java Development Environment ##:

We recommend using **IntelliJ IDEA**, **Eclipse**, or **NetBeans** as your IDE for Java development.

1. Download and install an IDE of your choice:
   - **[IntelliJ IDEA](https://www.jetbrains.com/idea/)**
   - **[Eclipse](https://www.eclipse.org/downloads/)**
   - **[NetBeans](https://netbeans.apache.org/download/index.html)**

2. Set up your IDE to use the JDK you installed earlier.

### 1.3 Writing Your First Java Program ##:

1. Open your IDE and create a new Java project.
2. Create a new class file named `HelloWorld.java`.
3. Add the following code:
   ```java
   public class HelloWorld {
       public static void main(String[] args) {
           System.out.println("Hello, World!");
       }
   }

1.4 Running the Program ##:
Open your terminal and navigate to the directory where HelloWorld.java is located.

Compile the program:

javac HelloWorld.java

Run the compiled program:

java HelloWorld

You should see the output:

Hello, World!

2. Java Variables and Data Types ##:
   
2.1 Variables ##:

Java requires explicit type declaration for variables. For example:

String name = "John";
int age = 25;
double height = 5.9;
boolean isActive = true;

2.2 Data Types ##:

Java supports several data types:

String: Text enclosed in double quotes.

String name = "Alice";

int: Whole numbers

int age = 30;

double: Decimal numbers

double weight = 70.5;

boolean: True or False values.

boolean isActive = true;



2.3 Basic Operators ##:
int x = 10;
int y = 3;

// Arithmetic Operators
System.out.println(x + y);  // Addition
System.out.println(x - y);  // Subtraction
System.out.println(x * y);  // Multiplication
System.out.println(x / y);  // Division

// Comparison Operators
System.out.println(x == y);  // Equal to
System.out.println(x != y);  // Not equal to


3. Java Control Flow ##:

3.1 If Statements ##:

int age = 18;

if (age >= 18) {
    System.out.println("You are an adult.");
} else {
    System.out.println("You are a minor.");
}

3.2 Loops ##:

3.2.1 For Loop ##:

for (int i = 0; i < 5; i++) {
    System.out.println(i);  // Prints 0 to 4
}

3.2.2 While Loop ##:

int count = 0;
while (count < 5) {
    System.out.println(count);
    count++;  // Increment the counter
}


4. Functions (Methods) in Java ##:

 4.1 Defining Methods ##:

Methods are defined inside a class and can take parameters and return values.

public class Main {
    public static void main(String[] args) {
        String message = greet("John");
        System.out.println(message);
    }

    public static String greet(String name) {
        return "Hello, " + name + "!";
    }
}


4.2 Arguments and Return Values ##:

public class Main {
    public static void main(String[] args) {
        int result = add(3, 5);
        System.out.println(result);  // Output: 8
    }

    public static int add(int a, int b) {
        return a + b;
    }
}


5. Java Libraries and Frameworks ##:

5.1 Installing Libraries with Maven ##:

To manage third-party libraries, Java uses Maven. First, add Maven to your project by including a pom.xml file (if your IDE supports Maven).

For example, to add the Apache Commons Lang library:

<dependency>
    <groupId>org.apache.commons</groupId>
    <artifactId>commons-lang3</artifactId>
    <version>3.12.0</version>
</dependency>

You can now use the library in your project:

import org.apache.commons.lang3.StringUtils;

public class Main {
    public static void main(String[] args) {
        String result = StringUtils.capitalize("java");
        System.out.println(result);  // Output: Java
    }
}

5.2 Using the Scanner Class for Input ##:

import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter your name: ");
        String name = scanner.nextLine();

        System.out.println("Hello, " + name + "!");
    }
}




6. Java File Handling ##:


6.1 Reading from a File ##:

import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class Main {
    public static void main(String[] args) throws IOException {
        BufferedReader reader = new BufferedReader(new FileReader("example.txt"));
        String line;

        while ((line = reader.readLine()) != null) {
            System.out.println(line);
        }

        reader.close();
    }
}

6.2 Writing to a File ##:

import java.io.FileWriter;
import java.io.IOException;

public class Main {
    public static void main(String[] args) throws IOException {
        FileWriter writer = new FileWriter("example.txt");

        writer.write("Hello, this is a new file!");
        writer.close();
    }
}

7. Java Working with APIs ##:

7.1 What is an API? ##:
An API (Application Programming Interface) allows your application to interact with other software or services.


7.2 Making a GET Request ##:
Java does not have a built-in HTTP library like Python's requests, but we can use the HttpURLConnection class.

import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.net.HttpURLConnection;
import java.net.URL;

public class Main {
    public static void main(String[] args) throws Exception {
        String url = "https://api.github.com/users/octocat";
        HttpURLConnection connection = (HttpURLConnection) new URL(url).openConnection();
        connection.setRequestMethod("GET");

        BufferedReader in = new BufferedReader(new InputStreamReader(connection.getInputStream()));
        String inputLine;
        StringBuffer response = new StringBuffer();

        while ((inputLine = in.readLine()) != null) {
            response.append(inputLine);
        }

        in.close();
        System.out.println(response.toString());
    }
}


8. Java Practice Projects ##:
Here are a few ideas to practice your Java skills:

To-Do List Application: Create a simple command-line to-do list app.
Currency Converter: Convert between different currencies using an API.
Weather App: Fetch weather data from an API and display it.


9. Next Steps ##:
Explore more advanced topics such as Object-Oriented Programming (OOP), Data Structures, and Algorithms.
Contribute to open-source projects on GitHub.
Keep practicing and building your projects!
