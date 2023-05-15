# Basic Datatypes And  Data Structures in Java

#### Datatypes and data structures serve as the foundation of creating robust and efficient programs in Java. </br>

By understanding these concepts, you'll be able to handle and manipulate data effectively, leading to more reliable and scalable applications.
# Datatypes In Java
- **variable** is a memory container that stores some value. 
- **Datatype** is a particular defined data item that specifies the size and type of a value. </br>
- So based on datatype a particular memory will be allocated to that variable.

Java is a **static typed language** so we have to specify data types to variables before compile time.</br>

</br>

**In Java data types are classified into two types:**
1. **Primitive Datatypes**: predefined by the language and named by a reserved keyword.
2. **Non-primitive Datatypes**: reference datatypes that are created by the developer.

### Primitive Datatypes: 

There are 8 primitive datatypes in Java.
#### 1. Boolean data type: boolean
- Stores two values: true or false
- Size: 1bit
- Default value: false
- use case: Simple flags that show true or false

#### 2. Byte datatype: byte
- Ranges from between -128 to 127(inclusive)
- Size: 1 bytes 
- Default value : 0
- Use case: To save memory in large arrays where memory savings is most required.

#### 3. Short datatype: short
- Ranges from between -32,768 to 32,767.
- Size: 2 bytes
- Default value : 0
- Use case: To save memory in the arrays if we know the min and max values in the array.

#### 4. Integer datatype: int
- Size: 4 bytes
- Default value: 0
- Use case: Used as the default data type for integral values unless there is a concern about memory usage.

#### 5.Long datatype: long
- Ranges from between -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807.
- Size: 8 bytes
- Default value: 0L
- Use case: Used when we need to represent larger integral values that are outside the range of int data type.

#### 6. Float datatype: float
- Ranges from between 1.4e-45 to 3.4028235e+38.
- Size: 4 bytes
- Default value: 0.0f
- Use case: Used when we need to represent floating-point values.

#### 7. Double datatype: double
- Ranges from between 4.9e-324 to 1.7976931348623157e+308.
- Size: 8 bytes
- Default value: 0.0d
- Use case: Used when we need to represent double-precision floating-point values.

#### 8. Charachter datatype : char
- Ranges from between '\u0000' to '\uffff'.
- Size: 2 bytes
- Default value: '\u0000'
- Use case: Used to represent a single character in Unicode format.
import java.util.LinkedList;
import java.util.Queue;


Here's an example of how to declare and assign values to these primitive data types:

```java
    byte b = 100;
    short s = 200;
    int i = 300;
    long l = 400L;
    float f = 3.14f;
    double d = 3.1415;
    char c = 'A';
    boolean bool = true;
```

</br>

### Non-Primitive Datatypes
- Non-primitive types are created by the programmer.
- Non-primitive types can be null and have methods to perform operations.
- Primitive types always have a value, while non-primitive types can be null.
- Primitive types start with a lowercase letter, while non-primitive types start with an uppercase letter (except for String).

```java
class Student{
  String name;
  int id;
}

// main
Student stu = new Student(); // user defined datatype(non-primitive)
int[] arr = new int[10]; // arr is also non primitive data type
```
</br> 

# Data Structures In Java
#### Java also provides several data structures that can be used to store and manipulate collections of data. 

</br>

## Arrays
 Collection of same type elements, arranged in contiguous block of memory. Each element can be accessed using index. First index is 0 and last index is n (length -1).
 ```java
 int[] numbers = {1, 2, 3, 4, 5}; // declare and initialize an array of integers

System.out.println(numbers[0]); // output: 1
System.out.println(numbers[2]); // output: 3

numbers[4] = 6; // assign a new value to the last element

for (int i = 0; i < numbers.length; i++) {
    System.out.println(numbers[i]); // output: 1 2 3 4 6
}

 ```
 </br>
 
- **Advantages:** Constant-time access to elements and efficient memory usage.
- **Limitations:** Fixed size and lack of flexibility in adding or removing elements.

</br>


## Arraylist
ArrayLists are implemented using an underlying array, but the ArrayList class provides methods for adding, removing, and accessing elements that make it easier to work with than arrays.
- Dynamic data structure that can hold elements of any data type.
- Can grow or shrink in size as needed.
- To use an ArrayList in Java, we must first import the **java.util.ArrayList class.**
```java
ArrayList<String> names = new ArrayList<>(); // declare an empty ArrayList of strings

names.add("Ali"); // add elements to the ArrayList
names.add("Barghav");
names.add("Charlie");

System.out.println(names.get(0)); // output: Ali
System.out.println(names.size()); // output: 3

names.remove(1); // remove an element from the ArrayList

for (String name : names) {
    System.out.println(name); // output: Ali Charlie
}
```
</br>

- **Advantages:** Constant-time access to elements and efficient memory usage.
- **Disadvantage:** Lack of flexibility in adding or removing elements.

</br>

## Linkedlist
Unlike arrays and ArrayLists, linked lists do not use contiguous blocks of memory. </br>
Instead, each node in a linked list can be located anywhere in memory, and the nodes are linked together by their references.
- To use a linked list, we must first import the java.util.LinkedList class.
```java
LinkedList<Integer> numbers = new LinkedList<>(); // declare an empty LinkedList of integers

numbers.add(1); // add elements to the LinkedList
numbers.add(2);
numbers.add(3);

System.out.println(numbers.getFirst()); // output: 1
System.out.println(numbers.getLast()); // output: 3

numbers.removeLast(); // remove the last element from the LinkedList

for (Integer number : numbers) {
    System.out.println(number); // output: 1 2
}

```

</br>

- **Advantages:** Flexible in adding or removing elements, and efficient insertion and removal of elements in the middle of the list.
- **Disadvantage:** Slower performance for random access to elements due to the need to traverse the list from the beginning.

</br>


## Stack
A stack is a data structure that follows the "last-in, first-out" (LIFO) principle, where the last element added to the stack is the first one to be removed.</br>

- **java.util.Stack** class implements a stack data structure that can hold elements of any data type.

```java

import java.util.Stack;

public class StackExample {
    public static void main(String[] args) {
        // Create a new stack of integers
        Stack<Integer> numbers = new Stack<>();

        // Push some numbers onto the stack
        numbers.push(1);
        numbers.push(2);
        numbers.push(3);

        // Print the top element of the stack
        System.out.println("Top element of the stack: " + numbers.peek());

        // Pop the top element of the stack and print it
        int poppedNumber = numbers.pop();
        System.out.println("Popped element: " + poppedNumber);

        // Print the new top element of the stack
        System.out.println("Top element of the stack: " + numbers.peek());
    }
}

```
</br>

- **Advantages:** Stack used in several applications such as expression evaluation, backtracking, and undo operations.
- **Disadvantage:** Limited access to elements in the middle of the stack and potential stack overflow errors if the stack size exceeds the available memory.

</br>

## Queue
A queue is a data structure that follows the "first-in, first-out" (FIFO) principle, where the first element added to the queue is the first one to be removed.

- java.util.Queue interface is used to implement a queue data structure that can hold elements of any data type.
- Queue interface was implemenetd by  LinkedList and ArrayDeque.


</br>

```java
import java.util.LinkedList;
import java.util.Queue;

public class QueueExample {
    public static void main(String[] args) {
        // Create a new queue of strings
        Queue<String> names = new LinkedList<>();

        // Add some names to the queue
        names.offer("Ali");
        names.offer("Bhargav");
        names.offer("Charlie");

        // Print the queue
        System.out.print("Queue: ");
        System.out.print(names); // Output: Queue: [Ali, Bhargav, Charlie]

        // Retrieve and remove the first name in the queue
        String firstName = names.poll();
        System.out.print(", First name removed: ");
        System.out.print(firstName); // Output: , First name removed: Ali

        // Print the updated queue
        System.out.print(", Updated queue: ");
        System.out.print(names); // Output: , Updated queue: [Bhargav, Charlie]

        // Retrieve the first name in the queue without removing it
        String firstInLine = names.peek();
        System.out.print(", First name in line: ");
        System.out.print(firstInLine); // Output: , First name in line: Bhargav
    }
}

```

</br>

- **Advantages:** Mainly used in simulation and scheduling algorithms.
- **Disadvantage:** limited access to elements in the middle of the queue and potential queue overflow errors if the queue size exceeds the available memory.

</br>

## HashMap

 - A Map is an interface in Java that represents a mapping between keys and values.
 - Each key is associated with a single value, and each key must be unique.
 - Some of the most commonly used implementations of the Map interface in Java include **HashMap**, **TreeMap**, and **LinkedHashMap**.
 - The HashMap class is a commonly used implementation of the Map.
 - It allows null values and provides constant-time performance for adding, removing, and retrieving elements.

**Hashmap:**  </br>

 - Basic implementation of a hash table, which stores key-value pairs in an unordered way.
 - Uses the key's hash code to determine the index in the array where the value should be stored.
 - Efficient for lookups and inserts

**LinkedHashMap:**  </br>

- Subclass of HashMap that maintains the order of insertion for the keys.
- It uses a doubly linked list to keep track of the order

**TreeMap:**  </br>

- Map that maintains the keys in sorted order.
- Uses a **binary search tree** to store the key-value pairs.
- Lookups and inserts are log(n) time complexity.
```java
import java.util.HashMap;
import java.util.LinkedHashMap;
import java.util.Map;
import java.util.TreeMap;

public class MapDemo {
    public static void main(String[] args) {
        // Create a HashMap
        Map<String, Integer> hashMap = new HashMap<>();
        hashMap.put("Charlie", 91);
        hashMap.put("Bhargav", 73);
        hashMap.put("Ali", 42);

        // Print the HashMap
        System.out.print("HashMap: ");
        System.out.println(hashMap); // {Charlie=91, Bhargav=73, Ali=42}

        // Create a LinkedHashMap
        Map<String, Integer> linkedHashMap = new LinkedHashMap<>();
        linkedHashMap.put("Charlie", 91);
        linkedHashMap.put("Bhargav", 73);
        linkedHashMap.put("Ali", 42);

        // Print the LinkedHashMap
        System.out.print("LinkedHashMap: ");
        System.out.println(linkedHashMap); // {Charlie=91, Bhargav=73, Ali=42}

        // Create a TreeMap
        Map<String, Integer> treeMap = new TreeMap<>();
        treeMap.put("Charlie", 91);
        treeMap.put("Bhargav", 73);
        treeMap.put("Ali", 42);

        // Print the TreeMap
        System.out.print("TreeMap: ");
        System.out.println(treeMap); // {Ali=42, Bhargav=73, Charlie=91}
    }
}

```
## References
- [Oracle Documentation: Primitive Datatypes](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/datatypes.html)
- [javaTpoint: Non-primitive Datatypes](https://www.javatpoint.com/non-primitive-data-types-in-java)
- [ MyGreatLearning: Basic Data Structures](https://www.mygreatlearning.com/blog/data-structures-using-java/)
