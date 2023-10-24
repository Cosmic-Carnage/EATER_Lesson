---
toc: True
comments: True
layout: post
title: Unit 7 ArrayLists
description: Lesson on the College Board Unit 7 ArrayLists.
courses: {'compsci': {'week': 1}}
type: hacks
authors: Tay, Raymond, Ethan T., Ethan Z., Anthony B.
---

## 7.1 Intro to ArrayLists

- An **ArrayList** is a utility from the ``java.util`` package

- To declare a variable, use the format `ArrayList<DataType> variableName = new ArrayList<DataType>(initial number of elements);`

- Unlike arrays, ArrayLists are mutable (can be resized after initialization)

- Functions as a more versatile array

    - Does technically take more space than an array but for the purposes of CSA it shouldn't matter
<br>
<br>

Difference between Array and Arraylist:
| Array | Arraylist |
| - | - |
| Fixed length | Resizable length |
| Fundamental Java Feature | Part of a Framework |
| An object with no methods | A Class with many methods |
| Not very flexible | Flexible |
| Can store primitives | Cannot store primitives - stores objects instead |

Example of Array: Basketball players on court

Example of Arraylist: Dodgeball players on court

### Question
When should we use ArrayLists vs Arrays?

Answer:

<br>
<br>
Showing how ArrayLists are mutable:


```java
import java.util.ArrayList;

class ArrayListExample { 
    public static void main(String[] args) 
    { 
        // Size of ArrayList 
        int n = 5; 
  
        // Declaring ArrayList with initial size n 
        ArrayList<Integer> arr1 = new ArrayList<Integer>(n); 
  
        // Declaring ArrayList without initial size
        ArrayList<Integer> arr2 = new ArrayList<Integer>(); 
  
        // Printing ArrayList 
        System.out.println("Array 1:" + arr1); 
        System.out.println("Array 2:" + arr2); 
  
        // Appending new elements to the end of the list 
        for (int i = 1; i <= n; i++) { 
            arr1.add(i); 
            arr2.add(i); 
        } 
  
        // Printing ArrayList 
        System.out.println("Array 1:" + arr1); 
        System.out.println("Array 2:" + arr2); 
    } 
}
ArrayListExample.main(null);
```

    Array 1:[]
    Array 2:[]
    Array 1:[1, 2, 3, 4, 5]
    Array 2:[1, 2, 3, 4, 5]


## 7.1 Popcorn Hack

Create an ArrayList that stores the integers 5, 8, 14, 18, 24, 39, and 56 and only print the numbers that are divisible by 3.


```java
import java.util.ArrayList;

public class DivisibleBy3 {
    public static void main(String[] args) {
        // declare variable and add integers

        System.out.println("Numbers divisble by 3:");
        // write code here
    }
}
DivisibleBy3.main(null);
```

### Vocabulary Refresher
- An **element** is a single value in the **array**

- The __**index**__ of an **element** is the position of the element in the **array** or **ArrayList**

    - The first index of an **ArrayList**, like **arrays** is also 0 
<br>
<br>
- The **length** of an **array** is the number of elements in the array.


## 7.2 Arraylist Methods
- add()
    - Adding a value to the ArrayList
    - Can be used to create an element at a specific index in the ArrayList - when this happens, everything at the positions of index and higher are moved to the right by 1 
- get()
    - Get the value of an index in the ArrayList
- set()
    - Change the value at an index in the ArrayList
- remove()
    - Delete the value at in index in the ArrayList
- clear()
    - Remove all values in an ArrayList
- size()
    - Get the length of the ArrayList


```java
import java.util.ArrayList;

public class Test {
    public static void main(String[] args) {
        ArrayList<Integer> test = new ArrayList<>();
        System.out.println(test.size());
        test.add(1); //index 0
        test.add(2); // index 1
        test.add(3); // index 2
        test.add(4); // index 3
        test.add(5); // index 4
        test.add(6); // index 5
        test.add(7); // index 6

        System.out.println(test);

        int i = test.set(1, 200); // prints what used to be at index 1
        int x = test.remove(4); // prints what was removed

        System.out.println(i);
        System.out.println(x);
        System.out.println(test);
    }
}
Test.main(null);
```

    0
    [1, 2, 3, 4, 5, 6, 7]
    2
    5
    [1, 200, 3, 4, 6, 7]


## Printing an ArrayList
- You can't print an **array** without a loop
- You can print **ArrayLists** with just one `System.out.println()`


```java
import java.util.ArrayList;

public class Main {
    public static void main(String[] args)
    {
        ArrayList<String> arr = new ArrayList<String>(); //initializes the arraylist object

        arr.add("I agree");
        arr.add(0, "You agree");
        System.out.println(arr);

        arr.set(0, "They agree");

        arr.add("I disagree");
        arr.remove(2);
        
        System.out.println();
        System.out.println(arr);
    }
}
Main.main(null);
```

    [You agree, I agree]
    
    [They agree, I agree]


## 7.2 Popcorn Hack

Finish the code below so that all duplicates in the ArrayList are removed.


```java
import java.util.Arraylist;

public class RemoveDuplicates {
    public static void main(String[] args) {
        ArrayList<Integer> arr = new ArrayList<>(); // creating new arraylist of integers
        
        // adding integers to the arraylist
        arr.add(1);
        arr.add(7);
        arr.add(9);
        arr.add(13);
        arr.add(3);
        arr.add(7);
        arr.add(9);
        arr.add(2);

        // add your code here
    }
}
RemoveDuplicates.main(null);
```

## Array to ArrayList
- You can use the Arrays.asList() method to convert an existing **array** to an **ArrayList**


```java
public class ArrayListFromArray
{
    public static void main(String[] args)
    {
       String[] names = {"Kim", "Tay", "Tran", "Ethan", "Sheng", "Raymond"};
       ArrayList<String> namesList = new ArrayList<String>(Arrays.asList(names));
       System.out.println(namesList);
    }
}
ArrayListFromArray.main(null);
```

    [Kim, Tay, Tran, Ethan, Sheng, Raymond]


## 7.3 Traversing ArrayLists
- You can traverse an ArrayList the same way as an array, with some exceptions:

- Deleting elements in the ArrayList while iterating over the ArrayList needs to be carefully done
- Using an enhanced for loop can result in the ConcurrentModificationException error
    - Do not delete elements in an ArrayList while using an enhanced for loop


```java
public static void main(String[] args)
{
    ArrayList<Integer> arr = new ArrayList<>();        
    arr.add(1);
    arr.add(7);
    arr.add(9);
    arr.add(13);
    arr.add(3);
    arr.add(7);
    arr.add(9);
    arr.add(2);

    for (int i = 0; i < arr.size(); i++) //for loop, would work the same as with an array
    {
        System.out.print(arr.get(i) + " ");
    }
    System.out.println();

    for (Integer i : arr) //enhanced for loop without removing, same as an array
    {
        System.out.print(i + " ");
    }

}
main(null);
```

    1 7 9 13 3 7 9 2 
    1 7 9 13 3 7 9 2 


```java
public static void main(String[] args)
{
    ArrayList<Integer> arr = new ArrayList<>();        
    arr.add(1);
    arr.add(7);
    arr.add(9);
    arr.add(13);
    arr.add(3);
    arr.add(7);
    arr.add(9);
    arr.add(2);

    for (Integer i : arr) //throws a ConcurrentModificationException
    {
        if (i % 2 == 0)
        {
            arr.remove(i);
        }
    }

}
main(null);
```


    ---------------------------------------------------------------------------

    java.util.ConcurrentModificationException: null

    	at java.base/java.util.ArrayList$Itr.checkForComodification(ArrayList.java:1013)

    	at java.base/java.util.ArrayList$Itr.next(ArrayList.java:967)

    	at .main(#13:13)

    	at .(#16:1)


## Popcorn Hack
Traverse the following ArrayList using a loop. Remove each element that is a multiple of 4. Keep in mind that the size will change when you remove an element.


```java
public static void main(String[] args)
{
    ArrayList<Integer> arr = new ArrayList<>();        
    arr.add(4);
    arr.add(7);
    arr.add(9);
    arr.add(80);
    arr.add(13);
    arr.add(3);
    arr.add(7);
    arr.add(8);
    arr.add(2);
    arr.add(16);
}
main(null);
```

## 7.4 Developing Algorithms Using ArrayLists
- For the most part, algorithms in ArrayLists and arrays are very similar.

## Popcorn Hacks
Find the maximum, minimum, and sum of an ArrayList.


```java
public static void main(String[] args)
{
    ArrayList<Integer> arr = new ArrayList<>();        
    arr.add(1);
    arr.add(7);
    arr.add(9);
    arr.add(80);
    arr.add(13);
    arr.add(3);
    arr.add(7);
    arr.add(8);
    arr.add(2);
    arr.add(16);
}
```

## 7.5 Searching

## 7.6 Sorting
- Using the sort() method

- Requires importing the Collections package

- Works both alphabetically (with Characters and Strings) and numerically (with Integers, Doubles, etc.)


```java
import java.util.ArrayList;
import java.util.Collections;

public class Main {
    public static void main(String[] args)
    {
        ArrayList<Character> arrSort = new ArrayList<Character>();
        arrSort.add('T');
        arrSort.add('E');
        arrSort.add('M');
        arrSort.add('B');
        arrSort.add('V');

        //Print the arraylist before sorting using enhanced for loop
        System.out.println("Before sorting: ");
        System.out.println(arrSort);

        Collections.sort(arrSort);

        //Print after sorting
        System.out.println("After sorting: ");
        System.out.println(arrSort);
    }
}
Main.main(null);
```

    Before sorting: 
    [T, E, M, B, V]
    After sorting: 
    [B, E, M, T, V]


## 7.6 Popcorn Hack

Given an ArrayList of String objects, sort the ArrayList on ascending order of word length.


```java
import java.util.ArrayList;

public class SortByLength {
    public static void main(String[] args) {
        ArrayList<String> words = new ArrayList<>(); // creating new arraylist
        
        // adding words to the list
        words.add("theater");
        words.add("connection");
        words.add("seasonal");
        words.add("feast");
        words.add("meeting");

        // add code for sorting by length here
    }
}
SortByLength.main(null);
```

## Hacks
- Complete all questions and popcorn hacks
- 

### Challenge
You are given an ArrayList of `Student` objects. Each `Student` has a name (String) and a GPA (double). Create a program that sorts the `Student` objects in descending order of GPA (greatest to smallest).


```java
import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;

class Student {
    String name;
    double gpa;

    public Student(String name, double gpa) {
        this.name = name;
        this.gpa = gpa;
    }
}

public class SortByGPA {
    public static void main (String[] args) {
        ArrayList<Student> students = new ArrayList<>(); // creating new arraylist to store student objects

        // add student objects to ArrayList

        // write code for sorting here
    }
}
SortByGPA.main(null);
```
