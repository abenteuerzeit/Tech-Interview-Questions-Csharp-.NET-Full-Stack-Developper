# Algorithms, Pseudo code

## Fibonacci sequences.

1. Write a method(or pseudo code), that generates the Fibonacci sequences.

Here is a method in C# that generates a Fibonacci sequence of a given length:

    class FibonacciGenerator 
    {
        public static IEnumerable<int> GenerateSequence(int length) {
            int first = 0;
            int second = 1;
            yield return first; // yield the first number
            yield return second; // yield the second number

            for (int i = 2; i < length; i++) {
                int next = first + second;
                yield return next; // yield the next number
                first = second;
                second = next;
            }
        }
    }

You can use this method like this:

    foreach(int n in FibonacciGenerator.GenerateSequence(10)){
        Console.WriteLine(n);
    }

This method uses the C# yield keyword, which allows the method to return a sequence of values without the need to store the entire sequence in memory. The method takes an integer parameter length and returns an IEnumerable<int> that allows to iterate over the generated sequence. The method starts by initializing two variables first and second to 0 and 1 respectively. Then it uses a for loop that starts at the third element, i.e 2, and ends at the given length, adding the two previous numbers and returning the sum using the yield keyword. The value of the two previous numbers are then updated with the sum, and the loop continues until it reaches the given length.

Here is a pseudocode that does the same:

    function GenerateFibonacciSequence(length:int): List[int]
        first = 0
        second = 1
        fibonacci_sequence = []
        fibonacci_sequence.append(first)
        fibonacci_sequence.append(second)
        for i = 2 to length
            next_number = first + second
            fibonacci_sequence.append(next_number)
            first = second
            second = next_number
        return fibonacci_sequence

This pseudocode uses a function GenerateFibonacciSequence that takes in a length as an input and returns a list of integers. It starts by initializing two variables first and second to 0 and 1 respectively. Then it uses a for loop that starts at the third element, i.e 2, and ends at the given length, adding the two previous numbers and appending the sum to the list fibonacci_sequence. The value of the two previous numbers are then updated with the sum, and the loop continues until it reaches the given length.

## Factorials

### Write a function 

...that, given a number as input, returns the factorial of that number. The factorial of a number ‘n’ is the product of all positive integers less than or equal to ‘n’. So, the factorial of 6 would be 6*5*4*3*2*1 = 720. The factorial of 0 is 1.

Here is a function in C# that calculates the factorial of a given number:

    int Factorial(int number) 
    {
        if (number < 0) {
            throw new ArgumentException("Number must be non-negative.");
        }
        int result = 1;
        for (int i = 1; i <= number; i++) {
            result *= i;
        }
        return result;
    }

This function takes an integer input number and returns an integer. It starts by checking if the input number is less than zero, if so, it throws an exception, as the factorial of a negative number is not defined. If the input is non-negative, the function initializes an integer variable result with a value of 1. Using a for loop, the function then iterates over the integers from 1 to the input number, on each iteration it multiplies the result with the current integer, at the end of the loop, the result variable holds the factorial of the input number.

Here is the equivalent pseudocode

    function Factorial(number:int) : int
        if number < 0
            throw "Number must be non-negative."
        result = 1
        for i = 1 to number
            result = result * i
        return result

This pseudocode uses a function Factorial that takes in a number as input and returns an integer. It starts by checking if the input number is less than zero, if so, it throws an exception, as the factorial of a negative number is not defined. If the input is non-negative, the function initializes an integer variable result with a value of 1. Using a for loop, the function then iterates over the integers from 1 to the input number, on each iteration it multiplies the result with the current integer, at the end of the loop, the result variable holds the factorial of the input number.

### Write your solution with recursion

    int Factorial(int number) 
    {
        if (number < 0) {
            throw new ArgumentException("Number must be non-negative.");
        }
        if (number == 0) {
            return 1;
        }
        return number * Factorial(number - 1);
    }

This function takes an integer input number and returns an integer. It starts by checking if the input number is less than zero, if so, it throws an exception, as the factorial of a negative number is not defined. If the input is non-negative, the function checks if the input number is 0, in this case it returns 1, as 0! = 1. If the input is greater than 0, the function calls itself, passing the input number minus 1, this way the function keeps calling itself with the input number decremented by 1 until it reaches the input number of 0, at this point the function starts returning the accumulated value of all the multiplications, that is the factorial of the input number.

Here is the equivalent pseudocode
    function Factorial(number:int) : int
        if number < 0
            throw "Number must be non-negative."
        if number == 0
            return 1
        return number * Factorial(number - 1)

Here is a recursive solution in C# that calculates the factorial of a given number:

Copy code
int Factorial(int number) {
    if (number < 0) {
        throw new ArgumentException("Number must be non-negative.");
    }
    if (number == 0) {
        return 1;
    }
    return number * Factorial(number - 1);
}
This function takes an integer input number and returns an integer. It starts by checking if the input number is less than zero, if so, it throws an exception, as the factorial of a negative number is not defined. If the input is non-negative, the function checks if the input number is 0, in this case it returns 1, as 0! = 1. If the input is greater than 0, the function calls itself, passing the input number minus 1, this way the function keeps calling itself with the input number decremented by 1 until it reaches the input number of 0, at this point the function starts returning the accumulated value of all the multiplications, that is the factorial of the input number.

Here is the equivalent pseudocode

Copy code
function Factorial(number:int) : int
    if number < 0
        throw "Number must be non-negative."
    if number == 0
        return 1
    return number * Factorial(number - 1)
This pseudocode uses a function Factorial that takes in a number as input and returns an integer. It starts by checking if the input number is less than zero, if so, it throws an exception, as the factorial of a negative number is not defined. If the input is non-negative, the function checks if the input number is 0, in this case it returns 1, as 0! = 1. If the input is greater than 0, the function calls itself, passing the input number minus 1, this way the function keeps calling itself with the input number decremented by 1 until it reaches the input number of 0, at this point the function starts returning the accumulated value of all the multiplications, that is the factorial of the input number.

## Write a function, that print all the files in a given folder and sub-folders with using recursion

    void PrintFiles(string path) 
    {
        try {
            var files = Directory.GetFiles(path);
            foreach (var file in files) {
                Console.WriteLine(file);
            }
            var directories = Directory.GetDirectories(path);
            foreach (var directory in directories) {
                PrintFiles(directory);
            }
        } catch (UnauthorizedAccessException e) {
            Console.WriteLine(e.Message);
        }
    }

This function takes a string path as input and print all files and sub-folders. It starts by using the Directory.GetFiles method to get all the files in the given path and prints them using the Console.WriteLine method. Then it uses Directory.GetDirectories method to get all the sub-folders in the given path, for each sub-folder, it calls itself and pass the sub-folder path recursively, this way it keeps calling itself for each sub-folder found until all the files and sub-folders are printed. The function has a try-catch block to handle the UnauthorizedAccessException that may be thrown when the code does not have permission to access a certain file or folder, in this case, it will print the error message.

## What is “Stack overflow”? Write a code that ends up with stack overflow

A stack overflow occurs when a program or system tries to use more memory space than the call stack has available. The call stack is a memory structure that stores the memory addresses of the program's instructions and data, including function calls, return addresses, and local variables. Each time a function is called, its memory address is added to the call stack, and when the function returns, that memory address is removed from the call stack.

A stack overflow occurs when the call stack is exhausted and there is no more memory available to store the next function call. This can happen when a program enters into an infinite recursion, where a function calls itself repeatedly without ever returning.

    void InfiniteRecursion() 
    {
        InfiniteRecursion();
    }

    void Main() {
        InfiniteRecursion();
    }

In this example, the InfiniteRecursion function calls itself indefinitely, causing the call stack to fill up with memory addresses of the function calls. Since the function never returns, the memory addresses are never removed from the call stack, causing a stack overflow.

It's worth noting that stack overflow is a type of exception that can be caught and handled in some programming languages, but in some other languages, it can cause the program to crash or terminate abruptly.

## What is binary search tree (BST)? Write an implementation in Csharp

A binary search tree (BST) is a type of data structure that organizes data in a hierarchical tree-like structure, where each node has at most two child nodes: a left child node and a right child node. The key characteristic of a binary search tree is that the value of each node is greater than the values of all the nodes in its left subtree and less than the values of all the nodes in its right subtree. This property allows for efficient searching, insertion, and deletion operations on the data stored in the tree.

TODO

## What is linked list? How to find if a linked list has a loop?

A linked list is a data structure that consists of a sequence of elements called nodes, where each node contains a value and a reference (pointer) to the next node in the list. The last node in the list typically contains a reference to null, indicating the end of the list. Linked lists are often used when the size of the data is unknown or when the data is frequently changing, as they can be easily inserted or removed from the list.

There are several ways to check if a linked list has a loop, one of the most common methods is called the "Floyd's cycle-finding algorithm", also known as "the Tortoise and the Hare algorithm". This algorithm uses two pointers, called the "tortoise" and the "hare", that move through the list at different speeds. The "tortoise" moves one step at a time while the "hare" moves two steps at a time. If there is a loop in the list, at some point the "hare" will catch up to the "tortoise" and the two pointers will point to the same node.

    class Node 
    {
        public int Data { get; set; }
        public Node Next { get; set; }

        public Node(int data) {
            Data = data;
            Next = null;
        }
    }

    class LinkedList 
    {
        public Node Head { get; set; }

        public bool HasLoop() {
            Node tortoise = Head;
            Node hare = Head;

            while (hare != null && hare.Next != null) {
                tortoise = tortoise.Next;
                hare = hare.Next.Next;
                if (tortoise == hare) {
                    return true;
                }
            }

            return false;
        }
    }

In this example, the HasLoop method of the LinkedList class uses the "tortoise" and "hare" pointers to move through the list. The pointers start at the head of the list and move through the list, if there is a loop in the list, at some point the "hare" will catch up to the "tortoise" and the two pointers will point to the same node, and the function will return true indicating that there is a loop in the list. If the hare reaches the end of the list and there's no loops, the function will return false indicating that there's no loops in the list.

## How can you find the middle element of a linked list in a single pass?

Finding the middle element of a linked list in a single pass can be done using a technique called the "two-pointer technique". This technique uses two pointers, one called the "fast pointer" and the other called the "slow pointer", that move through the list at different speeds. The "fast pointer" moves two steps at a time while the "slow pointer" moves one step at a time. When the "fast pointer" reaches the end of the list, the "slow pointer" will be pointing at the middle element of the list.

    class Node 
    {
        public int Data { get; set; }
        public Node Next { get; set; }

        public Node(int data) {
            Data = data;
            Next = null;
        }
    }

    class LinkedList 
    {
        public Node Head { get; set; }

        public Node FindMiddle() {
            Node slow = Head;
            Node fast = Head;

            while (fast != null && fast.Next != null) {
                slow = slow.Next;
                fast = fast.Next.Next;
            }

            return slow;
        }
    }

In this example, the FindMiddle method of the LinkedList class uses the "slow pointer" and the "fast pointer" to move through the list. The pointers start at the head of the list and the "fast pointer" moves two steps at a time while the "slow pointer" moves one step at a time. When the "fast pointer" reaches the end of the list, the "slow pointer" will be pointing at the middle element of the list. If the list has an even number of elements, the middle element will be the one closer to the end of the list.

It's worth noting that this approach works only if the number of elements in the list is known, otherwise you'll need to traverse the list first to know the number of elements.

## In an array of integers there are from 1 to 100 numbers, one of which is a duplicate, how can you find it?

There are several ways to find a duplicate in an array of integers where there is from 1 to 100 numbers, one of which is a duplicate. Here are a few common methods:

Hash table: This method uses a hash table to store the counts of each number in the array. By iterating through the array and incrementing the count for each number in the hash table, we can find the duplicate number by checking for any numbers with a count greater than 1.

    int FindDuplicate(int[] arr) {
        var hash = new HashSet<int>();
        for(int i = 0; i < arr.Length; i++) {
            if(hash.Contains(arr[i])) {
                return arr[i];
            }
            hash.Add(arr[i]);
        }
        return -1; // -1 if no duplicate
    }

Sorting: This method sorts the array and then iterates through the array to find any duplicate numbers that are next to each other.

    int FindDuplicate(int[] arr) {
        Array.Sort(arr);
        for(int i = 0; i < arr.Length-1; i++) {
            if(arr[i] == arr[i+1]) {
                return arr[i];
            }
        }
        return -1; // -1 if no duplicate
    }

Math: This method uses mathematical properties of the numbers in the array to find the duplicate. The idea is to sum the numbers from 1 to 100 and subtract the sum of the array, the result will be the duplicate.

    int FindDuplicate(int[] arr) {
        int expectedSum = (100*101)/2;
        int actualSum = 0;
        for(int i = 0; i < arr.Length; i++) {
            actualSum += arr[i];
        }
        return actualSum - expectedSum;
    }

It's worth noting that all above methods have a linear time complexity of O(n) and a constant space complexity of O(1) and are suitable for small arrays with a small range of numbers.

## What is the difference between Stack and Queue data structure?

Stack and Queue are both linear data structures that are used to store and organize data, but they have different characteristics and behaviors.

A Stack is a last-in, first-out (LIFO) data structure. This means that the last element added to the stack is the first element to be removed. Stacks are often used in situations where the order of operations is important, such as undo/redo operations, function calls in a program, and backtracking algorithms. The main operations of a stack are push (add an element to the top of the stack) and pop (remove the top element from the stack).

A Queue is a first-in, first-out (FIFO) data structure. This means that the first element added to the queue is the first element to be removed. Queues are often used in situations where elements need to be processed in the order they were received, such as scheduling tasks or handling events. The main operations of a queue are enqueue (add an element to the end of the queue) and dequeue (remove the front element from the queue).

In short, Stack follows LIFO principle and Queue follows FIFO principle, meaning that the last element added to a Stack is the first element to be removed while the first element added to a Queue is the first element to be removed.

## What is QuickSort? Describe the main logic of this sorting algorithm

Quicksort is a divide-and-conquer sorting algorithm that uses a pivot element to partition the array into two sub-arrays. The pivot element is chosen in such a way that all elements less than the pivot element are in one sub-array and all elements greater than the pivot element are in the other sub-array. The pivot element is then in its final sorted position. The two sub-arrays are then recursively sorted in the same manner.

Here is a high-level description of the main logic of the Quicksort algorithm:

Choose a pivot element from the array. This can be done in different ways, a common approach is to choose the last element in the array.

Partition the array around the pivot element, so that all elements less than the pivot element are to the left of it and all elements greater than the pivot element are to the right of it.

Recursively sort the left and right sub-arrays obtained after partitioning.

Repeat steps 2 and 3 on the left and right sub-arrays until the entire array is sorted.

Here is an example of the quicksort algorithm implemented in C#:

    void QuickSort(int[] arr, int low, int high) 
    {
        if (low < high) {
            int pivotIndex = Partition(arr, low, high);
            QuickSort(arr, low, pivotIndex);
            QuickSort(arr, pivotIndex + 1, high);
        }
    }

    int Partition(int[] arr, int low, int high) 
    {
        int pivot = arr[high];
        int i = low - 1;
        for (int j = low; j < high; j++) {
            if (arr[j] <= pivot) {
                i++;
                Swap(arr, i, j);
            }
        }
        Swap(arr, i + 1, high);
        return i + 1;
    }

    void Swap(int[] arr, int i, int j) 
    {
        int temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
    }

In this example, the QuickSort method takes in an array, arr, and the low and high indices of the sub-array to be sorted. It first checks if the low index is less than the high index, if so, it calls the Partition method which partitions the array around the pivot element and returns the index of the pivot element. The QuickSort method then recursively calls itself on the left and right sub-arrays obtained after partitioning.

It's worth noting that the time complexity of Quicksort depends on the pivot element, if the pivot element is chosen such that the sub-arrays are not well-balanced, the time complexity can be as bad as O(n^2). However, if the pivot element is chosen such that the sub-arrays are well-balanced, the time complexity is O(n*log(n)).
