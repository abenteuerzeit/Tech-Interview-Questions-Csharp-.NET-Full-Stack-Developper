# Threads, Concurrency

## When do you need to use threads in an application?

Threads are used in an application when multiple tasks need to be performed simultaneously or in parallel. Some examples include:

Long-running tasks that would otherwise block the main thread and make the application unresponsive to the user
Performing multiple tasks at the same time, such as downloading files while also updating the user interface
Utilizing multiple cores or processors in a system to improve performance
Performing background tasks that do not need to be completed immediately, such as data processing or logging.

## What is a daemon thread?

A daemon thread is a background thread in a program that runs without preventing the program from exiting. It is typically used for tasks that do not need to complete before the program exits, such as logging or performing cleanup tasks. The JVM terminates a program when all non-daemon threads have completed, whether daemon threads are still running or not.

## What is the difference between synchronous and asynchronous execution?

Synchronous execution is when a program runs one task at a time, and each task must be completed before the next one can begin. This means that the program will wait for a task to finish before moving on to the next one. This type of execution is often used in single-threaded applications.

Asynchronous execution, on the other hand, allows a program to run multiple tasks at the same time, without waiting for one task to finish before moving on to the next one. This is often achieved through the use of multiple threads or by using non-blocking I/O operations. This type of execution is often used in multi-threaded or concurrent applications, as it allows the program to continue running other tasks while waiting for a task to complete.

## What is the difference between concurrent and parallel execution of code?

Concurrent execution refers to the concept of multiple tasks or threads being executed simultaneously, but not necessarily at the same time. They may be interleaved or intermixed, and their ordering may not be determined.

Parallel execution refers to the concept of multiple tasks or threads being executed simultaneously, with the goal of utilizing multiple CPU cores or processors at the same time. The ordering of the tasks is determined, and the tasks are executed simultaneously. It is a subset of concurrent execution where the ordering is determined.

## What is the most important problem developers encounter with a callback function?

One of the most important problems developers may encounter with a callback function is the "callback hell" or "pyramid of doom" issue. This occurs when multiple nested callback functions are used, resulting in a complex and hard-to-read code structure. This can make the code difficult to understand, maintain and debug, leading to poor performance and increased risk of errors. Additionally, it can be harder to handle errors in a nested callback structure, leading to hard-to-diagnose bugs.

## When do deadlocks occur?

Deadlocks occur when two or more processes are unable to proceed because each is waiting for the other to release a resource. They can occur in concurrent systems, such as in multi-threaded programs, where multiple threads are competing for the same resources. Deadlocks can also occur in distributed systems, where multiple processes on different machines are communicating with each other and trying to acquire shared resources. In order to avoid deadlocks, it's important to have a strategy for managing shared resources, such as using locks or semaphores, and to carefully design and implement the communication between processes or threads.
