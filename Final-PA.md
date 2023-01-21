# PA questions for the advanced ASP.NET C# module

## LINQ

- used on collections, lists `IEnumerable`, `IQueryable`, `ICollection`

### Data Retrieval

Descirption of the methods:

`Where` returns a collection of elements that satisfy a condition, we use when we need more than one element and we want to filter them by some condition.

`Single` returns a single element, throws an exception if there are more than one element, used when we expect exactly one element.

`SingleOrDefault` returns a single element, if there is no element returns a default value, for example null for reference types or 0 for integer types.

`First` returns the first element of a collection, if there is no element returns a default value, for example null for reference types or 0 for integer types.

`FirstOrDefault` returns the first element of a collection, if there is no element returns a default value, for example null for reference types or 0 for integer types.

`Last` returns the last element of a collection, if there is no element returns a default value, for example null for reference types or 0 for integer types.

### Data projection ( converting a set into some other set)

`Select` goes through all the elements of a given collection, transforms each element of the sequence into a new form. It is used when we want to transform a collection into another collection.

`SelectMany` can turn a two-dimensional array into a single sequence of values

### Anonymous types

`Select` can be used to create anonymous types, which are types that are defined on the fly, without creating a class. They are useful when we want to return a collection of objects that have only a few properties.

#### Data division

`Skip` returns a collection of elements that are skipped from the beginning of the collection

`Take` returns a collection of elements that are taken from the beginning of the collection

`SkipWhile` returns a collection of elements that are skipped from the beginning of the collection, until the condition is met

`TakeWhile` returns a collection of elements that are taken from the beginning of the collection, until the condition is met

#### Sorting data

`OrderBy` returns a collection of elements that are sorted in ascending order

`OrderByDescending` returns a collection of elements that are sorted in descending order

`ThenBy` returns a collection of elements that are sorted in ascending order, after the first sorting

`ThenByDescending` returns a collection of elements that are sorted in descending order, after the first sorting

### Operations on sets

`Distinct` returns a collection of unique elements

`Union` returns a collection of unique elements from two collections

`Intersect` returns a collection of elements that are common in two collections

`Except` returns a collection of elements that are in the first collection but not in the second collection

#### Data Verification

`All` returns true if all elements satisfy a condition

`Any` returns true if any element satisfies a condition

### Processing data

**Eager loading** all data is automatically processed right away and some kind of structure is created from it.

**Lazy loading** processes only what we need, what we are currently using.

## Interface vs. Abstract Class

### Interface

- A class can implement one or multiple interfaces
- Only declaration of components, no implementation
- Interface components cannot contain access modifiers (public default)
- An interface can only inherit from other interfaces
- Cannot declare fields
- Cannot have a constructor

### Abstract Class

- A class can only inherit from one abstract class
- Declaration of components as well as their full implementation, in a derived class must be overridden, override
- Constituents of an abstract class can be marked with access attributes (private, protected, etc.)
- Abstract class can inherit from abstract classes, interfaces and even ordinary classes
- We can declare fields
- We can provide implementations of the default constructor

### Static class

We cannot create an instance of a static class.

- contains only static members
- is `sealed`
- cannot contain a constructor instance
- cannot be inherited
- cannot inherit from any class other than `Object`

**Static Constructor** - no access modifiers or parameters, only one in the class, cannot be inherited or overloaded, is called automatically, initializes the class, calls itself before other constructors of the class, is used, for example, to write log file entries in the class

### Misc

**Property** - a flexible mechanism, to read, write, calculate the value of private fields, field extension, include methods accesory, get and set, which are used to return and to write a new value.

You can choose to `override` a property, thanks to the set accesors, or make the property `virtual`, and in the derived class use the keyword `override`

**Middleware** – used in the starting class of the application.

**Program.cs** - part of an application code that is used to capture errors globally(app.UseExceptionHandler), e.g. We can use a middleware component to authenticate the user, and to serve static files such as JavaScript, CSS, images, etc.(app.UseStaticFiles), to redirect HTTP requests to HTTPS(app.UseHttpsRedirection), to route requests (app.UseRouting).

**Immutable types** – a type of object whose data is immutable after its creation. It can be `readonly` or `const`. It creates a new place in memory and stores its modified value there. E.g. strings, creates a new memory space instead of working on an existing one. Reduces application performance.
`readonly` allows modification of a field in the constructor, `const` does not!

**Mutable types** - a type of object whose members (properties, data, fields) can be modified after its creation. The value is changed in memory itself. StringBuilder, uses the same memory location and adds, modifies the contents of a single instance. This does not reduce the performance of the application

**Operand `==`** - compares different types, can be int with string compared and will return true

**Operand `===`** - strict equality, compares two operands and returns false if they are of different type

A **callback** function, a function that we pass as an argument to the function that we call, such as `AddEventListener`

**Promise** a container for the value that will be returned, we have sent some request and are waiting for it to be served. We wait for it to be returned, we don't know what the value will be, and when we get it, we decide what to do with it next.

`undefined` - undefined state, nothing is assigned to this variable, we did not specify what it is, it does not exist, unassigned area in memory

`null` defined state, the variable is empty in value

**serialization** - converting object data into text (JSON, XML), saving to a database or sending to another system

**Deserialization** - the inverse of serialization, converting text into an object

## GIT

It is a distributed version control system, it means that every developer has a full copy of all history of the project, and can work offline. It is a free and open source software.

`git init` creates a new Git repository. It adds a hidden subdirectory named .git that contains all of your necessary repository files – a Git repository skeleton. It is a local repository, it is not connected to any server.

`git clone` creates a local copy of a project that already exists remotely. The clone includes all the project’s files, history, and branches.

`git checkout` is used to switch from one branch to another. It is also used to tell Git to start tracking changes made to a file or set of files, or to restore the working tree files to a previous state.

`git status` shows the working tree status. It lists which files are staged, unstaged, and untracked.
Git add – It adds a change in the working directory to the staging area. It stages a new file, a modified file, or deleted file.

`git commit` records or snapshots the file permanently in the version history. It is like when you save a file, except with Git, every time you save it creates a unique ID (a.k.a. the "SHA" or "hash") that allows you to keep record of what changes were made when and by who. It is like a "save as" in other systems.

`git push` updates remote refs using local refs, while sending objects necessary to complete the given refs. It is used to upload local repository content to a remote repository.

`git pull` fetches from and integrates with another repository or a local branch. It is used to fetch and download content from a remote repository and immediately update the local repository to match that content.

`git fetch` downloads objects and refs from another repository. It is used to transfer commits, files, and refs from one repository to another repository.

`git merge` merges one or more branches into your current branch and automatically creates a new commit if there are no conflicts. It is used to join two or more development histories together.

`git rebase` takes all the changes that were committed on one branch and "replays" them on another branch. It is used to reapply commits on top of another base tip.
