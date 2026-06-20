16 - Exception Handling Interview Questions and Answers in Java

============================================================
1. What is an exception in Java?
============================================================
Answer:
An exception is an event that disrupts the normal flow of a program during execution.
It is used to represent errors or unexpected situations.

------------------------------------------------------------
2. What is the difference between error and exception?
============================================================
Answer:
An error represents a serious problem that usually cannot be recovered from easily, such as OutOfMemoryError.
An exception represents a problem that can often be handled by the program, such as IOException or ArithmeticException.

------------------------------------------------------------
3. What is the difference between checked and unchecked exceptions?
============================================================
Answer:
Checked exceptions are checked at compile time and must be handled or declared.
Unchecked exceptions are runtime exceptions and do not need to be declared explicitly.

------------------------------------------------------------
4. What is the hierarchy of exceptions in Java?
============================================================
Answer:
All exceptions inherit from Throwable.
Throwable has two main subclasses: Error and Exception.
Exception has subclasses like IOException and RuntimeException.

------------------------------------------------------------
5. What is the base class for all exceptions?
============================================================
Answer:
The base class for all exceptions is Throwable.

------------------------------------------------------------
6. What is the difference between RuntimeException and Exception?
============================================================
Answer:
RuntimeException is a subclass of Exception and represents unchecked exceptions.
Most other subclasses of Exception are checked exceptions.

------------------------------------------------------------
7. What is the purpose of the try-catch block?
============================================================
Answer:
The try block contains code that may throw an exception.
The catch block handles the exception if it occurs.

------------------------------------------------------------
8. Can we have multiple catch blocks for one try block?
============================================================
Answer:
Yes, we can have multiple catch blocks.
Each catch block handles a different type of exception.
The most specific exceptions should come first.

------------------------------------------------------------
9. What is the finally block used for?
============================================================
Answer:
The finally block is used to write cleanup code that must run whether an exception occurs or not.
It is commonly used for closing files and resources.

------------------------------------------------------------
10. Is finally block always executed?
============================================================
Answer:
Yes, finally is executed in most cases after try/catch, unless the JVM exits or the program is terminated forcefully.

------------------------------------------------------------
11. What is the difference between throw and throws?
============================================================
Answer:
throw is used to manually raise an exception inside a method.
throws is used in the method declaration to declare that a method may throw one or more exceptions.

------------------------------------------------------------
12. Can we use throw without throws?
============================================================
Answer:
Yes, we can use throw inside a method to manually throw an exception.
But if it is a checked exception, the method must also declare it using throws or handle it.

------------------------------------------------------------
13. What is exception propagation?
============================================================
Answer:
Exception propagation means passing an exception from one method to another until it is handled.
If it is not handled, the program stops.

------------------------------------------------------------
14. What happens if an exception is not caught?
============================================================
Answer:
If an exception is not handled, it propagates upward through the call stack.
If no handler exists, the JVM terminates the program and prints a stack trace.

------------------------------------------------------------
15. What is a custom exception?
============================================================
Answer:
A custom exception is a user-defined exception class created to represent special application-specific errors.

------------------------------------------------------------
16. How do you create a custom exception in Java?
============================================================
Answer:
You create a class that extends Exception or RuntimeException and provide a constructor that calls super(message).

------------------------------------------------------------
17. What is the difference between final, finally, and finalize?
============================================================
Answer:
final is a keyword used to restrict changes.
finally is a block used with try-catch for cleanup.
finalize is a method of Object that is called by the garbage collector, but it is not recommended for modern Java.

------------------------------------------------------------
18. What is try-with-resources?
============================================================
Answer:
try-with-resources is a feature that automatically closes resources after use.
It is useful for files, streams, database connections, and other resources.

------------------------------------------------------------
19. Why is try-with-resources preferred over finally for closing resources?
============================================================
Answer:
It reduces boilerplate code and ensures resources are closed automatically even if an exception occurs.

------------------------------------------------------------
20. Can we catch multiple exceptions in one catch block?
============================================================
Answer:
Yes, since Java 7, we can catch multiple exceptions in one catch block using the pipe symbol.
Example: catch (IOException | SQLException e)

------------------------------------------------------------
21. What are some common checked exceptions?
============================================================
Answer:
Examples include IOException, SQLException, FileNotFoundException, and ClassNotFoundException.

------------------------------------------------------------
22. What are some common unchecked exceptions?
============================================================
Answer:
Examples include ArithmeticException, NullPointerException, ArrayIndexOutOfBoundsException, and IllegalArgumentException.

------------------------------------------------------------
23. Why should we not use exceptions for normal flow control?
============================================================
Answer:
Exceptions are meant for exceptional situations, not for regular logic.
Using them for normal flow makes code slower and harder to read.

------------------------------------------------------------
24. What is the importance of meaningful exception messages?
============================================================
Answer:
Meaningful messages help developers understand what went wrong and make debugging easier.

------------------------------------------------------------
25. What is the difference between printStackTrace() and logging?
============================================================
Answer:
printStackTrace() prints the stack trace to the console.
Logging is more structured and is preferred in real applications.

------------------------------------------------------------
26. What is rethrowing an exception?
============================================================
Answer:
Rethrowing means catching an exception and then throwing it again so that the caller can handle it.

------------------------------------------------------------
27. Can we write a try block without catch?
============================================================
Answer:
Yes, a try block can be followed by finally, but not by only try without either catch or finally.

------------------------------------------------------------
28. What is the role of the stack trace?
============================================================
Answer:
A stack trace shows the sequence of method calls that led to the exception.
It helps in locating the source of the error.

------------------------------------------------------------
29. What is the difference between throws and try-catch?
============================================================
Answer:
throws declares that a method may throw an exception.
try-catch actually handles the exception.

------------------------------------------------------------
30. What are the best practices for exception handling?
============================================================
Answer:
Best practices include:
- Catch specific exceptions
- Avoid empty catch blocks
- Use finally or try-with-resources
- Do not swallow exceptions silently
- Use clear messages
- Handle exceptions at the correct level
- Do not use exceptions for program control flow

------------------------------------------------------------
31. Can we catch Throwable directly?
============================================================
Answer:
You can, but it is not recommended because it may catch serious errors that should not be handled normally.

------------------------------------------------------------
32. What happens if both try and finally throw exceptions?
============================================================
Answer:
If both throw exceptions, the exception from finally may override the one from try.
This is why finally should be used carefully.

------------------------------------------------------------
33. What is the difference between exception handling in Java and C++?
============================================================
Answer:
Java has checked and unchecked exceptions, while C++ uses a different exception model and does not have checked exceptions by default.

------------------------------------------------------------
34. Why are exceptions important in Java programming?
============================================================
Answer:
They help make programs more reliable, easier to debug, and safer to run in real-world situations.

------------------------------------------------------------
35. Example program showing try-catch-finally
============================================================
Program:
public class ExceptionInterviewExample {
    public static void main(String[] args) {
        try {
            int a = 10;
            int b = 0;
            int result = a / b;
            System.out.println(result);
        } catch (ArithmeticException e) {
            System.out.println("Handled exception: " + e.getMessage());
        } finally {
            System.out.println("Finally block executed.");
        }
    }
}

Output:
Handled exception: / by zero
Finally block executed.

------------------------------------------------------------
36. Conclusion
============================================================
Exception handling is one of the most important topics in Java.
A strong understanding of exceptions, error types, try-catch-finally, custom exceptions, and best practices is essential for writing professional and reliable Java programs.
