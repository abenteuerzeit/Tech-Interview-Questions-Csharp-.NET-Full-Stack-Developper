# Databases

## How can you connect your application to a database server? What are the possible ways?

There are several ways to connect an application to a database server, depending on the programming language and the type of database used. Some of the most common ways include:

ADO.NET: ADO.NET (ActiveX Data Objects .NET) is a data access technology that is built into the .NET Framework. It provides a set of classes that can be used to connect to a variety of data sources, including relational databases, XML files, and more. ADO.NET supports a variety of data providers, such as SQL Server, Oracle, and MySQL, and it can be used to perform a wide range of data-related tasks, including connecting to a database, executing queries, and retrieving data.

ORM (Object-Relational Mapping): ORM (Object-Relational Mapping) is a technique that allows developers to interact with a database using an object-oriented model. An ORM tool can be used to automatically generate the code required to connect to the database and to perform CRUD (Create, Read, Update, Delete) operations on the data. ORM frameworks, such as Entity Framework and NHibernate, are popular choices for .NET and Java development respectively.

JDBC (Java Database Connectivity): JDBC (Java Database Connectivity) is a Java-based data access technology that allows Java applications to connect to a wide variety of relational databases. JDBC provides a set of classes and interfaces that can be used to connect to a database, execute queries, and retrieve data. JDBC supports a variety of data providers, such as SQL Server, Oracle, and MySQL, and it is a popular choice for Java development.

ODBC (Open Database Connectivity): ODBC (Open Database Connectivity) is a widely supported open standard for connecting to relational databases. It provides a common interface for connecting to different databases, and it supports a variety of data providers, such as SQL Server, Oracle, and MySQL. ODBC can be used to connect to databases from a variety of programming languages, including C, C++, and C#.

PHP Data Objects (PDO): PDO (PHP Data Objects) is a data access technology that is built into PHP. It provides a set of classes that can be used to connect to a variety of data sources, including relational databases, and perform a wide range of data-related tasks, including connecting to a database, executing queries, and retrieving data. PDO supports a variety of data providers, such as SQL Server, Oracle, and MySQL, and it is a popular choice for PHP development.

NoSQL databases: NoSQL databases such as MongoDB, Cassandra, and Redis have their own libraries, driver or API to connect to them, it's not the same as relational databases but the concept of connecting to them is the same.

These are just some examples of the ways that an application can connect to a database server, and the specific approach will depend on the programming language, the type of database, and the needs of the application.

## When do you use the DISTINCT keyword in SQL?

The `DISTINCT` keyword in SQL is used to filter out duplicate rows from the result set of a query. When the `DISTINCT` keyword is used, the query will return only unique rows based on the selected columns.

The `DISTINCT` keyword is used in the `SELECT` statement, immediately after the `SELECT` keyword. Here is an example of how to use the `DISTINCT` keyword in a SQL query:

    SELECT DISTINCT column1, column2
    FROM table_name;

This query will return all unique rows from the "table_name" based on the values in "column1" and "column2".

It's important to note that DISTINCT only considers the values in the columns specified after the SELECT keyword, it doesn't take into account the entire row. You can also use DISTINCT with multiple columns, in this case, the query will return only unique combinations of values in all specified columns.

In addition, DISTINCT can be used with aggregate functions such as COUNT, SUM, AVG, etc. In that case, it will return only unique values after applying the aggregate function. For example:

    SELECT COUNT(DISTINCT column1) FROM table_name;

This query will return the number of unique values in column1.

In summary, the DISTINCT keyword is useful when you want to filter out duplicate rows from the result set of a query and only return unique rows based on the specified columns.

## What are aggregate functions in SQL? Give 3 examples

Aggregate functions in SQL are functions that perform a calculation on a set of values and return a single value. They are used to summarize and analyze data in a database. Some common examples of aggregate functions in SQL include:

SUM: This function returns the sum of all values in a specified column. For example, the following query returns the total salary of all employees in a table called "employees":

    SELECT SUM(salary) FROM employees;

COUNT: This function returns the number of rows in a specified table. For example, the following query returns the number of employees in the "employees" table:

    SELECT COUNT(*) FROM employees;

AVG: This function returns the average value of a specified column. For example, the following query returns the average salary of all employees in the "employees" table:

    SELECT AVG(salary) FROM employees;

MIN: This function returns the smallest value in a specified column. For example, the following query returns the minimum salary of all employees in the "employees" table:

    SELECT MIN(salary) FROM employees;

MAX: This function returns the largest value in a specified column. For example, the following query returns the maximum salary of all employees in the "employees" table:

    SELECT MAX(salary) FROM employees;

GROUPBY: This function groups rows that have the same values into summary rows, like "find the number of employees in each department". For example, the following query returns the number of employees in each department:

    SELECT department, COUNT(*) FROM employees GROUP BY department;

HAVING: This function is used with the GROUP BY clause to filter groups based on a condition. For example, the following query returns the number of employees in each department that have a salary greater than 1000:

    SELECT department, COUNT(*) FROM employees GROUP BY department HAVING SUM(salary) > 1000;

Some databases also provide more advanced aggregate functions such as MEDIAN, MODE and STANDARD DEVIATION.

It's important to note that aggregate functions are typically used in combination with a GROUP BY clause, which allows you to group the results of a query by one or more columns. This allows you to perform calculations on specific subsets of data, rather than on the entire table.

## What do you know about database normalization?

Database normalization is the process of organizing data in a relational database so that it follows a set of rules and guidelines known as normal forms. The goal of normalization is to minimize data redundancy and improve data integrity by ensuring that data is stored in a consistent and logical manner.

There are several normal forms that a database can follow, and each one builds upon the rules of the previous one. The most commonly used normal forms are:

First Normal Form (1NF) - A database is in 1NF if all data is atomic, meaning that each cell contains only one value. Additionally, the table must have a primary key.

Second Normal Form (2NF) - A database is in 2NF if it is already in 1NF and no non-key column is dependent on any other non-key columns. This means that each non-key column must depend on the primary key.

Third Normal Form (3NF) - A database is in 3NF if it is already in 2NF and there are no transitive dependencies between columns. This means that no non-key column should depend on another non-key column.

Boyce-Codd Normal Form (BCNF) - A database is in BCNF if it is in 3NF and every determinant is a candidate key.

Fourth Normal Form (4NF) - A database is in 4NF if it is in BCNF and there are no multi-valued dependencies.

Fifth Normal Form (5NF) - A database is in 5NF if it is in 4NF and there are no join dependencies.

Normalizing a database is an iterative process, and it's not always necessary to reach the highest normal form. The appropriate normal form for a particular database will depend on the specific requirements of the application, such as the types of queries that will be executed against the data.

Normalization can help to improve the performance and maintainability of a database by reducing the amount of duplicate data and ensuring that data is stored in a consistent and logical manner. However, normalization can also make it more difficult to perform certain types of queries, such as those that require data from multiple tables to be joined together. In such cases, denormalization can be used to improve query performance.

## What kind of JOIN types do you know in SQL? Could you give examples?

In SQL, a JOIN operation is used to combine rows from two or more tables based on a related column between them. The result is a new table that contains all columns from the joined tables, with rows that match the join condition. There are several types of JOINs in SQL, and they are used in different situations depending on the specific needs of a query. Some of the most common types of JOINs include:

INNER JOIN: An INNER JOIN returns only the rows that have matching values in both tables. For example, the following query returns all rows from the "employees" table where the "department_id" column matches a value in the "departments" table:

    SELECT *
    FROM employees
    INNER JOIN departments
    ON employees.department_id = departments.department_id;

LEFT JOIN (or LEFT OUTER JOIN): A LEFT JOIN returns all rows from the left table (the first table in the query), and the matching rows from the right table. If there is no match, NULL values will be returned for the right table's columns. For example, the following query returns all employees and the departments they belong to, even if an employee doesn't belong to any department:

    SELECT *
    FROM employees
    LEFT JOIN departments
    ON employees.department_id = departments.department_id;

RIGHT JOIN (or RIGHT OUTER JOIN): A RIGHT JOIN returns all rows from the right table (the second table in the query), and the matching rows from the left table. If there is no match, NULL values will be returned for the left table's columns. It's the same as LEFT JOIN but swapping the tables.

FULL JOIN (or FULL OUTER JOIN): A FULL JOIN returns all rows from both tables, whether or not there is a match. If there is no match, NULL values will be returned for the non-matching columns. The following query returns all departments and the employees belong to it, even if a department doesn't have any employee:

    SELECT *
    FROM employees
    FULL JOIN departments
    ON employees.department_id = departments.department_id;

These are some of the most common types of JOINs in SQL. Each one has its own specific use case, and the appropriate type of JOIN will depend on the specific requirements of a query.

## What are database transactions? When are they used?

A database transaction is a sequence of one or more SQL statements that are executed together as a single, atomic unit of work. The idea behind transactions is that the database should remain in a consistent state, regardless of any errors or failures that may occur during the execution of the statements.

Transactions are used to ensure that a group of related statements are executed together, so that either all of them are executed successfully or none of them are executed at all. This is known as the ACID properties (Atomicity, Consistency, Isolation and Durability) which are the characteristics that define a transaction.

Some examples of when transactions are used include:

When transferring money between bank accounts, a transaction is used to ensure that the account balances are updated correctly and that the funds are transferred atomically, so that either both accounts are updated or neither are.
When updating a customer's order, a transaction is used to ensure that the order is updated and the inventory is reduced atomically, so that the customer's order is not fulfilled with insufficient inventory.
There are several SQL commands that are used to control transactions, such as:

BEGIN TRANSACTION: starts a new transaction.
COMMIT: commits the current transaction and makes its changes permanent.
ROLLBACK: rolls back the current transaction and undoes any changes that were made.
It's important to note that a database management system will automatically handle the start and end of a transaction, this means that you don't need to explicitly start a transaction when you execute a query, but you can use these commands to manage the transaction if you need to.

In summary, database transactions are used to ensure that a group of related statements are executed together as a single, atomic unit of work, so that the database remains in a consistent state regardless of any errors or failures that may occur during the execution of the statements.

## What is a dead-lock in databases? How is it avoided?

A deadlock in a database occurs when two or more transactions are waiting for each other to release a lock on a resource before they can proceed with their own operations. This results in a situation where none of the transactions can proceed, and the database becomes "deadlocked."

For example, consider two transactions, T1 and T2, that are executing simultaneously. T1 has acquired a lock on resource A and is waiting for a lock on resource B. T2 has acquired a lock on resource B and is waiting for a lock on resource A. Now both transactions are waiting for each other to release the lock, but neither can proceed. This results in a deadlock.

There are several ways to avoid deadlocks in a database:

Lock Timeout: A lock timeout is a setting that allows a transaction to wait for a specified amount of time for a lock to be released before giving up and rolling back. This ensures that a transaction does not wait indefinitely for a lock.

Lock Ordering: By acquiring locks in a consistent order, it can prevent the possibility of a deadlock. If a transaction always acquires locks in the same order, it will never be waiting for a lock that another transaction holds.

Deadlock Detection and Resolution: Some database management systems (DBMS) include built-in mechanisms for detecting and resolving deadlocks. When a deadlock is detected, the DBMS will automatically choose one of the transactions to rollback, and release its locks, allowing the other transaction to proceed.

Read-Only transactions: By using read-only transactions, you can avoid the need for locks altogether, which eliminates the possibility of deadlocks.

Optimizing Queries: Optimizing queries can help to reduce the chances of a deadlock by reducing the amount of time a transaction holds a lock, which reduces the chances of another transaction needing the same lock.

It's important to note that deadlocks are a normal part of any database system and can occur in any system that uses locks, but by implementing the above-mentioned methods, it can be reduced and handled effectively.

## What is a two-phase commit? Write an example of how to use it

A two-phase commit (2PC) is a protocol that ensures that a distributed transaction is committed across multiple systems in a consistent and reliable way. A distributed transaction is a transaction that spans multiple systems, such as multiple databases or multiple services. The 2PC protocol is used to ensure that all systems involved in the transaction either commit or rollback the transaction together, so that the data remains consistent across all systems.

The two-phase commit protocol consists of two phases: the prepare phase and the commit phase.

1. Prepare Phase: In this phase, each system involved in the transaction sends a "prepare" message to a coordinator (often called a Transaction Manager), indicating that it is ready to commit the transaction. The coordinator then waits for a response from all systems before proceeding to the next phase.
2. Commit Phase: If all systems have responded positively to the prepare message, the coordinator sends a "commit" message to all systems, indicating that they should commit the transaction. If any system responds negatively, the coordinator sends a "rollback" message to all systems, indicating that they should rollback the transaction.

Here is an example of how 2PC works:

1. A client initiates a transaction, which includes updates to a database on System A and a message queue on System B.
2. The client sends a "prepare" message to the coordinator, which forwards the message to System A and System B.
3. System A and System B respond positively to the prepare message, indicating that they are ready to commit the transaction.
4. The coordinator receives the positive responses from System A and System B and sends a "commit" message to both systems.
5. System A and System B commit the transaction.

It's important to note that using 2PC can have a performance overhead, as all systems need to participate in the protocol, and it can also lead to increased complexity in terms of handling failures and errors. Additionally, in some systems, it's not necessary to implement 2PC, as the systems can automatically handle the consistency and atomicity of the transaction.

## What kind of database relations do you know? How are they defined?

There are several types of database relationships that can be defined between tables in a relational database:

One-to-One (1:1) Relationship: This type of relationship exists when one record in a table is related to only one record in another table. For example, a person can have only one passport, and a passport can belong to only one person.

One-to-Many (1:N) Relationship: This type of relationship exists when one record in a table is related to multiple records in another table. For example, a department can have many employees, but an employee can only belong to one department.

Many-to-Many (N:M) Relationship: This type of relationship exists when multiple records in a table are related to multiple records in another table. For example, a student can take multiple courses and a course can have multiple students. To resolve this kind of relationship, an additional table is created called a junction table which contains the foreign keys from both tables.

Self-referencing Relationship: This type of relationship exists when a table has a relationship with itself. For example, an employee table can have a manager_id column, which references the id column of the same table.

These relationships are defined by creating constraints on the database tables, such as foreign keys and unique keys. In most relational databases, these constraints are enforced by the database management system, which ensures that the data remains consistent and referentially intact.

For example, in SQL, a one-to-many relationship can be defined by adding a foreign key constraint on the "many" side table, which references the primary key of the "one" side table. This can be done using the following SQL statement:

    ALTER TABLE orders 
    ADD FOREIGN KEY (customer_id) REFERENCES customers(id);

In this example, the 'orders' table has a foreign key 'customer_id' which references the 'id' column of the 'customers' table, thus establishing a one-to-many relationship between the two tables.

## What is an ORM? What are the benefits, when is it used?

An ORM (Object-Relational Mapping) is a technique that allows developers to interact with a relational database using an object-oriented programming language. It maps the objects in the programming language to the tables in the database, allowing developers to work with the data in a more intuitive and natural way.

The benefits of using an ORM include:

Abstraction: ORM provides an abstraction layer between the application and the database, allowing developers to work with the data in a more intuitive and natural way, without having to write complex SQL queries.

Productivity: ORM can greatly increase developer productivity by reducing the amount of code that needs to be written, and by automating many of the repetitive tasks associated with database programming.

Portability: ORM allows developers to write code that is independent of the underlying database. This means that the same code can be used to work with different databases, such as SQL Server, MySQL, Oracle, and PostgreSQL.

Performance: ORM can improve performance by caching data, and by providing a more efficient way of querying the database.

Security: ORM can improve security by preventing SQL injection attacks by automatically escaping any user input.

It's important to note that ORM may not be the best fit for all projects, it's recommended to use ORM when:

you have a complex data model that changes frequently
you want to reduce the amount of code that needs to be written
you want to improve the performance of your application
you want to improve the security of your application
On the other hand, it's not recommended to use ORM when:

your application has simple data model
you have a high-performance requirement
you want to have more control over the SQL generated
you have specific requirements that the ORM does not support
Overall, ORM can be a powerful tool for simplifying database development, but it's important to understand its limitations and when it's appropriate to use it.

## What is a trigger? Provide an example of using it

A trigger is a set of instructions that are automatically executed by the database management system (DBMS) in response to specific events, such as an INSERT, UPDATE, or DELETE statement. Triggers are used to enforce business rules, maintain data integrity, and perform other tasks that are not easily achieved through standard SQL statements.

For example, consider a scenario where you want to automatically update the "last_updated" column in a "customers" table every time a record is updated. You could use a trigger to accomplish this task.

Here is an example of a trigger written in SQL:

    CREATE TRIGGER update_customer_last_update
    AFTER UPDATE ON customers
    FOR EACH ROW
    BEGIN
        UPDATE customers
        SET last_updated = NOW()
        WHERE customer_id = NEW.customer_id;
    END;

In this example, the trigger is defined to be executed after an update statement on the "customers" table. The trigger updates the "last_updated" column with the current timestamp (NOW()) for the customer that was updated.

The trigger is executed automatically by the DBMS whenever an update statement is issued on the "customers" table, ensuring that the "last_updated" column is always up-to-date.

It's important to note that triggers can also be defined to be executed before an event, and on different events such as insert and delete. Additionally, triggers can also be defined to be executed on multiple tables at once, and it can have multiple statements inside the trigger.

## What are indexes in a database?

Indexes are a database feature that allows for faster retrieval of data from a table. They are similar to the index in a book, which allows you to quickly find information by looking up the page number instead of scanning the entire book. In a database, an index is a data structure that allows for quick lookup of rows in a table based on the values in one or more columns.

When you create an index on a table, the DBMS builds a separate data structure that contains a copy of the values from the indexed columns, along with a reference to the location of the corresponding rows in the table. This data structure is then organized in a way that allows for fast lookups based on the indexed column values, usually through a search tree data structure.

There are different types of indexes, such as clustered and non-clustered indexes, unique and non-unique indexes, and full-text indexes.

Clustered indexes determine the physical order of data in a table, and a table can have only one clustered index. A non-clustered index does not determine the physical order of the data in a table, but instead provides a fast way to look up the location of a row based on the indexed column values. A table can have multiple non-clustered indexes.

Unique indexes ensure that no duplicate values are allowed in the indexed columns, while non-unique indexes allow duplicate values.

Full-text indexes are used to improve the performance of full-text searches on large character-based columns, such as varchar or text.

Indexes can greatly improve the performance of SELECT, UPDATE, and DELETE statements, but they can also slow down INSERT and UPDATE statements, as the DBMS needs to update the index data structures whenever a new row is added or an existing row is modified. Therefore it's important to use indexes judiciously and to monitor their performance.

## Explain the difference between WHERE and HAVING

The WHERE and HAVING clauses are used in SQL to filter the rows returned by a SELECT statement.

The WHERE clause is used to filter the rows before the groups are created, it specifies a condition that must be met by the rows in the table before they are included in the result set. The WHERE clause is used in the SELECT, UPDATE, DELETE statement and it can be used to filter on any column in the table.

For example, the following SQL statement uses a WHERE clause to filter the rows in the "employees" table based on the "salary" column:

    SELECT first_name, last_name, salary
    FROM employees
    WHERE salary > 50000;

On the other hand, the HAVING clause is used to filter the groups based on the aggregate values, it specifies a condition that must be met by the groups after they have been created by the GROUP BY clause. The HAVING clause is used in the SELECT statement, and it can be used to filter on any aggregate function such as COUNT, SUM, AVG, MAX and MIN.

For example, the following SQL statement uses a HAVING clause to filter the groups in the "employees" table based on the count of employees by department:

    SELECT department, COUNT(*) AS employee_count
    FROM employees
    GROUP BY department
    HAVING COUNT(*) > 5;

In this example, the SELECT statement groups the rows in the "employees" table by the "department" column and calculates the number of employees in each department using the COUNT() aggregate function. The HAVING clause filters the groups based on the number of employees, only returning the departments that have more than 5 employees.

It's worth noting that, if you don't use any aggregate function in your SELECT statement, the HAVING clause will have no effect.

## What is SQL Injection?

SQL injection is a type of cyber attack that targets SQL databases. It is a method of injecting malicious code into a SQL statement in order to alter the intended meaning of the statement and gain unauthorized access to the database. The attacker can use this access to view, modify, or delete sensitive data, such as personal information, financial data, or other confidential information.

SQL injection attacks can happen when an attacker is able to insert malicious code into a SQL statement through an application's user input. The attacker can then use this input to change the meaning of the SQL statement and gain access to the database. For example, if an application's user input is not properly sanitized, an attacker could enter a malicious value for a login form that results in a SQL statement that grants the attacker access to the application's database.

There are different methods to perform SQL injection, the most common are:

- Tautologies: when the attacker craft a query that always evaluates to true
- Union-based: when the attacker uses the UNION keyword to combine the results of two SELECT statement
- Error-based: when the attacker uses error messages to reveal information about the database schema
- Blind: when the attacker doesn't get any direct feedback but can infer information by making the application behave differently.

Preventing SQL injection attacks is critical to ensure the security of your data and it can be achieved through several methods, such as:

- Input validation: validate and sanitize any user input to ensure that it is safe to use in a SQL statement.
- Prepared statements: use prepared statements with parameterized queries to separate data from SQL code, which makes it more difficult for attackers to inject malicious code.
- Stored procedures: use stored procedures that are precompiled and stored on the database server, which can help to prevent SQL injection attacks.
- Use of ORM (Object-Relational Mapping) frameworks, they can provide protection against SQL injection by automatically escaping any user input.

It's important to keep in mind that SQL injection is a serious security vulnerability, and it's essential to have a comprehensive approach to securing your database and applications.
