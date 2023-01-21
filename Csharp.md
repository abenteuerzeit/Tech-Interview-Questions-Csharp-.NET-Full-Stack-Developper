
# C\#

## What is an assembly?

An assembly is a collection of one or more files (such as .dll or .exe files) that are used to build and run an application. Assemblies contain the Common Intermediate Language (CIL) code for the application, along with metadata that describes the types, members, and references within the assembly.

Assemblies are the building blocks of .NET Framework applications. They act as a boundary for the application's code, resources, and configuration information. They are the unit of deployment, versioning, and security for .NET Framework applications.

Each assembly contains a manifest, which is a metadata file that describes the assembly's contents and dependencies. The manifest includes information such as the assembly's name, version number, culture, and list of all the files that make up the assembly.

Assemblies are also self-describing, meaning they contain all the information needed to run the application. This allows them to be versioned, deployed and executed without the need of installing any external dependencies.

In summary, an assembly is a logical unit of code that is deployed, versioned, and executed as a single entity. It contains the code and resources required to run an application and also contains metadata that describes the assembly's contents and dependencies.

## What is the difference between an EXE and a DLL?

XE (executable) and DLL (dynamic-link library) are two different types of files in Windows that are used for different purposes.

An EXE file is a standalone executable file that can be run by double-clicking on it. An EXE file typically contains a Main() method, which is the entry point of the application, and it contains all the resources and code needed to run the application. When an EXE file is run, it creates a new process, which is a separate instance of the operating system that runs the code in the EXE file.

A DLL file, on the other hand, is a library of code and resources that can be shared by multiple applications. A DLL file contains code and data that can be used by multiple applications, but it doesn't have a Main() method or the ability to run on its own. Instead, it exports functions and data that can be called by other applications. When a DLL is loaded by an application, it becomes part of the application's process, sharing the same memory space and resources.

In summary, the main difference between an EXE and a DLL is that an EXE is a standalone executable file that runs as a separate process, while a DLL is a library of code and resources that can be shared by multiple applications, and it runs within the process of the application that calls it.

## What is strong-typing versus weak-typing? Which is preferred? Why?

Strong-typing and weak-typing are two different ways of handling data types in programming languages.

Strong-typing is a type system that enforces strict type checking at compile-time or runtime. In a strongly-typed language, variables must be declared with a specific data type and cannot be implicitly converted to another data type without explicit casting. This means that the type of a variable is known at compile time and the compiler can check for type errors before the program runs. This can help to catch type-related errors early and prevent unexpected behavior in the program. Languages such as C# and Java are examples of strongly-typed languages.

Weak-typing, also known as dynamic-typing, is a type system that does not enforce strict type checking at compile-time or runtime. In a weakly-typed language, variables can take on any type of value and can be implicitly converted to another data type. This means that the type of a variable is only known at runtime and the program can be more flexible in how it handles data. However, this also means that type errors may only be discovered at runtime, which can make it more difficult to debug the program. Languages such as JavaScript, Python and PHP are examples of weakly-typed languages.

In general, strong-typing is preferred in many cases as it can help to catch type-related errors early and prevent unexpected behavior in the program. However, weak-typing can also be useful when the structure of the data or the types of operations being performed are not known at compile-time, and it allows for more flexibility in handling data.

## Explain the purpose of IL and how does it relate to CLR?

IL (Intermediate Language) is a low-level programming language used by the .NET Framework. It is also known as Microsoft Intermediate Language (MSIL) or Common Intermediate Language (CIL). The purpose of IL is to provide a common, platform-independent language that can be used to write code that runs on any .NET-compatible platform.

When a .NET application is compiled, the source code is translated into IL code. This IL code can be thought of as a sort of "intermediate" code that is not specific to any particular platform, but can be run on any platform that has a .NET runtime environment, such as the Common Language Runtime (CLR). The CLR is responsible for executing the IL code and providing the necessary services such as memory management, exception handling, and security.

When an application is executed, the CLR loads the IL code into memory and converts it into machine code that can be executed by the host computer's processor. This process is known as Just-In-Time (JIT) compilation. The JIT compiler converts the IL code into native machine code, which is specific to the platform the application is running on. The JIT compiler also performs various other tasks such as memory management, type checking and security checks.

In summary, IL is a low-level programming language that provides a common, platform-independent language that can be used to write code that runs on any .NET-compatible platform. The CLR is responsible for executing the IL code and providing the necessary services such as memory management, exception handling, and security. The JIT compiler converts the IL code into native machine code and performs various other tasks such as memory management, type checking and security checks.

## What does “managed code” mean?

"Managed code" refers to code that is executed by the Common Language Runtime (CLR) in the .NET Framework. The CLR is a virtual machine that provides a runtime environment for executing code written in any .NET-compatible language, such as C# or Visual Basic. The CLR is responsible for managing the execution of the code, providing services such as memory management, exception handling, and security.

Managed code is written in a language that is compatible with the CLR, and it is compiled into Intermediate Language (IL) code. The IL code is a low-level, platform-independent language that is not specific to any particular platform, but can be run on any platform that has a .NET runtime environment. When an application is executed, the CLR loads the IL code into memory and converts it into machine code that can be executed by the host computer's processor. This process is known as Just-In-Time (JIT) compilation.

Managed code is different from "unmanaged code" which refers to code that is executed directly by the operating system and does not use the services provided by the CLR, such as C++ code. Unmanaged code does not have the benefits provided by CLR like garbage collection, automatic memory management, exception handling, and security, and developers have to take care of these by themselves.

In summary, "managed code" refers to code that is executed by the CLR in the .NET Framework. Managed code is written in a language that is compatible with the CLR, and it is compiled into IL code. The CLR is responsible for managing the execution of the code, providing services such as memory management, exception handling, and security.

## How does the generational garbage collector in the .NET CLR manage object lifetime? What is non-deterministic finalization?

The .NET CLR's garbage collector manages object lifetime by using a technique called generational garbage collection. This technique divides the managed heap, where objects are stored in memory, into three generations:

Generation 0: This is the youngest generation and contains newly created objects. When the garbage collector runs, it checks for objects in this generation that are no longer in use and frees up the memory they were using.

Generation 1: This generation contains objects that have survived one garbage collection cycle in Generation 0. The garbage collector checks this generation less frequently than Generation 0.

Generation 2: This generation contains objects that have survived multiple garbage collection cycles. The garbage collector checks this generation infrequently.

The garbage collector uses this technique because it has been observed that most objects are short-lived, so it's more efficient to focus on the youngest generation where most of the unused objects will be found.

Non-deterministic finalization is a feature in the .NET CLR that allows objects to have a finalizer method, which is a method that is executed when the object is about to be garbage collected. Finalizer methods are typically used to release resources that are not managed by the garbage collector, such as file handles or database connections. The finalizer method is called on a separate thread, and the order in which finalizer methods are executed is not deterministic. This means that the CLR does not guarantee the order in which finalizer methods will be called, and the programmer should not rely on any specific order.

In summary, the .NET CLR's garbage collector manages object lifetime by using a technique called generational garbage collection, where the managed heap is divided into three generations and checks for objects that are no longer in use more frequently in the youngest generation. Non-deterministic finalization is a feature that allows objects to have a finalizer method which is executed when the object is about to be garbage collected, but the order in which finalizer methods are executed is not guaranteed.

## What is the difference between .NET Core and .NET Standard? How do they relate to “classic” .NET?

.NET Core and .NET Standard are both implementations of the .NET Framework, but they have different focuses and use cases.

.NET Core is an open-source, cross-platform implementation of the .NET Framework. It is designed to be lightweight and modular, making it suitable for building cloud-based and containerized applications, as well as for running on devices with limited resources. .NET Core is also optimized for building microservices and web applications.

.NET Standard is a set of APIs that are common across different .NET implementations, such as .NET Core, Xamarin, and the Universal Windows Platform (UWP). It provides a consistent set of APIs that can be used across different platforms, allowing developers to write code that can run on any platform that supports the .NET Standard. This means that libraries written against .NET Standard can run on any .NET implementation that supports the same version of the standard.

On the other hand, "classic" .NET refers to the original .NET Framework that was first released by Microsoft in 2002. It is primarily designed to run on Windows and is typically used for building desktop and enterprise applications. It is also not cross-platform and does not support containerization.

In summary, .NET Core is an open-source, cross-platform implementation of the .NET Framework that is designed for building cloud-based and containerized applications. .NET Standard is a set of APIs that are common across different .NET implementations, allowing code to be portable across different platforms. "Classic" .NET refers to the original .NET Framework that was first released by Microsoft and designed to run on Windows and primarily used for building desktop and enterprise applications.

## What is a namespace?

A namespace is a container in C# and other programming languages that holds a set of identifiers (such as class, struct, interface, enum, and delegate names) that can be used to organize and group related elements of code. Namespaces provide a way to uniquely identify a class or other code element, and to avoid naming conflicts with elements from other libraries or code bases.

For example, imagine that you are developing a program that includes a class called "Person". If another developer is also developing a program that includes a class called "Person", there would be a naming conflict if both classes are included in the same program. However, if the classes are placed in different namespaces, the naming conflict can be avoided.

A namespace can also be nested within another namespace. For example, you can have a namespace called "Company" and inside it you can have another namespace called "HumanResources" where you can put classes related to HR such as Employee, Salary, etc.

Namespaces can be used by adding the namespace keyword followed by the namespace name, and placing the classes and other code elements within the curly braces of the namespace block.

In summary, a namespace is a container that holds a set of identifiers that can be used to organize and group related elements of code, and to avoid naming conflicts. Namespaces provide a way to uniquely identify a class or other code element and can be nested to create a more organized structure.

## Explain sealed class in C\#

n C#, a sealed class is a class that cannot be inherited by any other class. This means that once a class is declared as sealed, it cannot be used as a base class for any other class.

A sealed class is typically used when a class has been designed to be used only as a stand-alone class, and it is not intended to be used as a base class for other classes. For example, an "Immutable" class is a good candidate to be sealed, as it is not meant to be inherited by other classes, and it should maintain its state without being modified.

A sealed class is declared by using the "sealed" keyword before the class keyword.

    sealed class MySealedClass
    {
        // class members
    }

Additionally, a sealed class can also be used to prevent a method from being overridden in a derived class. To prevent a method from being overridden in a derived class, you can use the "sealed" keyword before the method declaration.

    class MyBaseClass
    {
        protected sealed void MySealedMethod()
        {
            // method body
        }
    }

    class MyDerivedClass : MyBaseClass
    {
        // Error: 'MyDerivedClass.MySealedMethod()': cannot override inherited member 'MyBaseClass.MySealedMethod()' because it is sealed
        protected override void MySealedMethod()
        {
            // method body
        }
    }

In summary, a sealed class in C# is a class that cannot be inherited by any other class. It is typically used when a class has been designed to be used only as a stand-alone class and is not intended to be used as a base class for other classes. Additionally, a sealed class can also be used to prevent a method from being overridden in a derived class.

## What is explicit vs. implicit conversion? Give examples of both of them

In C#, there are two types of data type conversions: explicit and implicit conversions.

An explicit conversion is a conversion that requires an explicit cast operator to be performed. For example, when you want to convert an integer to a float, you need to use a cast operator to explicitly tell the compiler to perform the conversion:

        int i = 10;
        float f = (float)i;

Explicit conversions can also result in data loss, such as when you convert a double to an int, the decimal part is truncated:

    double d = 10.5;
    int i = (int)d; // i is 10

An implicit conversion is a conversion that is performed automatically by the compiler without the need for a cast operator. Implicit conversions are performed when the destination data type can hold all the values of the source data type without losing any information. For example:

    int i = 10;
    long l = i; // implicit conversion from int to long

or

    short s = 10;
    int i = s; // implicit conversion from short to int

In summary, an explicit conversion is a conversion that requires an explicit cast operator to be performed, and it can result in data loss. An implicit conversion is a conversion that is performed automatically by the compiler without the need for a cast operator, and it cannot result in data loss.

## Is a struct stored on the heap or stack?

In C#, a struct is stored on the stack.

In C#, a struct is a value type, which means that it is stored on the stack, unlike a class which is a reference type and is stored on the heap.

When a struct variable is declared, memory is allocated on the stack for the struct and its member variables. The stack is a memory area that stores temporary data, such as method call frames and local variables. The stack is a Last In First Out (LIFO) data structure, meaning that the last data to be pushed onto the stack is the first one to be popped off.

Because structs are value types and stored on the stack, they are generally smaller in memory, and they are faster to allocate and deallocate than classes. However, they are also less flexible than classes because they cannot be inherited, and they cannot be a null value.

In summary, a struct in C# is stored on the stack, because it is a value type, unlike a class which is a reference type and is stored on the heap

## Can a struct have methods?

es, a struct in C# can have methods.

In C#, a struct is a value type that can have fields, properties, methods, events, and constructors. Structs can have any of the same members as classes, including methods. A struct can have both instance methods (with a specific instance of the struct) and static methods.

For example, the following struct has a method called `Print()`:

    struct MyStruct
    {
        public int x;
        public int y;

        public void Print()
        {
            Console.WriteLine("x = {0}, y = {1}", x, y);
        }
    }

It is worth noting that structs are designed for small, lightweight data structures, such as a point in a 2D space, or a color. They should be used only when the data they hold is small and it is expected to be short lived. Additionally, it is recommended to avoid creating methods that change the state of a struct instance as it may lead to unexpected behavior since structs are passed by value.

In summary, a struct in C# can have methods as well as other members like fields, properties, events and constructors. However, it's important to keep in mind that structs are designed for small and lightweight data structures and it is recommended to avoid creating methods that change the state of a struct instance.

## Can DateTimes be null?

No, DateTime values cannot be null in C#.

In C#, the DateTime struct represents a specific point in time, and it cannot have a null value. Instead, it has a default value of DateTime.MinValue, which represents the smallest possible date and time that can be represented in a DateTime value (January 1, 0001, 12:00:00 AM). If you need to represent an undefined or null date and time value, you can use a nullable struct: DateTime? which is a struct that can be assigned a null value.

For example, the following code assigns a null value to a nullable DateTime variable:

    DateTime? dt = null;

You can also use the HasValue property to check if the nullable struct has a value or not:

    if (nullableDate.HasValue) 
    {
        // use the Value property to access the non-nullable value
        DateTime date = nullableDate.Value;
        Console.WriteLine(date);
    } 
    else 
    {
        Console.WriteLine("nullableDate is null");
    }

In summary, the DateTime struct in C# cannot have a null value. Instead, you can use a nullable struct DateTime? which can be assigned a null value, and you can use the HasValue property to check if the nullable struct has a value or not.

## List out the differences between Array and ArrayList in C#?

1. Type Safety: An array is a type-safe data structure, which means that it can store only elements of a specific data type. On the other hand, an ArrayList is a non-type-safe data structure, which means that it can store elements of any data type.
2. Size: An array has a fixed size, which means that its size cannot be changed after it is created. An ArrayList, on the other hand, has a dynamic size, which means that its size can be increased or decreased as needed.
3. Performance: An array is generally faster than an ArrayList because it is type-safe and has a fixed size. An ArrayList, on the other hand, is slower than an array because it has to perform additional operations to manage its dynamic size.
4. Syntax: An array is declared with a specific data type and a fixed size, for example: `int[] myArray = new int[5];`. An ArrayList is declared without specifying a specific data type and size, for example: `ArrayList myArrayList = new ArrayList()`;
5. Indexing: An array uses zero-based indexing, which means that the first element of the array has an index of 0, while ArrayList uses one-based indexing, which means that the first element of the ArrayList has an index of 1.
6. Conversion: An array can be converted to an ArrayList using the ArrayList constructor and vice versa using the `ToArray()` method of the ArrayList class.

In summary, arrays are type-safe, have a fixed size, generally faster, use zero-based indexing and can be converted to an ArrayList. On the other hand, ArrayLists are non-type-safe, have a dynamic size, slower, use one-based indexing and can be converted to arrays.

## Why would you use “using” in C#?

The using statement in C# is used to ensure that a resource, such as a file, database connection, or network connection, is properly disposed of after it is no longer needed. The using statement is typically used in conjunction with classes that implement the IDisposable interface.

When a resource is created inside a using block, the runtime automatically calls the Dispose method on the resource when the block is exited, even if the block is exited due to an exception being thrown.

For example, when using a SqlConnection object to connect to a database, it is important to close the connection after the data has been retrieved or the changes have been made. The using statement can be used to ensure that the connection is closed properly, even if an exception is thrown, like this:

    using (SqlConnection connection = new SqlConnection(connectionString))
    {
        connection.Open();
        // Perform data access operations
    }

In this example, the connection.Open() method is called inside the using block, and the connection.Close() method is called automatically when the block is exited, even if an exception is thrown. This ensures that the connection is closed properly and any resources associated with it are freed.

In summary, the using statement is used in C# to ensure that resources that implement the IDisposable interface are properly disposed of after they are no longer needed. It is used to make sure that the resources are closed and freed even if an exception is thrown, avoiding resource leaks and making the code more robust.

## How can you make sure that objects using dedicated resources (database connection, files, hardware, OS handle, etc.) are released as early as possible?

There are several ways to make sure that objects using dedicated resources are released as early as possible:

The using statement: As mentioned earlier, the using statement can be used to ensure that resources that implement the IDisposable interface are properly disposed of after they are no longer needed. This ensures that the resources are closed and freed even if an exception is thrown.

The try-finally block: The try-finally block can be used to make sure that the resources are disposed of, even if an exception is thrown. The resource should be instantiated in the try block, and the finally block should be used to dispose of the resource.

    SqlConnection connection = null;
    try
    {
        connection = new SqlConnection(connectionString);
        connection.Open();
        // Perform data access operations
    }
    finally
    {
        if (connection != null)
        {
            connection.Close();
        }
    }

The Dispose pattern: This is a design pattern that is used to ensure that resources are properly disposed of. Classes that use resources should implement the IDisposable interface and define a Dispose method that releases the resources. The using statement and try-finally block both use this pattern internally.

    class MyClass : IDisposable
    {
        private SqlConnection connection;

        public MyClass()
        {
            connection = new SqlConnection(connectionString);
            connection.Open();
        }

        public void Dispose()
        {
            connection.Close();
        }
    }

Using the C# 8.0 using declaration, this is a new feature that allows you to define a variable inside the using statement and dispose of it automatically when the variable goes out of scope.

    using var connection = new SqlConnection(connectionString);
    connection.Open();

    // Perform data access operations

By using the above methods, you can ensure that objects using dedicated resources are released as early as possible. This helps in releasing the resources in a timely manner, avoiding resource leaks and making the code more robust.

## Why is the keyword “const” used in C#? Give an example

The keyword "const" in C# is used to declare a constant value. A constant is a value that cannot be modified after it is declared. Once a constant is assigned a value, it cannot be reassigned to a different value. Constants are usually used for values that are known at compile time and will not change during the execution of the program.

An example of using the keyword "const" is declaring a constant for the value of pi:

    const double PI = 3.14159265358979323846;

In this example, the constant PI is declared and assigned the value of pi. The value of PI cannot be changed after it is declared. Since PI is a mathematical constant, it will not change during the program execution.

A variable declared as const also has some specific characteristics, such as:

- It must be initialized at the time of declaration.
- It can be used in any scope.
- It can be used only for simple data types such as integers, floating-point values, and strings.
- It cannot be used for complex data types like classes or structs.

It is important to note that constants are resolved at compile-time, whereas variables are resolved at runtime. As a result, using constants can improve the performance of your code because the value is known at compile-time, and the compiler can optimize the code accordingly.

## What is the difference between “constant” and “readonly” variables in C#?

In C#, the difference between "constant" and "readonly" variables is the way they are initialized and when they are evaluated.

Constant variables are declared using the const keyword and they must be assigned a value at the time of declaration. These values are evaluated at compile-time and cannot be changed throughout the lifetime of the program. They are usually used for values that are known at compile-time and will not change during the execution of the program.

Readonly variables are declared using the readonly keyword and they can be assigned a value at the time of declaration or in the constructor. These values are evaluated at runtime and can be changed throughout the lifetime of the program. They are usually used for values that are not known at compile-time and can change during the execution of the program.

    const double PI = 3.14159265358979323846;

Readonly variables are declared using the readonly keyword and they can be assigned a value either at the time of declaration or in a constructor. These values are evaluated at runtime and cannot be changed after the object is created. They are usually used for values that are not known at compile-time but are known at runtime, or for values that are not supposed to change after the object is created.

    public class MyClass
    {
        public readonly double PI = 3.14159265358979323846;
    }

In summary, the main difference between const and readonly is that const variables are evaluated at compile-time, while readonly variables are evaluated at runtime. Therefore, const variables can be used only for values that are known at compile-time and will not change during the execution of the program, while readonly variables can be used for values that are not known at compile-time but are known at runtime, or for values that are not supposed to change after the object is created.

## What is a property in C#?

In C#, a property is a member of a class that provides a way to access a private field of the class. Properties have a public access level and are used to encapsulate the internal state of an object, while providing a way to read and write the values of the object's fields. Properties are similar to methods, but they have a syntax that is more similar to fields.

A property has a get accessor and a set accessor, which are used to read and write the value of the property, respectively. The get accessor is used to return the value of the property, and the set accessor is used to assign a new value to the property.

Here is an example of a property in C#:

    class Employee 
    {
        private string name;

        public string Name {
            get { return name; }
            set { name = value; }
        }
    }

In this example, the Name property is a public property of the Employee class. The property is backed by a private field called name. The get accessor returns the value of the name field, and the set accessor assigns a new value to the name field.

Properties are useful in C# because they allow for encapsulation and abstraction of the internal state of an object. They make it easier to change the implementation of a class without affecting the code that uses the class. Additionally, properties can be used to implement validation logic and other functionality when the value of a field is read or written.

## Explain “static” keyword in C\#

In C#, the static keyword is used to indicate that a member (field, property, method, etc.) belongs to the class, rather than to an instance of the class. When a member is declared as static, it can be accessed without creating an instance of the class.

Here are a few examples of how the static keyword is used in C#:

Static Fields: A static field is a field that belongs to the class, rather than to an instance of the class. It can be accessed directly from the class, without creating an instance of the class.

    class Counter 
    {
        public static int Count;
    }

Static Methods: A static method is a method that belongs to the class, rather than to an instance of the class. It can be accessed directly from the class, without creating an instance of the class.

    class Calculator 
    {
        public static int Add(int a, int b) {
            return a + b;
        }
    }

Static Properties: A static property is a property that belongs to the class, rather than to an instance of the class. It can be accessed directly from the class, without creating an instance of the class.

    class Config 
    {
        public static string Version { get; set; }
    }

Static Constructors: A static constructor is a special constructor that is called once when the class is first loaded. It can be used to initialize static fields and perform other class-level initialization tasks.

    class Logger 
    {
        private static string logFile;

        static Logger() 
        {
            logFile = Path.Combine(Environment.CurrentDirectory, "log.txt");
        }
    }

In summary, the static keyword is used to indicate that a member of a class belongs to the class, rather than to an instance of the class. This allows them to be accessed directly from the class, without creating an instance of the class.

## How is the using pattern useful? What is IDisposable? How does it support deterministic finalization?

The using pattern in C# is a convenient way to ensure that resources, such as database connections, file handles, and other unmanaged resources, are properly released when they are no longer needed. The pattern is implemented by wrapping the resource in a using block, which automatically calls the Dispose() method on the resource when the block is exited.

IDisposable is an interface that defines the Dispose() method. When an object implements this interface, it is indicating that it has resources that need to be manually released.

The using statement is a C# construct that is implemented in terms of the IDisposable interface. It creates a block in which an object is created and used, and then disposed of at the end of the block. The using statement ensures that the object is disposed of even if an exception occurs within the block.

    using (SqlConnection connection = new SqlConnection(connectionString))
    {
        // use the connection here
    }

The using statement is equivalent to the following code:

    SqlConnection connection = new SqlConnection(connectionString);
    try
    {
        // use the connection here
    }
    finally
    {
        if (connection != null)
        {
            connection.Dispose();
        }
    }

When an object is disposed of, it releases any unmanaged resources it holds and makes them available to other parts of the program. This is known as deterministic finalization because the developer has control over when the resource is released and is not dependent on the garbage collector to release it.

In summary, the using pattern in C# is a convenient way to ensure that resources are properly released when they are no longer needed by wrapping the resource in a using block. IDisposable is an interface that defines the Dispose() method, that when an object implements this interface, it is indicating that it has resources that need to be manually released. The using statement ensures that the object is disposed of even if an exception occurs within the block and it supports deterministic finalization because the developer has control over when the resource is released and is not dependent on the garbage collector to release it.

## How is exception handling done in C#?

In C#, exception handling is done using the try-catch-finally block. The try block contains the code that may throw an exception, the catch block contains the code that handles the exception, and the finally block contains the code that is always executed regardless of whether an exception was thrown or not.

The basic structure of exception handling in C# is as follows:

    try
    {
        // code that may throw an exception
    }
    catch (ExceptionType e)
    {
        // code to handle the exception
    }
    finally
    {
        // code that is always executed
    }

The try block contains the code that may throw an exception. If an exception is thrown, the program jumps to the appropriate catch block. If no catch block is found, the program continues to search for an exception handler in the call stack.

The catch block contains the code that handles the exception. The catch block is passed an object of the exception class that was thrown. This object can be used to get information about the exception, such as the message and stack trace.

The finally block contains the code that is always executed regardless of whether an exception was thrown or not. This block is typically used to release resources, such as file handles and database connections, that were acquired in the try block.

    try
    {
        // code that may throw an exception
        int x = int.Parse("abc");
    }
    catch (FormatException ex)
    {
        // code to handle FormatException
        Console.WriteLine(ex.Message);
    }
    catch (Exception ex)
    {
        // code to handle other exceptions
        Console.WriteLine(ex.Message);
    }
    finally
    {
        // code that is always executed
        Console.WriteLine("Finally block executed");
    }

In the above example try block contains the code that may throw an exception. If an exception is thrown, the program jumps to the appropriate catch block. In this case, the exception thrown is FormatException, so the program jumps to the first catch block, where the message of the exception is printed on the console. And finally block is executed after the catch block.

In summary, exception handling in C# is done using the try-catch-finally block. The try block contains the code that may throw an exception, the catch block contains the code that handles the exception and the finally block contains the code that is always executed regardless of whether an exception was thrown or not.

## Can we execute multiple catch blocks in C#?

Yes, you can execute multiple catch blocks in C#.

When an exception is thrown, the program looks for a catch block that can handle the exception. If a catch block is found, the program executes the code in that block and then continues execution after the catch block.

If an exception is thrown and the first catch block does not handle it, the program continues to look for catch blocks that can handle the exception. If a catch block is found, the program executes the code in that block and then continues execution after the catch block.

You can use multiple catch blocks to handle different types of exceptions that can occur in the same try block. Each catch block must handle a different type of exception.

    try
    {
        // code that may throw an exception
        int x = int.Parse("abc");
        int y = int.Parse("5");
        int z = x / y;
    }
    catch (FormatException ex)
    {
        // code to handle FormatException
        Console.WriteLine(ex.Message);
    }
    catch (DivideByZeroException ex)
    {
        // code to handle DivideByZeroException
        Console.WriteLine(ex.Message);
    }
    catch (Exception ex)
    {
        // code to handle other exceptions
        Console.WriteLine(ex.Message);
    }

In the above example, the try block contains three statements that may throw an exception. The first statement throws a FormatException when it fails to parse the string "abc" to integer. The second statement does not throw any exception. The third statement throws a DivideByZeroException when it tries to divide by zero.

The catch block for FormatException handles the exception thrown by the first statement. The catch block for DivideByZeroException handles the exception thrown by the third statement. And the general catch block handles other exceptions not handled by the first two catch blocks.

It's important to remember that the catch blocks are executed in the order they are written, so it is important to order them correctly. The most specific exception types should be handled first, then the more general exception types.

## Why would you use the “finally” block in C#?

The "finally" block in C# is used to ensure that certain code is executed after a try-catch block, regardless of whether an exception was thrown or not. It is useful for cleaning up resources, such as closing file handles, closing database connections, and releasing memory.

For example, you may open a file, read some data from it, and then close the file. You would want to close the file, even if an exception is thrown while reading the data.

    try
    {
        FileStream file = new FileStream("file.txt", FileMode.Open);
        // Read data from the file
        //...
    }
    catch (IOException ex)
    {
        Console.WriteLine(ex.Message);
    }
    finally
    {
        file.Close();
    }

In this example, the finally block is used to close the file handle, regardless of whether an exception was thrown or not. This ensures that the file is closed and the resources are freed, even if an exception is thrown while reading the data.

It's important to note that the finally block is executed after the try and catch blocks, regardless of whether an exception was thrown or not and whether an exception was handled or not. This makes it a useful place to put code that needs to be executed in all cases, such as cleaning up resources.

## Why is “catch(Exception)” almost always a bad idea?

Catching all exceptions using "catch(Exception)" is generally considered a bad practice because it hides important information about the error that occurred. When an exception is caught, it's important to understand the type of exception that was thrown so that the appropriate action can be taken to handle the error.

When you catch all exceptions with "catch(Exception)", it can be difficult to understand what went wrong and how to fix it. It's also difficult to know which exception should be handled where, and how to handle them.

Additionally, using a catch-all exception handler can cause performance issues. When an exception is thrown, the runtime has to walk the call stack and check each catch block to see if it matches the exception type. If the first catch block is a catch-all, it will prevent the runtime from checking any other catch blocks, which can lead to poor performance.

It's a best practice to catch specific exceptions that you know how to handle, and let the others propagate up the call stack so that they can be handled by a higher-level error handler or logged for later analysis.

Instead of "catch(Exception)", it's recommended to catch specific exception types. For example:

    try
    {
        // code that can throw an exception
        //...
    }
    catch (FileNotFoundException ex)
    {
        Console.WriteLine(ex.Message);
    }
    catch (IOException ex)
    {
        Console.WriteLine(ex.Message);
    }

This way you can handle specific exception types in specific ways, and the program can continue running.

## List out two different types of errors in C\#

There are two different types of errors in C#: compile-time errors and runtime errors.

1. Compile-time errors: These are errors that occur when the code is being compiled. Examples include syntax errors, missing semicolons, and undeclared variables. These errors prevent the code from being executed and must be fixed before the program can run.
2. Run-time errors: These are errors that occur while the code is being executed. Examples include null reference exceptions, index out of bounds exceptions, and divide by zero exceptions. These errors occur when the code is running and can be difficult to track down and fix.

It's important to note that there are also semantic errors which are errors that don't raise any exception, but the program doesn't behave as expected.

## Can we get an error while executing “finally” block in C#?

Yes, it is possible to get an error while executing the "finally" block in C#. The "finally" block is executed regardless of whether an exception is thrown or not, so if there is an error in the code within the "finally" block, it will be thrown and can be caught and handled just like any other exception.

For example:

    try
    {
        // code that can throw an exception
        //...
    }
    catch (FileNotFoundException ex)
    {
        Console.WriteLine(ex.Message);
    }
    finally
    {
        // code that can throw an exception
        //...
    }

In this case, if an exception is thrown in the try block, it will be caught by the catch block. However, if there is an error in the code within the finally block, it will also throw an exception and can be caught by an additional catch block.

It's important to be aware of this, and to handle any possible exception that could occur in the finally block.

## What is the difference between “out” and “ref” parameters in C#?

In C#, the "out" and "ref" keywords are used to pass parameters to a method by reference. The main difference between the two is the way the parameters are passed and the way they are used inside the method.

"out" parameters: An "out" parameter is a parameter that is passed to a method but doesn't have to be initialized before being passed. The method is responsible for initializing the value of the "out" parameter. Once the method has finished executing, the "out" parameter will have a value that can be used by the calling code.

    void GetValue(out int result)
    {
        result = 5;
    }
    ...
    int number;
    GetValue(out number);
    Console.WriteLine(number); // Output: 5

"ref" parameters: A "ref" parameter is a parameter that must be initialized before being passed to the method. The method can then use the value of the "ref" parameter, and it can also modify the value of the "ref" parameter. Once the method has finished executing, the "ref" parameter will have the new value that the method assigned to it.

    void GetValue(ref int result)
    {
        result = 10;
    }
    ...
    int number = 5;
    GetValue(ref number);
    Console.WriteLine(number); // Output: 10

It's important to note that "out" and "ref" parameters are not the same as return values. A method can return a value, but it can also use "out" and "ref" parameters to return multiple values.

In summary, "out" parameters are used when a method needs to return multiple values, and "ref" parameters are used when a method needs to modify the value of a variable passed to it. Both "out" and "ref" parameters allow the method to modify the value of the parameter, but "out" parameters don't need to be initialized before passing them to the method, while "ref" parameters do.

## Can we use “this” inside a static method in C#?

In C#, the "this" keyword refers to the current instance of the class, and it can only be used within an instance method or a property. It cannot be used within a static method because a static method does not have access to the current instance of the class.

A static method is a method that is associated with the class and not with any specific instance of the class. It can be called using the class name, and it does not require an object of the class to be created before it is called. It does not have access to the "this" keyword, and it cannot access non-static members of the class.

For example:

    class Example
    {
        public static void StaticMethod()
        {
            // This will cause a compile-time error
            // because "this" cannot be used in a static method.
            this.NonStaticMethod();
        }
        public void NonStaticMethod()
        {
        }
    }

In summary, "this" keyword can't be used inside a static method because a static method doesn't have access to the current instance of the class, it is associated with the class and not with any specific instance of the class.

## Can we have a “try” block without a “catch” block in C#?

In C#, a "try" block can be used without a "catch" block, but it must be accompanied by a "finally" block.

A "try" block is used to enclose code that may throw an exception. When an exception is thrown, the code inside the "try" block will stop executing, and control will be transferred to the "catch" or "finally" block.

A "catch" block is used to handle the exception that was thrown. It contains the code that will be executed when the exception is thrown. If an exception is thrown and there is no "catch" block to handle it, the program will terminate.

A "finally" block is used to enclose code that should always be executed, regardless of whether an exception was thrown or not. This block is optional, but if a "try" block does not have a "catch" block, it must have a "finally" block.

For example:
    try
    {
        // code that may throw an exception
    }
    finally
    {
        // code that will always be executed
    }

In summary, you can have a "try" block without a "catch" block, but it must be accompanied by a "finally" block in C#.

## Can we override a private virtual method in C#?

In C#, a private virtual method cannot be overridden by a derived class.

A virtual method is a method that can be overridden by a derived class, allowing the derived class to provide its own implementation of the method. To override a virtual method, the derived class must use the "override" keyword when defining the method.

A private method, on the other hand, is a method that is only accessible within the class that defines it. It cannot be accessed by any other classes, including derived classes.

Since a private method is not accessible to derived classes, it cannot be overridden. Therefore, a private virtual method cannot be overridden by a derived class.

For example:

class Base
{
    private virtual void DoWork()
    {
        // implementation
    }
}

class Derived : Base
{
    // this will not be allowed, because DoWork is private and can not be overridden
    // override void DoWork()
    // {
    //    // implementation
    // }
}

In summary, you can't override a private virtual method in C#. A private virtual method cannot be overridden by a derived class because a private method is not accessible to derived classes.

## What's the difference between IEquatable and just overriding Object.Equals()?

`IEquatable<T>` is an interface in C# that defines a single method, Equals(T other), which compares the current object to another object of the same type. It's used to establish value equality between two instances of a class.

On the other hand, Object.Equals(Object obj) is a method that is inherited by all objects in C# and it compares the current object to another object for reference equality.

Here are a few key differences between the two:

`IEquatable<T>` is a generic interface, whereas Object.Equals(Object obj) is not.
`IEquatable<T>` is typically used to establish value equality, whereas Object.Equals(Object obj) is used to establish reference equality.
`IEquatable<T>` requires the implementation of a single method Equals(T other), whereas Object.Equals(Object obj) is already implemented by the base class Object and can be overridden.
An example of `IEquatable<T>` implementation is :

    public class MyType : IEquatable<MyType>
    {
        public int Id { get; set; }
        public string Name { get; set; }

        public bool Equals(MyType other)
        {
            if (other == null)
                return false;

            return this.Id == other.Id && this.Name == other.Name;
        }
    }

An example of overriding Object.Equals() is:

    public class MyType
    {
        public int Id { get; set; }
        public string Name { get; set; }

        public override bool Equals(object obj)
        {
            var other = obj as MyType;
            if (other == null)
                return false;

            return this.Id == other.Id && this.Name == other.Name;
        }
    }

In summary, `IEquatable<T>` is an interface that allows you to establish value equality between two instances of a class, whereas Object.Equals(Object obj) is a method that allows you to establish reference equality between two objects.

## Explain the differences between public, protected, private and internal

In C#, the access modifiers determine the level of visibility and accessibility of class members and types.

- Public: A class member or type marked as public is accessible from anywhere, both within the same assembly and from other assemblies.
- Protected: A class member or type marked as protected is accessible only within the same class and its subclasses.
- Private: A class member or type marked as private is only accessible within the same class.
- Internal: A class member or type marked as internal is accessible only within the same assembly.

In general, it's a best practice to use the most restrictive access level that still allows the code to function properly. This makes the code more maintainable and less prone to errors.

## Explain the access modifier – “protected internal” in C\#

In C#, the access modifier "protected internal" is a combination of the "protected" and "internal" modifiers.

A class member or type marked as "protected internal" is accessible within the same assembly and also within the same class and its subclasses. It means it is accessible only within the assembly and to the derived classes in any assembly.

This access modifier is useful when you have a class or member that needs to be accessible to derived classes in any assembly, but not to other classes in the same assembly. This allows you to maintain encapsulation while still allowing derived classes to access the protected internal members.

## What’s the difference between using `override` and `new` keywords when defining method in child class?

In C#, when defining a method in a child class, you can use the override and new keywords to indicate how the method should behave with respect to the method it is overriding in the parent class.

Using the override keyword tells the compiler that the method in the child class is intended to override an existing method with the same signature in the parent class. This method is expected to provide a new implementation of the functionality that the parent class method provides. When a method is marked as override, the runtime will call the child class's implementation of the method when the method is called on an object of the child class type. The override keyword ensures that the method in the child class has the same signature and return type as the method it is overriding in the parent class.

Using the new keyword tells the compiler that the method in the child class is intended to hide an existing method with the same signature in the parent class. This method is not expected to provide a new implementation of the functionality that the parent class method provides. When a method is marked as new, the runtime will call the parent class's implementation of the method when the method is called on an object of the child class type. A method marked as new can have a different signature or return type than the method it is hiding in the parent class.

It's generally recommended to use override when you want to change the behavior of a method in a derived class, and new when you want to add a method with the same name as a method in the base class without changing the original behavior of the base class method.

## Explain the String Builder class in C\#

The StringBuilder class in C# is a mutable (modifiable) string class. It is used to manipulate and optimize strings by providing a way to build a string, append characters or strings to it, and insert characters or strings at a specific position. Unlike the standard string class, which is immutable, the StringBuilder class allows for efficient manipulation of strings by avoiding the creation of a new string object every time a modification is made. The StringBuilder class is useful for situations where a large amount of string manipulation is required, such as when building large strings from a loop or when working with large data sets. It also has a capacity property which allows to set the number of characters that a StringBuilder object can store before it is automatically resized.

## How we can sort the array elements in descending order in C#?

There are several ways to sort an array in descending order in C#:

Using the Array.Sort() method with a custom comparer:

    int[] numbers = { 3, 7, 1, 5, 2, 9, 4, 6, 8 };
    Array.Sort(numbers, (x, y) => y.CompareTo(x));

Using the LINQ OrderByDescending() method:

    int[] numbers = { 3, 7, 1, 5, 2, 9, 4, 6, 8 };
    numbers = numbers.OrderByDescending(x => x).ToArray();

Using Array.Reverse() method after Array.Sort():

    int[] numbers = { 3, 7, 1, 5, 2, 9, 4, 6, 8 };
    Array.Sort(numbers);
    Array.Reverse(numbers);

All the above methods will sort the elements of the array numbers in descending order.

## Explain Generics in C\#

Generics in C# is a way to create reusable classes and methods that work with any data type, rather than being specific to a single data type. This is achieved by using a placeholder data type (referred to as a generic type parameter) that is specified when the class or method is instantiated or called. The advantage of using generics is that it allows for the creation of more flexible, efficient, and type-safe code. For example, the `List<T>` class in C# is a generic implementation of a list data structure, where T represents the type of elements that the list will contain. This allows the same list class to be used to create a list of integers, a list of strings, or a list of any other data type, without having to create separate classes for each data type.

## Can you use a value type as a generic type argument in C#? For example when implementing an interface like (IEquatable)

Yes, it is possible to use value types as generic type arguments in C#. Value types, such as integers and structs, can be used as the type argument when instantiating a generic class or implementing a generic interface, such as `IEquatable<T>`. For example, the struct Point could implement `IEquatable<Point>` by providing its own implementation of the Equals method.

    struct Point : IEquatable<Point>
    {
        public int X { get; set; }
        public int Y { get; set; }

        public bool Equals(Point other)
        {
            return this.X == other.X && this.Y == other.Y;
        }
    }

It's important to note that value types are passed by value by default in C#, which means that a copy of the value is passed to the method instead of a reference. This can have some implications when working with value types as generic type arguments, such as when they are used as the type argument for a reference type like a class. In these cases, it is necessary to use the ref or out keyword to pass the value type by reference.

## What are Nullable Types in C#?

In C#, a nullable type is a feature that allows value types to be assigned a value of null. This is useful when working with databases or other systems where a value may not be present. A nullable type is represented by the generic `Nullable<T>` structure, where T is the underlying value type. For example, a nullable int is represented by the type `Nullable<int>`. The value of a nullable type can be accessed using the Value property, and it can be checked for null using the HasValue property. The following example shows how to declare and use a nullable type:

    int? num = null;
    Console.WriteLine(num.HasValue); // Outputs "False"
    num = 5;
    Console.WriteLine(num.HasValue); // Outputs "True"
    Console.WriteLine(num.Value);    // Outputs "5"

## Conceptually, what is the difference between early-binding and late-binding?

Early binding and late binding refer to the process of resolving method calls or variable references at runtime.

Early binding, also known as static binding or compile-time binding, is when the type of an object is determined at compile-time and the appropriate method or variable is called at runtime. This is the default behavior in most programming languages, including C# and Java. The compiler is able to determine the exact type of the object, and it generates code to call the appropriate method or variable based on that type. This results in faster performance at runtime, but it can also result in a compile-time error if the type of the object is not known.

Late binding, also known as dynamic binding or runtime binding, is when the type of an object is determined at runtime and the appropriate method or variable is called. This is typically achieved through the use of reflection or dynamic languages such as Python or JavaScript. Since the type of the object is not known at compile-time, the code cannot be optimized for performance, but it provides more flexibility at runtime. In C#, the dynamic keyword provides support for late binding.

In summary, early binding allows the compiler to optimize the code and catch errors early, while late binding allows for more flexibility and dynamic behavior at runtime.

## What is delegate, event, callback, multicast delegate?

A delegate is a type that defines a method signature. It is a reference type that can hold a reference to a method. It is often used to pass methods as arguments to other methods.

An event is a mechanism for communication between objects. It allows objects to subscribe to an event and be notified when the event occurs. Events are typically implemented using delegates.

A callback is a pattern where a method is passed as an argument to another method, and is invoked by the latter at a certain point. It is similar to an event, but with less overhead and more flexibility.

A multicast delegate is a delegate that can hold references to multiple methods and invoke them all when invoked itself. It is useful for implementing events that need to notify multiple subscribers.

Code examples:

        // Delegate
        public delegate void MyDelegate(string message);
    
        // Event
        public event EventHandler MyEvent;
    
        // Callback
        public void MyMethod(Action<string> callback)
        {
            callback("Hello World");
        }
    
        // Multicast delegate
        public delegate void MyDelegate(string message);
        public class MyClass
        {
            public event MyDelegate MyEvent;
    
            public void MyMethod()
            {
                MyEvent("Hello World");
            }
        }

## What is enum in C#?

An enum, short for enumeration, is a value type in C# that represents a set of named constants. It is used to define a set of named values for a variable, and these values are usually integers. The primary advantage of using an enum is that it makes your code more readable, as the variable is associated with a set of predefined, human-readable values. For example, you could define an enum named "DaysOfWeek" that contains the values "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday", and "Sunday". This way, instead of storing the integer values of 1,2,3,4,5,6,7 in the variable, you can use the more meaningful names.

Examples:

    // Define enum
    public enum DaysOfWeek
    {
        Monday,
        Tuesday,
        Wednesday,
        Thursday,
        Friday,
        Saturday,
        Sunday
    }
    
    // Use enum
    DaysOfWeek day = DaysOfWeek.Monday;

## What is null-conditional operator?

The null-conditional operator (?.) is a feature in C# that allows for null-safe navigation of an object's properties and methods. The operator is used to check if an object is null before trying to access its properties or methods. If the object is null, the operator returns null, otherwise it returns the property or method value. This operator is useful for avoiding null reference exceptions when working with objects that may be null. For example, instead of writing:

    if (obj != null)
    {
        var x = obj.Name;
    }

We can use the null-conditional operator:

    var x = obj?.Name;

This way, if obj is null, x will be assigned null and no exception will be thrown.

## What is null-coalescing operator?

The null-coalescing operator (??) is a shorthand way to check if a nullable value is null, and if so, provide a default value. It is used in the following format:

    variableName = nullableValue ?? defaultValue;

This will assign defaultValue to variableName if nullableValue is null, otherwise it will assign nullableValue to variableName.
It is used to avoid null reference exception.
Example:

    int? x = null;
    int y = x ?? -1; // y will be assigned the value -1, because x is null

## What is the difference between ref & out parameters?

The main difference between ref and out parameters is in how they are used when the method is called.

A ref parameter must be initialized before it is passed to the method, and its value can be read and modified within the method. The modified value is then returned to the caller.

An out parameter does not need to be initialized before it is passed to the method, and its value can only be modified within the method. The modified value is then returned to the caller.

In summary, ref parameters are used when the caller and callee need to share the same variable, out parameters are used when the callee needs to return multiple values.

## What is serialization?

Serialization is the process of converting an object's state to a format that can be stored or transmitted, and later reconstructed to its original form. This allows objects to be saved to a file, sent over a network, or stored in a database, among other possibilities. Common formats for serialization include JSON, XML, and binary formats. Serialization can be performed using built-in libraries or third-party libraries in the programming language being used.

## Can “this” be used within a static method?

No, the "this" keyword cannot be used within a static method because it refers to the current instance of the class, and a static method is not associated with any specific instance of a class. It is a method that belongs to the class itself, rather than an instance of the class.

## What is the difference between Finalize() and Dispose() methods?

The Finalize() method is used to perform cleanup operations on unmanaged resources held by an object before it is destroyed by the garbage collector. This method is called automatically by the garbage collector, and cannot be called directly by the developer.

The Dispose() method, on the other hand, is a public method that can be called directly by the developer to release managed and unmanaged resources. It is typically used to implement the IDisposable interface and is a more explicit way to release resources, as opposed to relying on the garbage collector.

The primary difference between the two is that the Dispose() method is used to release resources explicitly and immediately, while the Finalize() method is used to release resources in a non-deterministic way when the garbage collector decides to collect the object.

## How do you inherit a class from another class in C#?

In C#, a class can inherit from another class by using the ": base" syntax in the class declaration. The base class must have the "public" or "internal" access modifier. For example:

    public class BaseClass
    {
        public int x;
    }
    
    public class DerivedClass : BaseClass
    {
        public int y;
    }

This makes DerivedClass inherit from BaseClass, and allows DerivedClass to access to its public and protected members.

## Why can’t you specify the accessibility modifier for methods inside the interface?

In C#, methods inside an interface do not have an accessibility modifier because they are always public. This is because interfaces are contracts and all methods in an interface must be implemented by any class or struct that implements the interface. Therefore, it would not make sense to specify a different accessibility level for the methods inside an interface. Additionally, it makes the code more consistent and easier to understand, as all methods inside an interface are guaranteed to be public.

## What is the difference between “is” and “as” operators in C#?

In C#, the "is" operator is used to check if an object is of a certain type, or can be cast to a certain type. It returns a boolean value indicating whether the test was successful or not. For example, "object x is int" would return true if x is an integer, and false otherwise.

The "as" operator is similar, but instead of returning a boolean value, it attempts to cast the object to the specified type. If the cast is successful, the result is the object cast to the specified type. If the cast is not possible, the result is null. For example, "int y = x as int" would set y to the value of x if x is an integer, or to null if x is not an integer.

## What are indexers in C# .NET?

Indexers in C# .NET are properties that allow you to access an object's elements like an array. They provide a way to access elements of a class or struct using the array access notation, i.e. square brackets []. For example, instead of having a method that returns a specific element of an array, you can use an indexer to access that element directly. The syntax for an indexer is similar to that of a property, but it uses the "this" keyword and includes an index parameter. Indexers can be used to create classes and structs that behave like arrays, lists, dictionaries and other data structures that use indexed access to their elements.

## What is LINQ? Explain the idea of extension methods

LINQ (Language Integrated Query) is a set of features in C# and other .NET languages that allows developers to perform querying operations on data sources such as collections, arrays, and databases. It provides a unified syntax for querying different types of data sources, making it easier to write and maintain code.

An extension method is a special type of static method that allows developers to add new methods to existing types without modifying the original code. The method is defined in a static class and is called as if it were an instance method on the type to which it is extending. This allows developers to add functionality to existing types in a way that is consistent with the original design and that does not require modification of the original source code.

## How is the “yield” keyword used? Mention at least one practical scenario where it can be used

The "yield" keyword is used in C# to define iterators, which are methods that return an IEnumerable or IEnumerator object. It is used to implement the IEnumerable interface, which allows an object to be used in a foreach loop. The "yield" keyword is used to return elements of the sequence one at a time, rather than returning the entire sequence at once. This allows the method to be used in a foreach loop without having to load the entire sequence into memory at once.

## What’s the difference between camel and pascal casing?

Camel casing is a naming convention in which the first letter of the first word is lowercase, and the first letter of each subsequent word is uppercase. For example, "camelCasing".

Pascal casing is a naming convention in which the first letter of each word is uppercase. For example, "PascalCasing".

## What is reflection?

Reflection is the ability of a program to examine its own structure and behavior at runtime. It allows developers to inspect and modify the attributes and behavior of types, methods, and properties at runtime. It is used to implement features such as dependency injection, serialization, and unit testing.

## What are attributes in C#? Give some examples of usage of them

Attributes are metadata that can be applied to types, methods, properties, and other elements in C#. They are used to provide additional information about the program to the compiler, and can be used to control the behavior of the program at runtime. For example, the [Serializable] attribute is used to mark a class as serializable, and the [Obsolete] attribute is used to mark a method as obsolete and provide a message to the developer.

## By what mechanism does NUnit know what methods to test?

NUnit uses reflection to find all the methods in a class that are marked with the [Test] attribute. It then executes each of these methods in turn, and reports the results of each test. This allows developers to write tests without having to modify the test runner. It also allows developers to write tests in a way that is consistent with the original design, and that does not require modification of the original source code. This makes it easier to write and maintain tests. 

## What is the GAC? What problem does it solve?

The Global Assembly Cache (GAC) is a central repository for assemblies that are shared by multiple applications. It allows developers to share assemblies between applications without having to copy them to each application's directory. This makes it easier to deploy applications, as developers do not have to worry about copying assemblies to each application's directory. It also makes it easier to update assemblies, as developers only need to update the assembly in the GAC, and all applications that use that assembly will automatically use the updated version.
