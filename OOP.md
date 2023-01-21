# OOP

Link to [Codecool workbook](https://docs.google.com/document/d/1HZQEaAAHV8NTX-NDRTW7DMU7bgKdReGa/edit?usp=sharing&ouid=103462021949259031432&rtpof=true&sd=true) with other answers to these quesetions.

## What is OOP?

Object-oriented programming (OOP) is a programming paradigm that uses objects and their interactions to design applications and computer programs. It is based on the concept of "objects", which can contain data and code that manipulates that data. OOP languages, such as C#, allow for the creation of reusable and modular code, as well as the ability to model real-world objects and their relationships in a more intuitive way. OOP also includes concepts such as inheritance, polymorphism, and encapsulation which allows for a more organized and efficient coding.

## What is a class?

A class is a blueprint or template for creating objects in object-oriented programming. It defines a set of properties and methods that an object of that class will have. A class defines the structure and behavior of a specific type of object, and it serves as a blueprint for creating multiple objects of the same type.

For example, in C#, a class can be defined as follows:

    ```csharp
    class MyClass
    {
        public int myInt;
        public void MyMethod() { /* code */ }
    }
    ```

This class, named "MyClass", has a public integer property called "myInt" and a public method called "MyMethod". Objects can be created from this class using the "new" keyword, like this:

    ```csharp
    MyClass myObject = new MyClass();
    ```

And it can be accessed using this object.

## What is an object?

An object is an instance of a class in object-oriented programming. It is a concrete representation of the blueprint or template defined by a class. An object is created by using the "new" keyword and a class constructor, like this:

    ```csharp
    MyClass myObject = new MyClass();
    ```

An object is a combination of data and methods that operate on that data. The data is stored in the object's properties, and the methods define the behavior of the object. Objects can also interact with other objects, sending messages and receiving messages in response.

For example, in the class `MyClass` defined earlier, `myObject` is an instance of `MyClass`, it has a property `myInt` and a method `MyMethod()`. The object can access the properties and methods of the class and can perform the functionality that is defined by the class.

## What is casting? What is the difference between up vs downcasting?

Casting is the process of converting one data type to another. In C#, casting can be done either implicitly or explicitly. Implicit casting is when the compiler can automatically convert one data type to another, while explicit casting is when the programmer must specify the conversion.

Upcasting is the process of converting a derived class object to a base class object. It is also known as a widening conversion. It is safe because a derived class object is always a base class object. Upcasting is done implicitly.

Downcasting is the process of converting a base class object to a derived class object. It is also known as a narrowing conversion. It is not always safe because a base class object may not always be a derived class object. Downcasting requires an explicit cast to be done by the programmer, using the "as" or "is" keyword, or a direct cast using the "(Type)" notation.

For example, in C#,

    ```csharp
    BaseClass b = new DerivedClass(); // upcasting
    DerivedClass d = (DerivedClass) b; // downcasting
    ```

In the first line, `b` is a `BaseClass` object, and `DerivedClass` is derived from `BaseClass`, so it is a safe upcasting. In the second line, `b` is explicitly converted to `DerivedClass` object, it is a downcasting.

## What is Encapsulation? Explain the concept with a realistic example

Encapsulation is a fundamental concept in object-oriented programming (OOP) that refers to the practice of hiding the internal state and behavior of an object from the outside world. It is a way of protecting the integrity of an object by preventing unauthorized access to its internal data and methods.

The main idea behind encapsulation is to bundle the data (attributes) and methods (operations) that manipulate the data in a single unit called a class. The class can then be used to create objects that share the same behavior and data. Each object can have its own state (values of the attributes), but the behavior is shared among all objects of the same class.

A realistic example can be a Bank account class. It can have the attribute like account number, balance, and account holder name. The class can have methods like deposit, withdraw, check balance, etc. The user of the class should not have direct access to the internal state of the object, like balance. Instead, the class should provide methods to access the balance, like getBalance() or checkBalance().

This way, the class can control the way the balance is accessed and modified, and can enforce certain rules, such as not allowing the balance to go below zero. By encapsulating the balance attribute and the methods that manipulate it, the class can ensure the integrity of the object's state.

Encapsulation also allows for greater flexibility and maintainability of the code, as the internal implementation of the class can be changed without affecting the code that uses the class.

## What is Polymorphism? Explain the concept with a realistic example

Polymorphism is a concept in object-oriented programming that allows objects of different classes to be treated as objects of a common superclass. It allows objects to be used interchangeably, regardless of their specific type. Polymorphism enables objects to respond to the same method call in different ways, depending on their actual type.

There are two types of polymorphism:

1. Compile-time polymorphism or static polymorphism, which is also known as overloading.
2. Runtime polymorphism or dynamic polymorphism, which is also known as overriding.

A realistic example of polymorphism can be an application that deals with different types of shapes like a rectangle, circle, and triangle. All of these shapes can have a common method named `draw()` which is overridden in each derived class to provide the specific implementation for each shape.

    ```csharp
    class Shape 
    {
        public virtual void draw() { /* code for drawing the shape */ }
    }

    class Rectangle : Shape 
    {
        public override void draw() { /* code for drawing a rectangle */ }
    }

    class Circle : Shape 
    {
        public override void draw() { /* code for drawing a circle */ }
    }
    ```

In this example, the `draw()` method is defined in the base class `Shape` and overridden in derived classes `Rectangle` and `Circle` to provide specific implementation for each shape.

Now, we can create an array of shape objects and call the `draw()` method on each of them without knowing the actual type of the object.

    ```csharp
    Shape[] shapes = { new Rectangle(), new Circle()};
    foreach (Shape s in shapes)
    {
        s.draw();
    }
    ```

The `draw()` method will call the appropriate implementation of the method for the actual type of the object, whether it is a rectangle or a circle. This allows the same code to work with different types of objects, which is the essence of polymorphism.

## What is Inheritance? Explain the concept with a realistic example

Inheritance is a concept in object-oriented programming that allows one class to inherit properties and methods from another class. It is a mechanism that enables the creation of a hierarchy of classes, where a derived class inherits the properties and methods of a base class. The derived class can also add new properties and methods or override the inherited ones.

A realistic example of inheritance can be a transportation system like a train or a bus. A base class `Transportation` can have common attributes like number of wheels and speed and common methods like move() and stop(). We can have derived classes like `Train` and `Bus` which can inherit the properties and methods from the base class and can have additional properties and methods specific to them like number of compartments and number of doors.

    ```csharp
    class Transportation
    {
        public int wheels;
        public int speed;
        public void move() { /* code for moving */ }
        public void stop() { /* code for stopping */ }
    }

    class Train : Transportation
    {
        public int compartments;
        public void changeTrack() { /* code for changing track */ }
    }

    class Bus : Transportation
    {
        public int doors;
        public void pickUpPassenger() { /* code for picking up passenger */ }
    }
    ```

In this example, the base class `Transportation` has two attributes `wheels` and `speed` and two methods `move()` and `stop()`. The derived classes `Train` and `Bus` inherit these attributes and methods from the base class and have additional attributes and methods specific to them. The derived class can also override the methods of the base class if necessary.

Inheritance allows for code reuse and helps to organize and structure the code in a logical way. It also allows for a more natural and intuitive representation of real-world objects and their relationships.

## Define a constructor

A constructor is a special type of method in C# that is automatically called when an object of a class is created. It is used to initialize the state of an object and allocate memory for its properties. The main purpose of a constructor is to set the initial values for the properties of the object and perform any other setup that is required before the object can be used.

A constructor is defined with the same name as the class and does not have any return type, not even void. A class can have multiple constructors with different parameters, this is called constructor overloading.

For example,

    ```csharp
    class MyClass
    {
        public int myInt;
        public MyClass() { /* default constructor */ }
        public MyClass(int value) { myInt = value; }
    }
    ```

In this example, `MyClass` has two constructors. The first one is a default constructor, which takes no arguments and does not initialize the `myInt` property. The second constructor takes an integer argument and sets the value of `myInt` to that value.

Creating an object using a constructor:

    ```csharp
    MyClass myObject = new MyClass(10);
    ```

This creates an object of `MyClass` and calls the second constructor which initializes the `myInt` to 10.

It's worth noting that if a class doesn't have any constructors defined, the compiler will automatically provide a default constructor with no parameters.

## What is method overloading?

Method overloading, also known as function overloading or compile-time polymorphism, is a feature in C# that allows a class to have multiple methods with the same name but with different parameters. When a method is called, the compiler determines which version of the method to call based on the arguments passed to the method.

Method overloading is useful when a class needs to perform similar actions with different input. Instead of creating different methods with different names, the class can use method overloading to provide different versions of the same method with different parameters.

For example,

    ```csharp
    class MyClass
    {
        public void MyMethod() { /* code */ }
        public void MyMethod(int value) { /* code */ }
        public void MyMethod(string text) { /* code */ }
    }
    ```

In this example, `MyClass` has three methods with the same name "MyMethod", but with different parameters. When the method is called, the compiler determines which version of the method to call based on the arguments passed to the method.

    ```csharp
    MyClass myObject = new MyClass();
    myObject.MyMethod();  // calls the first version of the method
    myObject.MyMethod(10);  // calls the second version of the method
    myObject.MyMethod("text");  // calls the third version of the method
    ```

It's worth noting that when overloading a method, the return type of the methods is not considered, only the parameter list is taken into account.

## What are different types of arguments? (context: pass by value / pass by reference)

When passing arguments to a method in C#, there are two main ways to pass the arguments: by value and by reference.

Pass by value means that a copy of the argument's value is passed to the method. Any changes made to the argument inside the method do not affect the original value of the argument. For example, in the following code snippet, the value of the variable `x` is passed to the method `MyMethod`, but the value of `x` is not changed after the method is called:

    ```csharp
    int x = 10;
    MyMethod(x);
    Console.WriteLine(x); // will output 10
    ```

Pass by reference means that a reference to the memory location of the argument is passed to the method. Any changes made to the argument inside the method will affect the original value of the argument. For example, in the following code snippet, the reference of the variable `x` is passed to the method `MyMethod`, and the value of `x` is changed after the method is called:

    ```csharp
    int x = 10;
    MyMethod(ref x);
    Console.WriteLine(x); // will output 20
    ```

In C#, all reference types (classes, strings, arrays, etc) are passed by reference by default. Value types (int, double, etc) are passed by value by default. When passing a value type by reference, you can use the `ref` keyword when calling the method and also when defining the method's parameter, this tells the compiler that the argument should be passed by reference.

It's worth noting that in C#, starting with version 7.0, there's another keyword called `in` and `out` which are used to pass arguments by reference but with some restrictions. `in` keyword is used to pass a readonly reference and `out` keyword is used to pass a writeonly reference.

## What is method overriding?

Method overriding, also known as runtime polymorphism or dynamic polymorphism, is a feature in C# that allows a derived class to provide a different implementation for a method that is already defined in its base class. When a method is overridden, the version of the method that is called at runtime is determined by the actual type of the object, rather than the type of the reference.

Method overriding is achieved by using the `override` keyword in the derived class and the `virtual` keyword in the base class. The method in the derived class must have the same name, return type, and parameter list as the method in the base class.

For example,

    ```csharp
    class Shape
    {
        public virtual void Draw() { /* code for drawing the shape */ }
    }
    class Rectangle : Shape
    {
        public override void Draw() { /* code for drawing a rectangle */ }
    }
    ```

In this example, the base class `Shape` has a method `Draw()` which is marked as `virtual`. The derived class `Rectangle` has a method `Draw()` which is marked as `override`.

When a `Rectangle` object is created and `Draw()` method is called on it, the overridden version of the method in the `Rectangle` class is called, which provides the specific implementation for drawing a rectangle.

    ```csharp
    Rectangle rect = new Rectangle();
    rect.Draw(); // calls the Draw() method of the Rectangle class
    ```

Method overriding allows derived classes to provide a different implementation for a method that is already defined in the base class, this allows for a more flexible and extensible code, and it also enables the creation of a class hierarchy that models real-world objects and their relationships in a more natural and intuitive way.

## What is an interface?

An interface in C# is a blueprint for a class, specifying a set of methods and properties that a class must implement. An interface defines a contract that a class must adhere to, but it does not provide an implementation for the methods or properties. It is a way to define a common set of methods and properties for multiple classes, regardless of their actual implementation.

An interface is defined using the `interface` keyword and can include methods, properties, events, and indexers. An interface can also include explicit interface implementation.

For example,

    ```csharp
    interface IShape
    {
        void Draw();
    }
    class Rectangle : IShape
    {
        public void Draw() { /* code for drawing a rectangle */ }
    }
    ```

In this example, `IShape` is an interface that defines a single method `Draw()`. The `Rectangle` class implements the `IShape` interface by providing an implementation for the `Draw()` method.

A class can implement multiple interfaces, and an interface can be implemented by multiple classes. Interfaces allow for a more flexible and extensible code, as they provide a way to define a common set of methods and properties for multiple classes, regardless of their actual implementation. Interfaces also provide a way to achieve polymorphism by allowing objects of different classes to be treated as objects of a common interface.

## What is exception handling?

Exception handling is a mechanism in C# that allows you to handle exceptional situations, such as runtime errors, in a structured and predictable way. Exception handling allows your code to continue executing even when an error occurs, by providing a way to catch and handle the exception, rather than letting the program terminate abruptly.

The basic syntax of exception handling in C# is the try-catch block. You put the code that might throw an exception in a try block, and then provide one or more catch blocks to handle the exception.

For example,

    ```csharp
    try
    {
        int result = 5 / 0;
    }
    catch (DivideByZeroException ex)
    {
        Console.WriteLine("Cannot divide by zero.");
    }
    ```

In this example, the try block contains the code that might throw an exception, in this case, dividing by zero. The catch block catches the exception of type `DivideByZeroException` and provides a way to handle the exception by displaying an error message.

It's worth noting that you can also provide a finally block which will execute whether an exception was thrown or not. You can also provide multiple catch block each handling different type of exception.

Exception handling allows your code to handle errors in a structured and predictable way, and it provides a way to continue executing even when an error occurs. This helps to create more robust and reliable software, and it also allows you to handle and recover from errors in a way that is appropriate for your specific application.

## Explain the difference between overloading and overriding

Overloading and overriding are two related but distinct concepts in object-oriented programming.

Method overloading, also known as function overloading or compile-time polymorphism, is a feature that allows a class to have multiple methods with the same name but with different parameters. When a method is called, the compiler determines which version of the method to call based on the arguments passed to the method. Method overloading is useful when a class needs to perform similar actions with different input, Instead of creating different methods with different names, the class can use method overloading to provide different versions of the same method with different parameters.

Method overriding, also known as runtime polymorphism or dynamic polymorphism, is a feature that allows a derived class to provide a different implementation for a method that is already defined in its base class. When a method is overridden, the version of the method that is called at runtime is determined by the actual type of the object, rather than the type of the reference. Method overriding is achieved by using the `override` keyword in the derived class and the `virtual` keyword in the base class. The method in the derived class must have the same name, return type, and parameter list as the method in the base class.

In summary, overloading is a feature that allows a class to have multiple methods with the same name but different parameters, while overriding is a feature that allows a derived class to provide a new implementation for a method that is already defined in the base class. Overloading is a feature that is resolved at compile time, while overriding is a feature that is resolved at runtime.

## What is an abstraction?

Abstraction is a key concept in object-oriented programming that refers to the process of hiding the implementation details of an object or a class and exposing only the essential features to the user. Abstraction is the process of identifying the essential characteristics of an object or a class and encapsulating those characteristics in a separate entity, such as an interface or an abstract class.

An abstract class is a class that cannot be instantiated and serves as a base class for other classes. It can have abstract methods, which are methods without implementation and must be overridden in the derived classes.

For example,

    ```csharp
    abstract class Shape
    {
        public abstract void Draw();
    }
    class Rectangle : Shape
    {
        public override void Draw() { /* code for drawing a rectangle */ }
    }
    ```

In this example, the base class `Shape` is an abstract class and it has an abstract method `Draw()` which is a method without implementation. The derived class `Rectangle` implements this method by providing the specific implementation for drawing a rectangle.

An interface is another way to achieve abstraction in C#, an interface defines a contract that a class must adhere to but it does not provide an implementation for the methods or properties. It is a way to define a common set of methods and properties for multiple classes, regardless of their actual implementation.

Abstraction allows for a more flexible and extensible code, as it provides a way to hide the implementation details of an object or a class and expose only the essential features to the user. This makes the code more maintainable and easier to understand and use. It also allows for a more natural and intuitive representation of real-world objects and their relationships.

## What are access modifiers?

Access modifiers are keywords in C# that are used to control the level of access to the members of a class, such as methods, properties, and fields. Access modifiers determine which parts of the code can access the members of a class and how they can be accessed.

C# provides the following access modifiers:

* `public`: The member can be accessed from any part of the code.
* `private`: The member can only be accessed within the same class.
* `protected`: The member can be accessed within the same class and derived classes.
* `internal`: The member can be accessed within the same assembly.
* `protected internal`: The member can be accessed within the same assembly and derived classes.

By default, the access level of class members is private.

For example,

    ```csharp
    class MyClass
    {
        private int myInt;
        public int MyProperty { get; set; }
        protected void MyMethod() { /* code */ }
    }
    ```

In this example, the `myInt` field is private and can only be accessed within the same class, the `MyProperty` property is public and can be accessed from any part of the code and the `MyMethod` method is protected and can be accessed within the same class and derived classes.

Access modifiers allow you to control the level of access to the members of a class, this helps to ensure that the code is secure, maintainable and easy to understand. It also allows you to create a more flexible and extensible code by exposing only the necessary members to the user.

## What is early and late binding?

Early binding and late binding are terms used to describe the way that the runtime resolves method calls in object-oriented programming.

Early binding, also known as static binding or compile-time binding, is the process of resolving method calls at compile time. In early binding, the compiler knows the exact type of an object and can bind the method call to the appropriate method at compile time. Because the method call is resolved at compile-time, it is more efficient, as the method call doesn't need to be resolved at runtime.

For example,

    ```csharp
    Rectangle rect = new Rectangle();
    rect.Draw();
    ```

In this example, the `rect` object is of type `Rectangle`, the compiler knows the exact type of the object and can bind the method call `rect.Draw()` to the `Draw()` method of the `Rectangle` class at compile-time.

Late binding, also known as dynamic binding or runtime binding, is the process of resolving method calls at runtime. In late binding, the compiler does not know the exact type of an object and must bind the method call to the appropriate method at runtime. Because the method call is resolved at runtime, it is less efficient, as the method call needs to be resolved at runtime and it can also lead to runtime errors.

For example,

    ```csharp
    Shape shape = new Rectangle();
    shape.Draw();
    ```

In this example, the `shape` object is of type `Shape`, the compiler does not know the exact type of the object and must bind the method call `shape.Draw()` to the appropriate method at runtime, in this case the `Draw()` method of the `Rectangle` class.

In C#, early binding is the default behavior, and it's achieved by using the `virtual` and `override` keywords to define and call methods. Late binding is achieved by using the `dynamic` keyword, or by using reflection or interfaces.

In general, early binding is more efficient as it doesn't need to be resolved at runtime, but late binding can provide more flexibility and can be useful in certain cases like when working with dynamic languages or when working with objects that don't share a common interface.

## Are parameters required for constructors?

No, parameters are not required for constructors. A constructor is a special method that is called when an object of a class is created. It is used to initialize the object's state and allocate memory for the object. A constructor can have no parameters, which is called a default constructor, or it can have one or more parameters.

A default constructor is a constructor that takes no arguments and initializes the object with default values. If a class does not have a constructor defined, the compiler will automatically provide a default constructor with no parameters.

For example,

    ```csharp
    class MyClass
    {
        public MyClass()
        {
            // Initialization code
        }
    }
    ```

In this example, `MyClass` has a default constructor with no parameters.

On the other hand, a constructor with parameters is used to initialize an object with specific values when it is created. For example,

    ```csharp
    class MyClass
    {
        int x, y;
        public MyClass(int x, int y)
        {
            this.x = x;
            this.y = y;
        }
    }
    ```

In this example, `MyClass` has a constructor that takes two integers as parameters, which are used to initialize the `x` and `y` fields of the class.

In general, whether or not to use parameters in a constructor depends on the needs of the class and the desired behavior when an object is created. A default constructor with no parameters can be useful when the class only requires default initialization, while a constructor with parameters can be useful when the class requires specific initialization when an object is created.

## What is a copy constructor?

A copy constructor is a special type of constructor in C# that creates a new object and initializes it with the same values as an existing object. The copy constructor takes a single argument, which is a reference to the object to be copied, and it creates a new object with the same values as the original object.

Copy constructors are useful when you want to create a new object that has the same state as an existing object, without affecting the original object. It is typically used when creating a new object that is a copy of an existing object.

For example,

    ```csharp
    class MyClass
    {
        int x, y;
        public MyClass(int x, int y)
        {
            this.x = x;
            this.y = y;
        }
        public MyClass(MyClass other)
        {
            this.x = other.x;
            this.y = other.y;
        }
    }
    ```

In this example, `MyClass` has a constructor that takes two integers as parameters, which are used to initialize the `x` and `y` fields of the class and also has a copy constructor that takes an object of type `MyClass` and it creates a new object with the same values as the original object.

It's worth noting that when creating a copy constructor, you should consider the types of the fields of the class. If the class contains reference types, you should be careful to create a deep copy of the object instead of a shallow copy, which can cause issues like modifying the original object when the copy is modified.

Copy constructor is not a built-in feature in C#, it is a feature that is provided by the compiler when you define a constructor that takes an object of the same type as a parameter. However, you can also define a copy constructor manually by defining a constructor that takes an object of the same type as a parameter.

## Can static methods use non static members?

No, static methods cannot use non-static members (fields or properties) directly. A static method is a method that belongs to the class, rather than an instance of the class, and it can be called without creating an object of the class. Because static methods do not have an object context, they cannot access non-static members of the class directly, as they cannot refer to `this` or any other object of the class.

However, a static method can use non-static members through an instance of the class or by using a static reference to a non-static member. For example,

    ```csharp
    class MyClass
    {
        public int x;
        public static void MyStaticMethod()
        {
            MyClass instance = new MyClass();
            int y = instance.x;
        }
    }
    ```

In this example, the static method `MyStaticMethod` creates an instance of `MyClass`, and uses it to access the non-static field `x`.

It's worth noting that when a non-static member is accessed from a static method, it is accessed through an instance of the class, and not through the class itself. So, if that non-static member is modified, it will only affect the instance that is used to access it.

In general, it's a good practice to keep static methods stateless and avoid using non-static members, this makes them more reusable and easier to understand, and it also helps to avoid issues like unexpected behavior or race conditions.

## What is a base class, subclass and superclass?

In object-oriented programming, a base class, also known as a superclass, is a class that is inherited by one or more derived classes, also known as subclasses. A base class defines the common properties and methods that are shared by the derived classes.

A subclass is a class that inherits from a base class, it can add new properties and methods, and it can also override or extend the properties and methods of the base class.

For example,

    ```csharp
    class Shape
    {
        public void Draw() { /* code for drawing a shape */ }
    }

    class Rectangle : Shape
    {
        public int Width { get; set; }
        public int Height { get; set; }
        public override void Draw() { /* code for drawing a rectangle */ }
    }
    ```

In this example, `Shape` is the base class and `Rectangle` is the subclass. The `Rectangle` class inherits from the `Shape` class and it has its own properties `Width` and `Height`, and it overrides the `Draw()` method of the base class to provide its own implementation for drawing a rectangle.

The relationship between a base class and a subclass is called inheritance, and it allows for code reuse and polymorphism. A base class defines the common properties and methods that are shared by the derived classes, and a subclass can add new properties and methods, or override the properties and methods of the base class to provide its own implementation.

It's worth noting that the term superclass is used interchangeably with base class, and the term subclass is used interchangeably with derived class.

## What is static and dynamic binding?

Static binding and dynamic binding are terms used to describe the way that the runtime resolves method calls in object-oriented programming.

Static binding, also known as compile-time binding or early binding, is the process of resolving method calls at compile time. In static binding, the compiler knows the exact type of an object and can bind the method call to the appropriate method at compile time. Because the method call is resolved at compile-time, it is more efficient, as the method call doesn't need to be resolved at runtime.

For example,

    ```csharp
    Rectangle rect = new Rectangle();
    rect.Draw();
    ```

In this example, the `rect` object is of type `Rectangle`, the compiler knows the exact type of the object and can bind the method call `rect.Draw()` to the `Draw()` method of the `Rectangle` class at compile-time.

Dynamic binding, also known as runtime binding or late binding, is the process of resolving method calls at runtime. In dynamic binding, the compiler does not know the exact type of an object and must bind the method call to the appropriate method at runtime. Because the method call is resolved at runtime, it is less efficient, as the method call needs to be resolved at runtime and it can also lead to runtime errors.

For example,

    ```csharp
    Shape shape = new Rectangle();
    shape.Draw();
    ```

In this example, the `shape` object is of type `Shape`, the compiler does not know the exact type of the object and must bind the method call `shape.Draw()` to the appropriate method at runtime, in

## Which OOP concept is used as a reuse mechanism?

Inheritance is the OOP concept that is used as a reuse mechanism. It allows you to create new classes that are based on existing classes, and inherit the properties and methods of the existing classes. This allows you to reuse the existing code and extend it to create new classes with the same functionality but with additional properties or methods.

For example,

    ```csharp
    class Shape
    {
        public void Draw() { /* code for drawing a shape */ }
    }

    class Rectangle : Shape
    {
        public int Width { get; set; }
        public int Height { get; set; }
    }
    ```

In this example, the class `Rectangle` inherits from the class `Shape`, it inherits the `Draw()` method of the `Shape` class and also has its own properties `Width` and `Height`.

By inheriting from the `Shape` class, the `Rectangle` class can reuse the `Draw()` method and also add its own properties and methods. This allows for code reuse and also making the code more maintainable, as the common functionality is defined in the base class, and any changes made to the base class will be reflected in the derived classes.

Inheritance is a powerful concept that allows for code reuse, abstraction and polymorphism, it makes the code more flexible and extensible and also makes it more natural and intuitive representation of real-world objects and their relationships.

## Which OOP concept exposes only necessary information to the calling functions?

Encapsulation is the OOP concept that exposes only necessary information to the calling functions. It is the process of hiding the internal details of an object and exposing a simplified, or more abstract, public interface.

Encapsulation is achieved by using access modifiers, such as `public`, `private` and `protected`, to control the level of access to the members of a class. Public members can be accessed from any part of the code, while private members can only be accessed within the same class.

For example,

    ```csharp
    class MyClass
    {
        private int myInt;
        public int MyProperty { get; set; }
        protected void MyMethod() { /* code */ }
    }
    ```

In this example, the `myInt` field is private and can only be accessed within the same class, the `MyProperty` property is public and can be accessed from any part of the code and the `MyMethod` method is protected and can be accessed within the same class and derived classes.

Encapsulation allows you to control the level of access to the members of a class, this helps to ensure that the code is secure, maintainable and easy to understand. It also allows you to create a more flexible and extensible code by exposing only the necessary members to the user and hiding the unnecessary details of the implementation, this way the user only interacts with the functionality provided by the class and not the underlying implementation details.

Encapsulation is one of the fundamental concepts of OOP and it is often implemented in combination with other OOP concepts such as inheritance and polymorphism.

## What is data hiding?

Data hiding is a concept that is closely related to encapsulation, it refers to the practice of hiding the internal details of an object and exposing only the necessary information to the outside world. The main idea behind data hiding is to protect the internal state of an object from unauthorized access or modification, and to provide a simplified, or more abstract, public interface to the object.

Data hiding is achieved by using access modifiers, such as `private`, `protected`, and `internal` in C#, to control the level of access to the members of a class. Private members can only be accessed within the same class, protected members can be accessed within the same class and derived classes, and internal members can be accessed within the same assembly.

For example,

    ```csharp
    class MyClass
    {
        private int myInt;
        public int MyProperty { get; set; }
        protected void MyMethod() { /* code */ }
    }
    ```

In this example, the `myInt` field is private and can only be accessed within the same class, the `MyProperty` property is public and can be accessed from any part of the code, and the `MyMethod` method is protected and can be accessed within the same class and derived classes.

Data hiding is a powerful technique that helps to ensure that the internal state of an object is protected from unauthorized access or modification, it also allows you to create a more flexible and extensible code by exposing only the necessary members to the user and hiding the unnecessary details of the implementation. This way, the user only interacts with the functionality provided by the class and not the underlying implementation details.

Data hiding is one of the fundamental concepts of OOP and it is often implemented in combination with other OOP concepts such as encapsulation and inheritance.

## What is variable shadowing?

Variable shadowing is a concept that occurs when a local variable or parameter in a method has the same name as a member variable in the class. In this case, the local variable or parameter "shadows" the member variable, and the member variable is not directly accessible from the method.

When a local variable or parameter has the same name as a member variable, the local variable or parameter takes precedence within the scope of the method and any reference to the variable name within the method refers to the local variable or parameter, not the member variable.

For example,

    ```csharp
    class MyClass
    {
        int x;
        public void MyMethod(int x)
        {
            x = x + 1;
            Console.WriteLine(x); // Outputs 2
        }
    }
    ```

In this example, the local variable `x` in the `MyMethod` method shadows the member variable `x` in the `MyClass` class. Any reference to the variable `x` within the `MyMethod` method refers to the local variable `x` and not the member variable `x`.

It's worth noting that shadowing variables can lead to confusion and unexpected behavior if not handled properly. It is considered a good practice to use different names for local variables and member variables, and to use the `this` keyword to refer to the member variables explicitly.

In C#, you can use the `new` keyword to indicate that you want to shadow a variable. This is done by declaring a new variable with the same name in a derived class, but with the "new" keyword. This is often used when you want to override a variable from a base class.

For example,

    ```csharp
    class MyBaseClass
    {
        public int x;
    }

    class MyDerivedClass : MyBaseClass
    {
        new public int x;
    }
    ```

In this example, the `MyDerivedClass` shadows the `x` variable from the `MyBaseClass`.

## What is the difference between hiding a static method and overriding an instance method?

Hiding a static method and overriding an instance method are two different concepts in object-oriented programming.

When you hide a static method, you create a new method in a derived class with the same name and signature as a static method in the base class, but with the `new` keyword. When you call the method on an instance of the derived class, the new method in the derived class will be called, not the method in the base class. Hiding a static method allows you to provide a new implementation of a method in a derived class, while still preserving the original method in the base class.

For example,

    ```csharp
    class MyBaseClass
    {
        public static void MyStaticMethod() { /* code */ }
    }

    class MyDerivedClass : MyBaseClass
    {
        new public static void MyStaticMethod() { /* new code */ }
    }
    ```

When you override an instance method, you create a new method in a derived class with the same name and signature as an instance method in the base class, but with the `override` keyword. When you call the method on an instance of the derived class, the new method in the derived class will be called, not the method in the base class. Overriding an instance method allows you to provide a new implementation of a method in a derived class, while still preserving the original method in the base class.

For example,

    ```csharp
    class MyBaseClass
    {
        public virtual void MyMethod() { /* code */ }
    }

    class MyDerivedClass : MyBaseClass
    {
        public override void MyMethod() { /* new code */ }
    }
    ```

The main difference between hiding a static method and overriding an instance method is the scope of the methods. Static methods belong to the class and can be called without creating an instance of the class. Instance methods belong to an object and can be called on an instance of the class. Hiding a static method allows you to provide a new implementation of a method that belongs to the class and can be called without creating an instance of the class. Overriding an instance method allows you to provide a new implementation of a method that belongs to an object and can be called on an instance of the class.

## Define the following terms: Instantiation, Attribute, Method

* **Instantiation**: Instantiation refers to the process of creating an instance of a class. It is the process of allocating memory for an object and initializing it with the constructor of the class. An instance of a class is also known as an object.
* **Attribute**: Attribute refers to a property or field of a class that describes the characteristics of an object. An attribute is a piece of data that belongs to an object and describes its state. It can be a variable, a constant or a property.
* **Method**: A method is a block of code that can be executed by an object. It defines the behavior of an object, and it can be used to manipulate the object's attributes or perform other actions. A method can take zero or more parameters and can return a value or not. Methods are also known as functions or procedures.

For example,

    ```csharp
    class MyClass
    {
        int x;
        public int MyProperty { get; set; }
        public void MyMethod(int y) { x = x + y;}
    }
    ```

In this example, `MyClass` has one attribute `x`, one property `MyProperty` and one method `MyMethod`. To create an instance of MyClass we use the new keyword: `MyClass myObject = new MyClass();` This is the instantiation process. Now the object `myObject` has access to the attribute `x`, property `MyProperty` and method `MyMethod`.

## Explain how object oriented languages implement abstract data types

In object-oriented programming, an abstract data type (ADT) is a data type that is defined by its behavior, rather than its implementation. An ADT is an abstraction of the implementation details, and it defines a set of operations that can be performed on the data type, without specifying how the operations are implemented.

Object-oriented languages, such as C# and Java, implement ADTs by using classes. A class defines the behavior of an ADT by specifying the properties and methods that can be used to manipulate the data, and it can also define the internal state of the data, but it does not specify how the properties and methods are implemented.

For example, a stack is an ADT that can be implemented as a class in C#:

    ```csharp
    class Stack
    {
        private List<int> _items;
        public void Push(int item) { /* code for adding an item to the stack */ }
        public int Pop() { /* code for removing an item from the stack */ }
        public int Peek() { /* code for looking at the top item on the stack */ }
        public bool IsEmpty() { /* code for checking if the stack is empty */ }
    }
    ```

In this example, the class `Stack` defines the behavior of a stack ADT by providing methods for pushing, popping and peeking items, as well as checking if the stack is empty. However, it doesn't specify how these methods are implemented, for example, it doesn't specify that the stack is implemented using a List.

Through abstract data types, the implementation details are hidden from the user, and the user can only interact with the class through the provided methods, this allows for more flexibility and easy maintenance as the implementation of the class can be changed without affecting the user.

The use of abstract data types is a key concept in object-oriented programming, and it allows for the separation of concerns, where the implementation details are separated from the interface and behavior of the data type.

## Explain how object oriented languages attempt to simplify memory management for programmers

Object-oriented languages, such as C# and Java, attempt to simplify memory management for programmers by using a feature called garbage collection. Garbage collection is a mechanism that automatically frees up memory that is no longer being used by the program.

In languages that don't have garbage collection, such as C and C++, the programmer is responsible for allocating and deallocating memory manually, using functions such as malloc() and free(). This can be a time-consuming and error-prone process, as the programmer must ensure that all allocated memory is properly freed and that there are no memory leaks.

In contrast, object-oriented languages with garbage collection automatically track the references to objects in memory and periodically scan for objects that are no longer being used. When an object is no longer being used, the garbage collector frees up the memory occupied by that object, without the need for the programmer to explicitly deallocate the memory.

For example, in C#, when an object is no longer being referenced by any variable, it becomes eligible for garbage collection, and the garbage collector will automatically free up the memory occupied by that object.

    ```csharp
    MyClass myObject = new MyClass();
    myObject = null; // myObject is eligible for garbage collection
    ```

This way, the programmer can focus on the logic of the program, without worrying about the details of memory management, and leaving it to the garbage collector to manage the memory.

It's worth noting that garbage collection is not a panacea and can cause issues such as performance degradation, as well as not being deterministic, meaning that it's not possible to know exactly when an object will be collected. However, in general, it simplifies memory management for the programmers and prevents a common source of

## Explain the *Single Responsibility* principle

The Single Responsibility Principle (SRP) is a fundamental principle in object-oriented programming that states that a class or module should have only one reason to change. It means that a class should have only one responsibility, or one reason to change, and that responsibility should be completely encapsulated by the class.

The idea behind SRP is that a class should have a single, well-defined responsibility, and that it should be focused on doing one thing and doing it well. By adhering to the SRP, a class becomes more flexible, easier to understand, and easier to maintain.

For example, consider a class that is responsible for both calculating the price of an item and displaying the price on a screen. According to the SRP, this class should be split into two classes, one for calculating the price, and another for displaying the price on a screen.

This way, if the calculation of the price changes, it would only affect the class that handles the calculation, and if the display of the price changes, it would only affect the class that handles the display, and not the whole system.

By following the SRP, the classes become more cohesive, meaning that they do one thing and do it well, and more loosely coupled, meaning that they are less dependent on each other. This leads to a more maintainable, testable and scalable codebase.

It's worth noting that the Single Responsibility Principle is not only applied to classes, but also to modules, functions and methods, it's a principle that should be applied at all levels of the codebase.

## What is an object oriented program? Explain and, show an example

An object-oriented program is a type of computer program that is built using object-oriented programming (OOP) concepts. OOP is a programming paradigm that is based on the concept of objects, which are instances of classes.

In OOP, a class defines the properties and methods that an object can have and use. A class defines the blueprint for an object, and an object is an instance of a class. A class can have properties, which are variables that store data, and methods, which are functions that define the behavior of the class.

For example, consider a class named `Car` that represents a car. The class might have properties such as `make`, `model`, `year`, and `color`, and methods such as `start`, `drive`, and `stop`. Each instance of the `Car` class would have its own unique values for `make`, `model`, `year`, and `color`, and would be able to execute the `start`, `drive`, and `stop` methods.

Here is an example of a simple class in C#:

    ```csharp
    class Car
    {
        public string make;
        public string model;
        public int year;
        public string color;

        public void Start() { /* code to start the car */ }
        public void Drive() { /* code to drive the car */ }
        public void Stop() { /* code to stop the car */ }
    }
    ```

In this example, the `Car` class has properties for `make`, `model`, `year`, and `color`, and methods for `Start()`, `Drive()`, and `Stop()`. To create an object of the class, you would use the `new` keyword to instantiate it, like so:

    ```csharp
    Car myCar = new Car();
    myCar.make = "Toyota";
    myCar.model = "Camry";
    myCar.year = 2020;
    myCar.color = "Blue";
    ```

This creates an object of the `Car` class, and assigns values to the properties of the object. The object can then execute the methods of the class, like so:

    ```csharp
    myCar.Start();
    myCar.Drive();
    myCar.Stop();
    ```

In this example, the `Car` class represents an object-oriented program, it defines the properties and methods of the object, and the object represents an instance of the class, with its own unique values for the properties, and it can execute the methods.

## Draw an object oriented family (as entities, with relations)

I can describe the relationships between entities in an object-oriented family in text.

A family can be modeled as an object-oriented program using classes and objects. Here's an example of how a family can be represented:

    ```csharp
    class Person 
    {
        string name;
        int age;
        string gender;
        Person mother;
        Person father;
        List<Person> children;
        public void Greet() { /* code to greet */ }
        public void AddChild(Person child) { /* code to add a child */ }
    }
    ```

In this example, the `Person` class represents a person in the family. It has properties such as `name`, `age`, and `gender`, and it has a reference to the person's mother and father, and a list of children. The class also has a method `Greet()` and `AddChild()` which can be used to greet and add a child respectively.

Each person in the family is an instance of the `Person` class. The `mother`, `father` and `children` properties are references to other objects of the class `Person`.

It can be represented as a tree-like structure where each node is a person, and each person has a reference to their parents and children, like so:

    ```text
    +-----------------+
    |                 |
    |      John       |
    |                 |
    +-----------------+
        /           \
       /             \
      /               \
+-----------------+   +-----------------+
|                 |   |                 |
|      Mary       |   |      Peter      |
|                 |   |                 |
+-----------------+   +-----------------+
    ```

It's worth noting that this is just one way to model a family using object-oriented programming, and different models can be used depending on the specific requirements of the program.

## What does it mean that an object is immutable?

In object-oriented programming, an object is considered immutable if its state cannot be modified once it has been created. An immutable object is an object whose state is fixed and cannot be changed after it is created.

An immutable object has properties that are read-only, meaning that they can be accessed but not modified. Instead of modifying the properties of an immutable object, a new object with the modified properties is created.

For example, consider a class `Person` that has properties such as `name`, `age`, and `gender`, and a method `ChangeName()`. If the `Person` class is immutable, the `ChangeName()` method would not directly change the `name` property of the `Person` object, but it would return a new `Person` object with the updated name.

    ```csharp
    class Person
    {
        public string name { get; }
        public int age { get; }
        public string gender { get; }

        public Person(string name, int age, string gender)
        {
            this.name = name;
            this.age = age;
            this.gender = gender;
        }
        public Person ChangeName(string newName)
        {
            return new Person(newName, age, gender);
        }
    }
    ```

In this example, the `Person` class is immutable, the properties `name`, `age`, and `gender` are read-only. The `ChangeName()` method returns a new `Person` object with the updated name, but the original object is not modified.

Immutable objects have several advantages such as they are thread-safe, they are easy to reason about, they can be used as keys in a hash table, and they are useful in functional programming. However, it's worth noting that immutable objects can use more memory as each modification requires creating a new object.

## How do you make a class immutable? What do you need to watch out for?

To make a class immutable, you need to follow these steps:

1. Make all fields private and read-only
2. Use a constructor to set the initial values of the fields
3. Don't provide any setters for the fields
4. Don't provide any methods that can change the state of the object
5. For complex objects, make sure that the objects referenced by the class are also immutable
6. If you need to make changes to the object, return a new object with the desired changes

Here is an example of an immutable `Person` class:

    ```csharp
    class Person
    {
        private readonly string name;
        private readonly int age;
        private readonly string gender;

        public Person(string name, int age, string gender)
        {
            this.name = name;
            this.age = age;
            this.gender = gender;
        }

        public string Name { get { return name; } }
        public int Age { get { return age; } }
        public string Gender { get { return gender; } }

        public Person ChangeName(string newName)
        {
            return new Person(newName, age, gender);
        }
    }
    ```

In this example, the class `Person` has read-only properties `Name`, `Age`, and `Gender` and it can only be initialized by the constructor that takes in the name, age, and gender. The class also has a method `ChangeName()` that returns a new `Person` object with the updated name, but the original object is not modified.

When making a class immutable, it's important to keep in mind that

* Immutable classes are thread-safe, but if they are passed to other threads, they may be modified by those threads.
* Immutable classes are easy to reason about, but they might use more memory as each modification requires creating a new object.
* Objects referenced by the class need to be immutable as well, otherwise, their state can be modified through the class.
* If you are passing an immutable class to another class, make sure that the other class does not try to change the state of the class.
* If you need to make a lot of modifications, it might be more efficient to use a mutable class.

It is also worth noting that immutable classes are useful in functional programming, but they are not necessary for functional programming.

## How do you prevent developers from subclassing a class?

There are a few ways to prevent developers from subclassing a class:

1. Use the `sealed` keyword: In C#, you can use the `sealed` keyword to prevent a class from being subclassed. A sealed class cannot be inherited by another class.

        ```csharp
        sealed class MyClass { /* class code here */ }
        ```

2. Make the class `static`: In C#, you can make a class `static` to prevent it from being subclassed. A static class cannot be instantiated, and therefore cannot be inherited by another class.

        ```csharp
        static class MyClass { /* class code here */ }
        ```

3. Make the constructor private: In C#, you can make the constructor of a class private to prevent it from being subclassed. This means that the class cannot be instantiated, and therefore cannot be inherited by another class.

        ```csharp
        class MyClass
        {
            private MyClass() { /* constructor code here */ }
        }
        ```

4. Use an interface instead of a class: If you want to define a set of methods and properties that a class must implement, you can use an interface instead of a class. Interfaces cannot be instantiated and therefore cannot be subclassed.

        ```csharp
        interface IMyInterface { /* interface code here */ }
        ```

It's worth noting that while these techniques can prevent a class from being subclassed, they also make it harder to reuse the code, and you should be careful when using them. It's important to consider the design trade-offs and the specific requirements of the program before deciding whether or not to prevent a class from being subclassed.

## How do you prevent developers from overriding a method in a subclass?

There are a few ways to prevent developers from overriding a method in a subclass:

1. Use the `sealed` keyword: In C#, you can use the `sealed` keyword to prevent a method from being overridden in a subclass. A sealed method cannot be overridden by a subclass.

        ```csharp
        class MyClass 
        {
            public sealed void MyMethod() { /* method code here */ }
        }
        ```

2. Make the method `private` or `internal`: Making a method `private` or `internal` means that it is not accessible to subclasses. So, a subclass cannot override the method

        ```csharp
        class MyClass 
        {
            private void MyMethod() { /* method code here */ }
        }
        ```

3. Make the method `final`: In some languages like Java, making a method `final` prevents it from being overridden.

        ```csharp
        class MyClass 
        {
            public final void MyMethod() { /* method code here */ }
        }
        ```

4. Make the class `final`: Similar to making a method `final`, in some languages like Java, making a class `final` prevents any of its methods from being overridden by a subclass.

        ```csharp
        final class MyClass {
            public void MyMethod() { /* method code here */ }
        }
        ```

It's worth noting that while these techniques can prevent a method from being overridden, it also makes it harder to reuse the code, and you should be careful when using them. It's important to consider the design trade-offs and the specific requirements of the program before deciding whether or not to prevent a method from being overridden.

## How do you prevent developers from changing the value of a variable?

There are a few ways to prevent developers from changing the value of a variable:

1. Use the `readonly` keyword: In C#, you can use the `readonly` keyword to prevent a variable from being modified after it is initialized.

        ```csharp
        class MyClass 
        {
            public readonly int MyVariable = 5;
        }
        ```

2. Make the variable `private`: Making a variable `private` means that it is not accessible to external classes, so it cannot be modified by them.

        ```csharp
        class MyClass {
            private int MyVariable = 5;
        }
        ```

3. Use a property with a private setter: You can use a property to provide read-only access to a variable. By making the setter of the property private, it can only be set by the class where it is defined, and it cannot be modified by external classes.

        ```csharp
        class MyClass 
        {
            public int MyVariable { get; private set; }
            public MyClass() { MyVariable = 5; }
        }
        ```

4. Use Immutable objects: You can use immutable objects, which cannot be modified after they are created, and all their properties are read-only.

It's worth noting that while these techniques can prevent a variable from being changed, it also makes it harder to reuse the code, and you should be careful when using them. It's important to consider the design trade-offs and the specific requirements of the program before deciding whether or not to prevent a variable from being changed.