11 - Checked and Unchecked Exceptions in Java

============================================================
1. Introduction
============================================================
In Java, exceptions are divided into two main categories:
- Checked Exceptions
- Unchecked Exceptions

These categories help developers understand which errors must be handled and which can occur during normal program execution.

------------------------------------------------------------
2. Checked Exceptions
------------------------------------------------------------
Definition:
Checked exceptions are exceptions that are checked by the compiler at compile time.

Important points:
- The programmer must handle them using try-catch or declare them using throws.
- They usually occur due to external resources like files, databases, or network operations.

Examples:
- IOException
- SQLException
- FileNotFoundException

Why they are important:
- They force the programmer to handle possible problems.
- They improve reliability.

------------------------------------------------------------
3. Unchecked Exceptions
------------------------------------------------------------
Definition:
Unchecked exceptions are not checked by the compiler at compile time.

Important points:
- They are also called runtime exceptions.
- They usually occur due to programming mistakes.
- They do not need to be declared or handled explicitly.

Examples:
- ArithmeticException
- NullPointerException
- ArrayIndexOutOfBoundsException
- IllegalArgumentException

Why they are important:
- They help identify logical or coding errors.
- They can be prevented by writing better code.

------------------------------------------------------------
4. Difference Between Checked and Unchecked Exceptions
------------------------------------------------------------
Checked Exceptions:
- Checked at compile time
- Must be handled or declared
- Example: IOException

Unchecked Exceptions:
- Checked at runtime
- Not required to be handled
- Example: ArithmeticException

------------------------------------------------------------
5. Program 1: Checked Exception Example
============================================================
Headline:
Handling Checked Exception

Program:
import java.io.*;

public class CheckedExceptionExample {
    public static void main(String[] args) {
        try {
            FileReader file = new FileReader("demo.txt");
            System.out.println("File opened successfully.");
        } catch (IOException e) {
            System.out.println("Error: " + e.getMessage());
        }
    }
}

Explanation:
- FileReader may throw FileNotFoundException, which is a checked exception.
- The program handles it using try-catch.

Output:
If file exists:
File opened successfully.

If file does not exist:
Error: demo.txt (The system cannot find the file specified)

------------------------------------------------------------
6. Program 2: Unchecked Exception Example
============================================================
Headline:
Handling Unchecked Exception

Program:
public class UncheckedExceptionExample {
    public static void main(String[] args) {
        int a = 10;
        int b = 0;

        try {
            int result = a / b;
            System.out.println(result);
        } catch (ArithmeticException e) {
            System.out.println("Cannot divide by zero.");
        }
    }
}

Explanation:
- Division by zero causes ArithmeticException.
- It is an unchecked exception.
- The program handles it using try-catch.

Output:
Cannot divide by zero.

------------------------------------------------------------
7. Important Rules
------------------------------------------------------------
- Checked exceptions must be handled or declared.
- Unchecked exceptions are usually caused by logic errors.
- A good program should handle checked exceptions properly.
- Developers should avoid unchecked exceptions by writing correct code.

------------------------------------------------------------
8. Conclusion
============================================================
Checked and unchecked exceptions are important parts of Java exception handling.
Checked exceptions are forced to be handled, while unchecked exceptions are usually due to coding mistakes.
Understanding both helps developers write safer and more reliable Java programs.
