# Hello Inputs

![](hello_inputs.png)


# Standard Input (Scanner)

## Introduction to Standard Input (Scanner)
In Java, programs often need to interact with users by accepting input from them. This is where the Scanner class comes in handy. Imagine you're at a grocery store checkout, and the cashier asks for your membership card to give you discounts. In this scenario, you provide your card (input), and the cashier scans it to process the discounts (Scanner). Similarly, in Java, the Scanner class is used to "scan" or read inputs provided by the user, making it an essential tool for creating interactive programs.

### Why Use Scanner?
Using the Scanner class helps you:
- Read various types of input from the user, such as strings, numbers, and more.
- Make your programs interactive by processing user-provided data.
- Easily handle and validate input, enhancing the user experience.
- Avoid hardcoding values, making your programs more flexible and reusable.

### Basic Concepts of Scanner
The Scanner class in Java is part of the `java.util` package and is used to obtain input from various sources, such as keyboard input (standard input), files, and more. It can read different types of data, including strings, integers, and floating-point numbers.

### Creating a Scanner Object
To use the Scanner class, you first need to create a Scanner object. This object serves as a "listener" that waits for the user to input data.

Syntax:
```java
Scanner scanner = new Scanner(System.in);
```

Example:
```java
import java.util.Scanner;

public class UserInputExample {
    public static void main(String[] args) {
        // Create a Scanner object
        Scanner scanner = new Scanner(System.in);

        // Prompt the user for input
        System.out.println("Enter your name:");
        
        // Read input from the user
        String name = scanner.nextLine();

        // Output the user's input
        System.out.println("Hello, " + name + "!");
    }
}
```

### Reading Different Data Types
The Scanner class allows you to read different types of input, such as strings, integers, and floating-point numbers. Each data type has a corresponding method in the Scanner class.

#### Reading a String
You can use `nextLine()` to read a full line of text.

Syntax:
```java
String userInput = scanner.nextLine();
```

Example:
```java
import java.util.Scanner;

public class ReadStringExample {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("What is your favorite programming language?");
        String language = scanner.nextLine();

        System.out.println("You love " + language + "!");
    }
}
```

#### Reading an Integer
You can use `nextInt()` to read an integer value.

Syntax:
```java
int number = scanner.nextInt();
```

Example:
```java
import java.util.Scanner;

public class ReadIntExample {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Enter your age:");
        int age = scanner.nextInt();

        System.out.println("You are " + age + " years old.");
    }
}
```

#### Reading a Floating-Point Number
You can use `nextDouble()` to read a floating-point number.

Syntax:
```java
double value = scanner.nextDouble();
```

Example:
```java
import java.util.Scanner;

public class ReadDoubleExample {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Enter the price of the item:");
        double price = scanner.nextDouble();

        System.out.println("The item costs $" + price);
    }
}
```

### Important Notes on Scanner
- Always close the Scanner object using `scanner.close()` when it is no longer needed to free up resources.
- Be cautious when mixing `nextLine()` with other `nextX()` methods (like `nextInt()` or `nextDouble()`), as `nextLine()` might capture the newline character left by other methods. This can be resolved by adding an extra `nextLine()` after the integer or double input.
- Handle potential exceptions that can occur when the user enters unexpected input types.

### Practice Exercise: User Profile (15 minutes)
Create a simple program that asks the user for their name, age, and favorite hobby, then prints out a short "user profile" summary.

#### Task Description:
1. Prompt the user to enter their name and store it as a string.
2. Ask the user to input their age and store it as an integer.
3. Request the user's favorite hobby and store it as a string.
4. Print out a summary that includes the user's name, age, and hobby.



#### Bonus Challenges (if time permits):
1. Add a feature to validate the user's age to ensure they enter a positive integer.
2. Modify the program to ask the user for their favorite number and display the sum of their age and favorite number.

Remember to test your code thoroughly to ensure it handles all user inputs gracefully. Good luck!

# Hangman Game Exercise

## Objective

Create a simple Hangman game in Java. The player must guess the letters in a hidden word within a limited number of attempts.

## Instructions

### Setup

1. **Create an Array of Words**:  
   - Prepare an array of words that the game will choose from.
   
2. **Randomly Select a Target Word**:  
   - Randomly select one word from the array to be the target word.
   
3. **Represent the Target Word**:  
   - Use an array of characters (`char[]`) to represent the letters of the target word.
   
4. **Display the Current State**:  
   - Create another array of characters to display the current state of the word with blanks (e.g., `_ _ _ _`).

### User Input

1. **Reading the Player's Guess**:  
   - Use the `Scanner` class to read the player's guess.
   - The player should guess one letter at a time.

### Game Logic

1. **Handling a Correct Guess**:  
   - If the guessed letter is in the word, reveal its position(s) in the display array.
   
2. **Handling an Incorrect Guess**:  
   - If the guessed letter is not in the word, decrease the number of remaining attempts.
   
3. **Repeat the Process**:  
   - Continue until the player either guesses the word or runs out of attempts.

### String Methods and Loops

1. **Looping for Guesses**:  
   - Use loops to repeatedly prompt the player for guesses.
   
2. **String Handling**:  
   - Use string methods like `.charAt()` to handle the player's input and `.equals()` to check if the word is fully guessed.

### End of Game

1. **Winning or Losing**:  
   - Display a message when the player correctly guesses the word or when they lose, showing the correct word.


# File Reader and File Writer

## Introduction to File Reader and File Writer
In Java, handling files is a crucial aspect of many applications, especially when dealing with data persistence—saving data that can be accessed even after the program is closed. Imagine writing a note on a piece of paper and storing it in a file cabinet; you can retrieve it whenever you need it. Similarly, Java provides mechanisms to read from and write to files, which allows your programs to store and retrieve information.

### Why Use File Reader and File Writer?
Using File Reader and File Writer helps you:
- **Persist Data:** Store data that can be used across different sessions of the program.
- **Process Large Data:** Handle data that might be too large to store in memory by reading from or writing to files.
- **Automate Tasks:** Automate the process of reading from and writing to files, which is essential for many applications, such as logging, data analysis, and report generation.

### Basic Concepts of File Reader and File Writer
In Java, `FileReader` and `FileWriter` are classes used for reading from and writing to text files. `FileReader` reads character streams, while `FileWriter` writes character streams to a file. These classes are part of the `java.io` package.

- **FileReader:** Used for reading text from a file. It reads data character by character.
- **FileWriter:** Used for writing text to a file. It writes data character by character.

### Reading from a File using FileReader
The `FileReader` class allows you to read data from a file. It's important to handle potential exceptions, such as the file not being found.

Syntax:
```java
FileReader reader = new FileReader("filename.txt");
```

Example:
```java
import java.io.FileReader;
import java.io.IOException;

public class FileReaderExample {
    public static void main(String[] args) {
        try {
            // Step 1: Create a FileReader object to read from the file
            FileReader reader = new FileReader("example.txt");

            // Step 2: Read the data from the file
            int character;
            while ((character = reader.read()) != -1) {
                // Step 3: Print each character to the console
                System.out.print((char) character);
            }

            // Step 4: Close the FileReader
            reader.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

### Writing to a File using FileWriter
The `FileWriter` class is used to write data to a file. If the file does not exist, it will be created. If it does exist, the data will be overwritten unless you specify to append to the file.

Syntax:
```java
FileWriter writer = new FileWriter("filename.txt");
```

Example:
```java
import java.io.FileWriter;
import java.io.IOException;

public class FileWriterExample {
    public static void main(String[] args) {
        try {
            // Step 1: Create a FileWriter object to write to the file
            FileWriter writer = new FileWriter("output.txt");

            // Step 2: Write some text to the file
            writer.write("Hello, World!\n");
            writer.write("This is a text file.");

            // Step 3: Close the FileWriter
            writer.close();
            
            System.out.println("Data has been written to the file.");
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

### Appending to a File
You can also append data to an existing file using `FileWriter`. This means the new data will be added to the end of the file, rather than overwriting its contents.

Syntax:
```java
FileWriter writer = new FileWriter("filename.txt", true);
```

Example:
```java
import java.io.FileWriter;
import java.io.IOException;

public class FileWriterAppendExample {
    public static void main(String[] args) {
        try {
            // Step 1: Create a FileWriter object in append mode
            FileWriter writer = new FileWriter("output.txt", true);

            // Step 2: Append some text to the file
            writer.write("\nAppending new line to the file.");

            // Step 3: Close the FileWriter
            writer.close();
            
            System.out.println("Data has been appended to the file.");
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

### Important Notes on FileReader and FileWriter
- **File Path:** Always ensure that the correct file path is specified. If the file is not in the current directory, you need to provide the full path.
- **Error Handling:** Always handle exceptions like `FileNotFoundException` and `IOException` to ensure your program doesn't crash if the file is missing or inaccessible.
- **Resource Management:** It's a best practice to close your `FileReader` and `FileWriter` objects using the `close()` method or by using try-with-resources to ensure resources are freed.
- **Character Encoding:** `FileReader` and `FileWriter` use the default character encoding. If you need a specific encoding, consider using `InputStreamReader` and `OutputStreamWriter`.

### Practice Exercise: Simple Note Taker (15 minutes)
Create a program that allows the user to write notes to a file and then read the notes back from the file.

#### Task Description:
1. Prompt the user to enter a note and save it to a file named "notes.txt".
2. After saving the note, read the contents of "notes.txt" and display them on the console.
3. Ensure the notes are appended to the file, not overwritten.

#### Bonus Challenges (if time permits):
1. **Clear Notes:** Add an option for the user to clear all notes in the file.
2. **Timestamp Notes:** Modify the program to add a timestamp to each note before saving it to the file.

Remember to test your program thoroughly to handle various inputs and scenarios gracefully. Good luck!
Here’s a detailed exercise prompt for your bootcamp students:

---


# Java Methods

## Introduction to Java Methods
In Java, methods are like recipes that tell the program how to perform a specific task. Think of methods as the instructions for making a sandwich—each step (method) tells you what to do next, whether it's adding the bread, spreading the peanut butter, or slicing the sandwich. Similarly, Java methods allow you to organize your code into sections that perform specific tasks.

### Why Use Java Methods?
Using methods in Java helps you:
- **Improve Code Organization:** Break down complex tasks into smaller, more manageable steps.
- **Promote Code Reusability:** Write a method once and use it multiple times within your program.
- **Enhance Readability:** Make your code easier to read and understand by grouping related operations together.
- **Simplify Maintenance:** Updating a method in one place updates all parts of your program that use it, making maintenance easier.

### Basic Concepts of Java Methods
A method in Java is a block of code that performs a specific task. You can define a method once and call (or invoke) it whenever you need to perform that task. Methods can take inputs, called parameters, perform actions, and return a result. If a method doesn't need to return anything, it's declared with the `void` keyword.

### Defining a Method
To define a method in Java, you specify its return type, name, and parameters (if any). The method body contains the code that defines what the method does.

Syntax:
```java
returnType methodName(parameterType parameterName) {
    // Method body
    // Code to be executed
    return value; // Only if the method is not void
}
```

Example:
```java
// Define a method that returns a greeting message
String sayHello(String name) {
    return "Hello, " + name + "!";
}

public static void main(String[] args) {
    // Call the sayHello method and print the result
    String greeting = sayHello("Alice");
    System.out.println(greeting);
}
```

### Method Parameters and Return Values
Methods can accept parameters, which are values you pass to the method when calling it. The method can then use these parameters to perform operations. Methods can also return a value, which is the result of the method's operations.

#### Method with Parameters
A method can take multiple parameters, which are specified in the method definition.

Syntax:
```java
returnType methodName(parameterType1 parameterName1, parameterType2 parameterName2) {
    // Method body
    return value; // Only if the method is not void
}
```

Example:
```java
// Method that adds two numbers
int add(int a, int b) {
    return a + b;
}

public static void main(String[] args) {
    // Call the add method with parameters
    int sum = add(5, 3);
    System.out.println("Sum: " + sum);
}
```

#### Method with Return Values
A method can return a value, which must match the method's declared return type.

Syntax:
```java
returnType methodName() {
    // Method body
    return value; // The value must match the returnType
}
```

Example:
```java
// Method that calculates the square of a number
int square(int number) {
    return number * number;
}

public static void main(String[] args) {
    // Call the square method and store the result
    int result = square(4);
    System.out.println("Square: " + result);
}
```

### Void Methods
Void methods do not return any value. They simply perform an action, such as printing to the console.

Syntax:
```java
void methodName() {
    // Method body
    // No return statement is needed
}
```

Example:
```java
// Void method that prints a message
void printMessage(String message) {
    System.out.println(message);
}

public static void main(String[] args) {
    // Call the printMessage method
    printMessage("Hello, World!");
}
```

### Method Overloading
Method overloading is a feature in Java where you can have multiple methods with the same name but different parameter lists. The compiler determines which method to call based on the number and type of parameters passed.

Syntax:
```java
// Method with one parameter
int multiply(int a) {
    return a * a;
}

// Overloaded method with two parameters
int multiply(int a, int b) {
    return a * b;
}

public static void main(String[] args) {
    // Call the multiply method with different parameter lists
    System.out.println("Multiplying one number: " + multiply(5));
    System.out.println("Multiplying two numbers: " + multiply(5, 4));
}
```

### Important Notes on Java Methods
- **Method Names:** Choose method names that clearly describe what the method does.
- **Parameters:** Ensure parameters are meaningful and provide the necessary information for the method to perform its task.
- **Method Reusability:** Aim to make methods reusable by limiting their scope to a single, well-defined task.
- **Method Length:** Keep methods concise. If a method is too long, consider breaking it into smaller methods.

### Practice Exercise: Simple Calculator (15 minutes)
Create a simple calculator program with methods for addition, subtraction, multiplication, and division.

#### Task Description:
1. Define four methods: `add`, `subtract`, `multiply`, and `divide`.
2. Each method should accept two integer parameters and return the result.
3. In the `main` method, demonstrate the use of each calculator method by calling them with sample inputs.

#### Bonus Challenges (if time permits):
1. **Input Validation:** Modify the methods to validate the inputs (e.g., check for non-negative numbers).
2. **Floating-Point Operations:** Overload the methods to handle floating-point operations by accepting `double` parameters.

Remember to test your methods thoroughly to ensure they handle all expected and unexpected inputs gracefully. Good luck!

### Weekend optional exercise: File Encoder and Decoder Console Program

**Objective:**  
Your task is to create a console-based program that encodes and decodes text files. This program will prompt the user to choose whether they want to encode or decode a file and then perform the selected operation. You are free to design the encoding and decoding algorithms as you see fit, as long as the encoding process is reversible by your decoding process.


### Requirements:

1. **Main Menu:**
   - The program should start by displaying a menu with at least the following options:
     1. Encode a File
     2. Decode a File
     3. Exit

2. **File Selection:**
   - The program should prompt the user to enter the path of the text file they wish to encode or decode. Optionally, you can implement a file selection prompt to make it easier for the user to choose the file.

3. **Encoding and Decoding:**
   - You have the freedom to choose how you want to encode and decode the text. Some possible ideas include:
     - **Substitution Cipher:** Replace each character with another character.
     - **Reversal Cipher:** Reverse the entire text.
     - **Shift Cipher (Caesar Cipher):** Shift each character by a fixed number of positions in the ASCII table.
     - **Custom Algorithm:** Feel free to create your own encoding method.
   - The encoded file should be saved with a new file name to avoid overwriting the original file. For example, if the original file is `message.txt`, the encoded file could be `message_encoded.txt`.

4. **File Writing:**
   - After encoding or decoding, the program should save the output to a new text file. Ensure that the original file remains unchanged.


5. **Exiting the Program:**
   - If the user selects the "Exit" option from the main menu, the program should terminate gracefully.

### Suggested Workflow:

1. **Setup the Project:**
   - Create a new Java project and add a class with a `main` method.
   - Import the necessary classes: `Scanner`, `File`, and `FileWriter`.

2. **Implement the Main Menu:**
   - Use a loop to display the main menu and process the user's selection.
   - Depending on the user's choice, call the appropriate method to encode or decode the file.

3. **File Handling:**
   - Use `Scanner` to read the contents of the selected file.
   - Use `FileWriter` to write the encoded or decoded contents to a new file.

4. **Encoding/Decoding Algorithms:**
   - Implement your chosen encoding and decoding algorithms in separate methods.

5. **Testing:**
   - Thoroughly test your program with different files and scenarios to ensure it works as expected.

### Bonus Challenges (Optional):
- Add a feature that allows the user to specify a custom key for the encoding/decoding process.
- Implement a basic file selection prompt for the file. 

### Possible Example:

```
Welcome to the File Encoder/Decoder!
------------------------------------
1. Encode a File
2. Decode a File
3. Exit
------------------------------------
Please select an option: 1

Enter the path of the file to encode: example.txt
Encoding the file...

File encoded successfully! The encoded file is saved as example_encoded.txt
```


# Java Classes

## Introduction to Java Classes
Java classes are the foundation of object-oriented programming in Java. They serve as blueprints for creating objects, which are instances of a class. Classes encapsulate data for the object and methods to manipulate that data, providing a powerful way to structure and organize code.

## Why Use Java Classes?
Using Java classes helps you:
- Organize code into logical, reusable units
- Implement encapsulation, hiding internal details and exposing only what's necessary
- Create modular and maintainable code
- Model real-world objects and concepts in your programs
- Implement inheritance and polymorphism for more flexible and extensible code

## Basic Concepts of Java Classes
A Java class typically consists of:
- Fields (also called attributes or properties)
- Methods (functions that operate on the data)
- Constructors (special methods for initializing objects)
- Access modifiers (to control visibility and accessibility)

## Access Modifiers
Access modifiers in Java control the visibility and accessibility of classes, methods, and variables. The four main access modifiers are:

1. **public**: Accessible from any other class.
2. **protected**: Accessible within the same package and by subclasses.
3. **default** (no modifier): Accessible only within the same package.
4. **private**: Accessible only within the same class.

Example:
```java
public class MyClass {
    public int publicVar;
    protected int protectedVar;
    int defaultVar;
    private int privateVar;

    public void publicMethod() { /* ... */ }
    protected void protectedMethod() { /* ... */ }
    void defaultMethod() { /* ... */ }
    private void privateMethod() { /* ... */ }
}
```

## Final Keyword
The `final` keyword in Java is used to create constants and prevent inheritance, method overriding, and variable reassignment.

1. **Final Variables**: Cannot be reassigned after initialization.
2. **Final Methods**: Cannot be overridden by subclasses.
3. **Final Classes**: Cannot be inherited.

Example:
```java
public final class Constants {
    public static final double PI = 3.14159;
    
    public final void printMessage() {
        System.out.println("This method cannot be overridden.");
    }
}
```

## Static Keyword
The `static` keyword is used to create class-level members (variables and methods) that belong to the class rather than instances of the class.

1. **Static Variables**: Shared across all instances of a class.
2. **Static Methods**: Can be called without creating an instance of the class.

Example:
```java
public class Counter {
    private static int count = 0;
    
    public static void incrementCount() {
        count++;
    }
    
    public static int getCount() {
        return count;
    }
}
```

## Classes and Objects
A class is a blueprint for creating objects. Objects are instances of a class.

Example:
```java
public class Car {
    private String model;
    private int year;
    
    public Car(String model, int year) {
        this.model = model;
        this.year = year;
    }
    
    public void displayInfo() {
        System.out.println("Model: " + model + ", Year: " + year);
    }
}

// Creating an object
Car myCar = new Car("Toyota Camry", 2022);
myCar.displayInfo();
```

## Inheritance
Inheritance allows a class to inherit properties and methods from another class. The `extends` keyword is used to create a subclass.

Example:
```java
public class Vehicle {
    protected String brand;
    
    public void honk() {
        System.out.println("Honk honk!");
    }
}

public class Car extends Vehicle {
    private int numberOfDoors;
    
    public Car(String brand, int numberOfDoors) {
        this.brand = brand;
        this.numberOfDoors = numberOfDoors;
    }
}
```

## Constructors
Constructors are special methods used to initialize objects. They have the same name as the class and no return type.

Example:
```java
public class Person {
    private String name;
    private int age;
    
    // Default constructor
    public Person() {
        name = "Unknown";
        age = 0;
    }
    
    // Parameterized constructor
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
}
```

## Polymorphism
Polymorphism allows objects of different classes to be treated as objects of a common superclass. It can be achieved through method overriding and method overloading.

1. **Method Overriding**: Subclass provides a specific implementation for a method defined in its superclass.
2. **Method Overloading**: Multiple methods in the same class with the same name but different parameters.

Example:
```java
public class Animal {
    public void makeSound() {
        System.out.println("The animal makes a sound");
    }
}

public class Dog extends Animal {
    @Override
    public void makeSound() {
        System.out.println("The dog barks");
    }
    
    // Method overloading
    public void makeSound(int times) {
        for (int i = 0; i < times; i++) {
            System.out.println("Woof!");
        }
    }
}

// Polymorphism in action
Animal myAnimal = new Dog();
myAnimal.makeSound(); // Outputs: The dog barks
```

## Important Notes on Java Classes
- Always use meaningful names for classes, following the CamelCase convention (e.g., `CarFactory`, not `carfactory`).
- Keep classes focused on a single responsibility to improve maintainability.
- Use access modifiers judiciously to implement encapsulation.
- Consider using interfaces and abstract classes for more flexible designs.
- Be cautious with inheritance; favor composition over inheritance when appropriate.
- Always provide appropriate constructors for your classes.


## Practice Exercise: Library Management System (20 minutes)
Create a simple library management system using Java classes.

### Task Description:
1. Create a `Book` class with properties like title, author, and ISBN.
2. Create a `Library` class that can add books, remove books, and display all books.
3. Use appropriate access modifiers, constructors, and methods.
4. In the `main` method, demonstrate the usage of your classes by adding books to the library, removing a book, and displaying the library contents.

### Bonus Challenges (if time permits):
1. Implement a `searchBooks` method in the `Library` class that can search for books by title or author.
2. Add a `borrowBook` method that marks a book as borrowed and prevents it from being borrowed again until it's returned.

Remember to apply the concepts of encapsulation, constructors, and method design we've discussed. Good luck!
