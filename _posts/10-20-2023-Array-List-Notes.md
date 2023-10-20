---
toc: True
comments: True
layout: post
title: ArrayList Notes
description: notes
courses: {'compsci': {'week': 1}}
type: hacks
---

**ArrayList Definition**
ArrayList is a part of the Java Collections Framework and is implemented in the java.util package.
It's a dynamic array that can grow or shrink in size during runtime.
Declaration and Initialization

- To use an ArrayList, you need to import the java.util.ArrayList class.
Declare an ArrayList like this: ArrayList<Type> listName = new ArrayList<Type>();
Adding Elements

- Use the add() method to insert elements at the end of the ArrayList: listName.add(element);
Elements can be of any data type (e.g., integers, strings, custom objects).
Accessing Elements

- Retrieve elements by their index using the get() method: listName.get(index);
Indexing is 0-based, so the first element is at index 0.
Size and Capacity

- **size() method** returns the number of elements in the ArrayList.
capacity is automatically managed by the ArrayList and expands as needed.
Removing Elements

- Remove elements by index using the remove(index) method.
Remove by object using the remove(object) method.
Checking for Existence

- Use contains(element) method to check if an element is present in the ArrayList.
Iterating Over ArrayList

- You can use a for-each loop, traditional for loop, or iterators to traverse elements.
ArrayList vs. Array

- Unlike arrays, ArrayLists can dynamically resize.
You don't need to specify a fixed size when initializing an ArrayList.
Generics

- Data type can be specified of what the ArrayList will hold (e.g., ArrayList<Integer>).
Common Operations

- **Sorting:** Use Collections.sort(listName) for sorting.
- **Clearing:** Use clear() to remove all elements from the ArrayList.

**Performance Considerations**
- ArrayLists are less efficient for inserting/removing elements in the middle.
- ArrayLists are more efficient for accessing elements by index.

**Autoboxing**
- ArrayLists automatically handle primitive types through autoboxing.

**Synchronization**
If thread safety is a concern, consider using Collections.synchronizedList() to create a synchronized ArrayList.

**ArrayList vs. LinkedList**
ArrayLists are generally faster for accessing elements by index.
LinkedLists are better for frequent insertions/deletions in the middle.
Memory Efficiency

- ArrayLists can be less memory-efficient due to their dynamic resizing and unused capacity.
Null Elements

- ArrayLists can contain null elements.
Compatibility

- ArrayLists can be used with enhanced for loops and other collection-related functions.