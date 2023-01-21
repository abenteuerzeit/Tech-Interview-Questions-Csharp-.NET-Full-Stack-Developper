# Testing

## What are unit test, integration test, system test, regression test, acceptance test? What is the major difference between these?

Unit tests, integration tests, system tests, regression tests, and acceptance tests are all types of software testing that are used to evaluate the functionality, performance, and security of a software application.

Unit tests are the most granular form of testing, they test individual units of code, such as functions or methods, to ensure that they work as expected. Unit tests are typically automated and are used to ensure that small pieces of code are working correctly before they are integrated into the larger system.

Integration tests are used to test how different units of code work together. They test the interactions between different modules or components of the system to ensure that they are integrated correctly and work as expected. Integration tests are also typically automated.

System tests are used to test the entire system as a whole. They evaluate the system's performance and functionality under different scenarios and conditions, such as different load and stress conditions, to ensure that it behaves as expected.

Regression tests are used to ensure that changes made to the system do not break existing functionality. They are typically used after making changes to the system to make sure that the system still works as expected.

Acceptance tests are used to evaluate whether the system meets the requirements and expectations of the end-user. They are typically performed by the customer or by a testing team to ensure that the system is fit for its intended purpose.

The main difference between these types of testing is the level of granularity and the scope of what is being tested. Unit tests are the most granular, testing individual units of code, while system tests are the most comprehensive, testing the entire system as a whole. Integration tests, system tests, regression tests, and acceptance tests are all used to test how different parts of the system work together and to ensure that the system behaves as expected under different conditions.

## What is the difference between functional and non-functional testing? Give an example

Functional testing and non-functional testing are two different types of software testing that are used to evaluate the functionality and performance of a software application.

Functional testing is the process of testing the functional requirements of the system. It tests the system's functionality, its inputs and outputs, and its features to ensure that it works as expected. Examples of functional tests include testing that a login feature allows users to sign in with the correct credentials, testing that a shopping cart feature allows users to add and remove items, or testing that a search feature returns the correct results.

Non-functional testing, on the other hand, is the process of testing the non-functional requirements of the system. These requirements include aspects such as performance, security, scalability, and usability. Non-functional tests are used to evaluate how well the system performs under different conditions and to ensure that it meets the performance and security requirements. Examples of non-functional tests include load testing, stress testing, and security testing.

A simple example to differentiate the two is to consider an e-commerce website, functional testing will test if the website's functionality such as adding items to the cart, checking out, or changing the shipping address works as expected. While non-functional testing will test if the website can handle a large number of concurrent users, how fast the website can load, or how secure the website is from hacking attempts.

## What is code coverage? Why is it used? How can you measure?

Code coverage is a metric used to measure how much of the source code of a program is executed when a particular test suite runs. It is used to evaluate how well a test suite exercises the source code of a program. Code coverage is typically measured as a percentage, with 100% being the ideal value.

Code coverage can be measured by using a code coverage tool, such as [JaCoCo](https://www.eclemma.org/jacoco/), [Cobertura](http://cobertura.github.io/cobertura/), or [Coveralls](https://coveralls.io/). These tools can be integrated into the build process to measure the code coverage of the program every time the test suite is run.

Code coverage is a software testing technique that measures the percentage of source code that is executed during testing. It is used to determine how much of the code has been tested and to identify areas of the code that have not been tested.

Code coverage is used to ensure that all parts of the code have been tested, and that there are no untested areas. By measuring the code coverage, developers can identify which parts of the code have not been executed and focus their testing efforts on those areas. This helps to increase the quality of the code and to reduce the number of bugs and defects.

There are several ways to measure code coverage, some of the most common methods include:

Statement coverage: This measures the percentage of conditions in the code that have been evaluated to both true and false.

Statement/decision coverage: This measures the percentage of conditions and decisions in the code that have been evaluated.

Statement coverage: This measures the percentage of statements in the code that have been executed.

Branch coverage: This measures the percentage of branches in the code that have been executed.

Function coverage: This measures the percentage of functions in the code that have been executed.

There are several tools available that can be used to measure code coverage, some popular ones are:

Jacoco
Cobertura
Istanbul
OpenCover
Visual Studio Code Coverage
These tools can be used to measure code coverage for different programming languages such as Java, C#, C++, and Python. These tools integrate with the development environment and provide detailed reports on code coverage, highlighting the lines of code that have been executed and those that have not been executed.

## What does mocking mean? How would you do it 'manually' (i. e. without using any fancy framework)?

Mocking is a technique used in software testing to simulate the behavior of dependent components or services in a controlled environment. In this way, it is possible to isolate the unit under test, and test its behavior in isolation.

When mocking a component or service, a "mock" object is created that mimics the behavior of the real object. This mock object can be configured to return specific results or to throw specific exceptions. It allows the developer to test the behavior of the unit under test without having to rely on the real component or service.

There are different ways to do mocking "manually" without using any framework, some of the most common methods include:

Creating a mock class: Create a new class that implements the same interface as the class that you want to mock. This class can be configured to return specific results or to throw specific exceptions.

Using a stub: A stub is an object that has the same interface as the object that you want to mock, but with hard-coded return values. This can be useful when you want to test a specific behavior of the unit under test.

Using a spy: A spy is an object that records method calls and returns a default value. This can be useful when you want to check if a specific method was called on the mock object.

Using a mock object library: There are several libraries available that provide the ability to create mock objects, such as the built-in 'unittest.mock' library in Python. These libraries can simplify the process of creating mock objects and provide additional functionality such as verifying method calls and argument matching.

In all of these methods, the goal is to isolate the unit under test and control the behavior of the dependent components or services, in order to test the unit in isolation and make sure that it is working as expected.

## What is the difference between stub and mock?

A stub is an object that is used to simulate the behavior of a real object. It is used to isolate the unit under test and to control the behavior of the dependent components or services. A stub is typically used to return a specific result or to throw a specific exception.

A mock is an object that is used to simulate the behavior of a real object. It is used to isolate the unit under test and to control the behavior of the dependent components or services. A mock is typically used to verify that a method was called on the mock object, and to verify the arguments that were passed to the method.

The main difference between a stub and a mock is that a stub is used to return a specific result or to throw a specific exception, while a mock is used to verify that a method was called on the mock object, and to verify the arguments that were passed to the method.

## What is a test case? What is an assertion? Provide examples

A test case is a set of conditions or variables that are used to determine whether a system under test works as expected. It is used to define the input values, execution conditions, and expected results for a test. A test case typically consists of a test name, a description of the test, the input values, the execution conditions, and the expected results.

An assertion is a statement that verifies the expected result of a test. It is used to verify that the actual result matches the expected result. Assertions are typically used in unit tests to verify that the unit under test is working as expected.

Here's an example of a test case and an assertion in C# using the xUnit framework:

    [Fact]
    public void Test_Addition()
    {
        // Arrange 
        int a = 2;
        int b = 3;
        int expected = 5;
        
        // Act
        int result = a + b;
        
        // Assert
        Assert.Equal(expected, result);
    }

In this example, the test case is testing the addition of two integers, a and b. The test case includes the inputs (a and b), the expected output (5), and the steps to be executed (the addition of a and b). The assertion is in the last line, where we are checking whether the result of the addition (result) is equal to the expected output (expected), using the Assert.Equal method.

Another example in python using the unittest library

    import unittest

    def add(x, y):
        return x + y

    class TestAdd(unittest.TestCase):

        def test_add(self):
            # Test case
            result = add(10, 5)
            
            # Assertion
            self.assertEqual(result, 15)

In this example, the test case is testing the addition of two integers, x and y, using the add function. The test case includes the inputs (x, y) and the steps to be executed (the add function). The assertion is in the last line, where we are checking whether the result of the addition (result) is equal to the expected output (15), using the assertEqual method.

In both examples, the test case is providing the inputs, and the assertion is checking the output, and if the output matches the expected output, the test case passes otherwise it fails.

## What is TDD? What are the benefits?

Test-driven development (TDD) is a software development methodology in which developers write automated tests for a new feature before they write the actual code for that feature. The tests are written in such a way that they fail initially, and then the developers write the code to make the tests pass. This approach helps to ensure that the code is testable, maintainable, and that it meets the requirements.

Here is the general flow of TDD:

1. Write a test for a new feature
2. Run the test and see it fail
3. Write the code for the feature
4. Run the test again and see it pass
5. Refactor the code, as needed
6. Repeat the process

The main benefits of TDD are:

- It ensures that all the code is covered by tests and that new features are thoroughly tested before being released.
- It encourages simple, clean, and maintainable code because the tests act as a specification for the code.
- It helps to find bugs early in the development process, which makes them cheaper and easier to fix.
- It helps to create a robust and reliable codebase by testing edge cases and different scenarios.
- It promotes a design-first approach, as developers have to think about the design of their code before writing it.
- It helps to build a culture of quality and continuous improvement.

TDD is not a silver bullet and it may not be suitable for all types of projects, but it is a powerful technique that helps to increase the quality of the code and to reduce the number of bugs and defects. It is a practice that when implemented consistently it can lead to better code, fewer bugs, and more efficient development.

## What is BDD? What are the benefits?

Behavior-Driven Development (BDD) is a software development methodology that emphasizes the collaboration between developers, quality assurance (QA) engineers, and business stakeholders in order to deliver software that meets the business needs. BDD is an extension of TDD (Test-Driven Development) and it uses natural language constructs to express the behavior of the system.

BDD is based on the idea that by describing the behavior of the system in a natural language format, it is possible to create a shared understanding of the requirements among all stakeholders. This shared understanding helps to ensure that the system meets the business needs and that it behaves as expected.

Here is the general flow of BDD:

1. Write a user story in a natural language format that describes the behavior of the system.
2. Write acceptance criteria that define the expected behavior of the system
3. Write automated tests that check if the system behaves as expected
4. Write the code that makes the tests pass
5. Refactor the code, as needed
6. Repeat the process

The main benefits of BDD are:

- It promotes collaboration between all stakeholders and helps to create a shared understanding of the requirements.
- It helps to deliver software that meets the business needs.
- It helps to find and fix defects early in the development process.
- It helps to improve communication between developers, QA engineers, and business stakeholders.
- It helps to create a living documentation of the system that is always up-to-date and easy to understand.
- It helps to create a culture of quality and continuous improvement.

BDD is not a replacement of TDD but an extension of it, it encourages the use of natural language constructs to express the behavior of the system which makes it more accessible to non-technical stakeholders, it focuses more on the business value, and user-centered approach. Like TDD, BDD is not a silver bullet and it may not be suitable for all types of projects, but it is a powerful technique that helps to increase the quality of the code and to reduce the number of bugs and defects. It helps to create a shared understanding of the requirements and to deliver software that meets the business needs.

## What are the unit testing best practices? (Eg. how many assertion should a test case contain?)

Unit testing is a technique used to test individual units of code, such as methods or functions, to ensure that they behave as expected. There are several best practices that can help to improve the quality of unit tests and make them more effective. Some of the most important unit testing best practices include:

One Assert per Test: Each test should check one specific behavior or condition, and it should contain only one assertion. This makes the test simple and easy to understand, and it helps to identify the cause of a failure quickly.

Keep tests independent: Tests should be independent of each other and should not rely on the state of the system or the order in which they are executed. This makes the tests more reliable and less prone to errors.

Use test-specific data: Tests should use test-specific data that is not shared with other tests. This helps to keep the tests independent and ensures that they are not affected by changes in the data.

Use descriptive test names: Tests should have descriptive and meaningful names that clearly indicate what they are testing. This makes it easy to understand the purpose of the test and it helps to identify the cause of a failure.

Avoid testing private methods: Private methods are implementation details and they should not be tested directly. Tests should focus on the public interface of the class or module, and they should test the behavior of the system as a whole.

Keep tests small and focused: Tests should be small and focused on a specific behavior or condition. This makes the tests easy to understand and maintain, and it helps to identify the cause of a failure quickly.

Use automated testing: Automated testing helps to ensure that tests are executed consistently and that the results are reliable. It also helps to reduce the time and effort required to run tests manually.

Use a test runner: A test runner is a tool that helps to run, execute, and organize the tests. It helps to automate the testing process, and it makes it easy to run and organize the tests.

Use test-driven development (TDD): TDD is a methodology that helps to ensure that the code is thoroughly tested before it is released. It encourages developers to think about the design of their code before writing it, and it helps to increase the quality of the code.

Continuously refactor: Continuously refactor the code and the tests as the system changes. This helps to ensure that the code is maintainable and easy to understand.

By following these best practices, you can write better, more effective unit tests that help to ensure that the code is correct, reliable, and easy to understand.
