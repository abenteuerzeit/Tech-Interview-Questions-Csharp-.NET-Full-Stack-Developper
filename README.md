
# Question Index

## OOP / General

Click to view the [answers](https://github.com/abenteuerzeit/Tech-Interview-Questions-Csharp-.NET-Full-Stack-Developper/blob/master/OOP.md#oop)

1. What is OOP?

    - Inheritance
    - Polymorphism
    - Abstraction
    - Encapsulation

2. What is a class?
3. What is an object?
4. What is casting? What is the difference between up vs downcasting?
5. What is Encapsulation? Explain the concept with a realistic example!
6. What is Polymorphism? Explain the concept with a realistic example!
7. What is Inheritance? Explain the concept with a realistic example!
8. Define a constructor?
9. What is method overloading?
10. What are different types of arguments? (context: pass by value / pass by reference)
11. What is method overriding?
12. What is an interface?
13. What is exception handling?
14. Difference between overloading and overriding?
15. What is an abstraction?
16. What are access modifiers?
17. What is early and late binding?
18. Do we require parameters for constructors?
19. What is a copy constructor?
20. Whether a staticWhether static method can use non static members?
21. What are base class, subclass and superclass?
22. What is static and dynamic binding?
23. Which OOP concept is used as a reuse mechanism?
24. Which OOP concept exposes only necessary information to the calling functions?
25. What is data hiding?
26. What is variable shadowing?
27. What is the difference between hiding a static method and overriding an instance method?
    - Instance Methods
    - Static Methods
    - Differences
28. Define the following terms: Instantiation, Attribute, Method
29. Explain how object oriented languages implement abstract data types.
30. Explain how object oriented languages attempt to simplify memory management for Programmers.
31. Explain the “Single Responsibility” principle!
32. What is an object oriented program? Explain, show.
33. Draw an object oriented family (as entities, with relations) on the whiteboard.
34. What does it mean that an object is Immutable?
35. How do you make a class immutable? What do you need to watch out for?
36. How do you prevent developers from subclassing a class?
37. How do you prevent developers from overriding a method in a subclass?
38. How do you prevent developers from changing the value of a variable?

## Algorithms, Pseudo code

1. Fibonacci sequences. Write a method(or pseudo code), that generates the Fibonacci sequences.
2. Factorial
    a. Write a function that, given a number as input, returns the factorial of that number. The factorial of a number ‘n’ is the product of all positive integers less than or equal to ‘n’. So, the factorial of 6 would be 6*5*4*3*2*1 = 720. The factorial of 0 is 1.
    b. Write your solution with recursion.
3. Write a function, that print all the files in a given folder and sub-folders with using recursion.
4. What is “Stack overflow”? Write a code that ends up with stack overflow.
5. What is binary search tree (BST)? Write an implementation in Java.
6. What is linked list? How to find if a linked list has a loop?
7. How to find middle element of linked list in one pass?
8. In an integer array, there is 1 to 100 number, out of one is duplicate, how to find?
9. What is the difference between Stack and Queue data structure?
10. What is QuickSort? Describe the main logic of this sorting algorithm.

## Testing

1. What are unit test, integration test, system test, regression test, acceptance test? What is the major difference between these?
2. What is the difference between functional and non-functional testing? Give an example.
3. What is code coverage? Why is it used? How can you measure?
4. What does mocking mean? How would you do it 'manually' (i. e. without using any fancy framework)?
5. What is the difference between stub and mock?
6. What is a test case? What is an assertion? Give examples!
7. What is TDD? What are the benefits?
8. What is BDD? What are the benefits?
9. What are the unit testing best practices? (Eg. how many assertion should a test case contain?)

## Databases

1. How can you connect your application to a database server? What are the possible ways?
2. When do you use the DISTINCT keyword in SQL?
3. What are aggregate functions in SQL? Give 3 examples.
4. What do you know about database normalization?
5. What kind of JOIN types do you know in SQL? Could you give examples?
6. What are database transactions? When to use?
7. What is a dead-lock in databases? How to avoid?
8. What is a two-phase commit? Bring an example how to use?
9. What kind of database relations do you know? How to define them?
10. What is an ORM? What are the benefits, when to use?
11. What is the trigger? Bring an example of using?
12. Indexes at database.
13. The difference between WHERE and HAVING
14. What is SQL Injection?

## Networking, HTTP, Web technologies

1. What is the difference between HTML and XML?
2. What is a schema in XML? How to validate a schema?
3. What is XSLT?
4. When to use AJAX? Bring examples.
5. What kind of HTTP status codes do you know?
6. What is a REST API?
7. What is JSON? When to use?

## Software Methodologies

1. What kind of software-lifecycle models do you know?
2. What kind of software development methodologies do you know? What are the main features of these?
    - Waterfall Model
    - Agile Model
3. What is a UML diagram? What kind of diagram types do you know? UML has lots of diagram types:
4. What is a UML class diagram? What are the typical elements?
5. What kind of design patterns do you know? Bring at least 3 examples.
6. What do you know about the SOLID principles?

## Csharp

1. What is an assembly?
2. What is the difference between an EXE and a DLL?
3. What is strong-typing versus weak-typing? Which is preferred? Why?
4. Explain the purpose of IL and how does it relate to CLR?
5. What does “managed code” mean?
6. How does the generational garbage collector in the .NET CLR manage object lifetime? What is non-deterministic finalization?
7. What is the difference between .NET Core and .NET Standard? How do they relate to “classic” .NET?
8. What is a namespace?
9. Explain sealed class in C#?
10. What is explicit vs. implicit conversion? Give examples of both of them.
11. Is a struct stored on the heap or stack?
12. Can a struct have methods?
13. Can DateTimes be null?
14. List out the differences between Array and ArrayList in C#?
15. Why to use “using” in C#?
16. How can you make sure that objects using dedicated resources (database connection, files, hardware, OS handle, etc.) are released as early as possible?
17. Why to use keyword “const” in C#? Give an example.
18. What is the difference between “constant” and “readonly” variables in C#?
19. What is a property in C#?
20. Explain “static” keyword in C#?
21. How is the using() pattern useful? What is IDisposable? How does it support deterministic finalization?
22. How the exception handling is done in C#?
23. Can we execute multiple catch blocks in C#?
24. Why to use “finally” block in C#?
25. Why is “catch(Exception)” almost always a bad idea?
26. List out two different types of errors in C#?
27. Can we get an error while executing “finally” block in C#?
28. What is the difference between “out” and “ref” parameters in C#?
29. Can we use “this” inside a static method in C#?
30. Can we have only “try” block without “catch” block in C#?
31. Can we override private virtual method in C#?
32. What's the difference between IEquatable and just overriding Object.Equals()?
33. Explain the differences between public, protected, private and internal.
34. Explain access modifier – “protected internal” in C#!
35. What’s the difference between using `override` and `new` keywords when defining method in child class?
36. Explain String Builder class in C#!
37. How we can sort the array elements in descending order in C#?
38. Explain Generics in C#!
39. Can you use a value type as a generic type argument in C#? For example when implementing an interface like (IEquatable).
40. What are Nullable Types in C#?
41. Conceptually, what is the difference between early-binding and late-binding?
42. What is delegate, event, callback, multicast delegate?
43. What is enum in C#?
44. What is null-conditional operator?
45. What is null-coalescing operator?
46. What is the difference between ref & out parameters?
47. What is serialization?
48. Can “this” be used within a static method?
49. What is the difference between Finalize() and Dispose() methods?
50. How do you inherit a class from another class in C#?
51. Why can’t you specify the accessibility modifier for methods inside the interface?
52. What is the difference between “is” and “as” operators in C#?
53. What are indexers in C# .NET?
54. What is LINQ? Explain the idea of extension methods.
55. How to use of “yield” keyword? Mention at least one practical scenario where it can be used?
56. What’s the difference between camel and pascal casing?
57. What is reflection?
58. What are attributes in C#? Give some examples of usage of them.
59. By what mechanism does NUnit know what methods to test?
60. What is the GAC? What problem does it solve?

## Threads, Concurrency

1. When you need to use threads in an application?
2. What is a deamon thread?
3. What is the difference between synchronous and asynchronous execution?
4. What is the difference between concurrent and parallel execution of code?
5. What is the most important problem developers are problem is callback function.
6. In what kind of situations can deadlocks occur?
