# ADTs: Stacks and Queues (5.25.21)

## On data structures

Both stacks and queues are types of [data structures](https://en.wikipedia.org/wiki/Data_structure), or the logical formation and ordering of data in sequence (ie a list). More specifically, as I understand it, what distinguishes a stack from a queue is the means in which data is acessed in memory: *LIFO, FIFO*.

In the process of my research I also came accross *Abstract Data Types*, which are defined as "a type for objects whose behaviour is defined by a set of values and operations" [(Geeks for Geeks)](https://www.geeksforgeeks.org/abstract-data-types/). More on that in a second. For now it will suffice to say that the notion of data structures forms the basis for ADTs.

## Abstract Data Types

> The process of providing only the essentials and hiding the details is known as abstraction.

As was stated above abstract data types, hereby referred to as ADTs, are types or classes for objects that are defined by a set of values and operations. They are *implementation agnostic* as the ADT does not specify how its operations or values will be implemented.

**Stacks, Queues and Lists are types of ADTs**; sometimes referred to as the Stack ADT, List ADT, or Queue ADT.

## Lists

A list contains elements of the same type stored in sequential order in memory. Here are some of this ADTs operations:

- get() - return an element form the list given a positions

- insert() - insert an element at any position

- remove() - remove the first occurence of an element

- removeAt() - remove an element at a given position

- replace() - Replace an element at any position with another element

- size() - returns the number of elements in the list

- isEmpty() - return true if empty

- isFull() - !isEmpty()

> I'm noticing some similarities to the [binary search algorithm](https://replit.com/@CullenSharp2/Binary-Search#index.js) I worked on earlier. Particularly, the names of these operations... get() for example was used in my arrayView() function. Maybe what that "function" actually does is define a data structure or abstract data type. I define operations outside of what the primitive was designed to facilitate... 🤔

---

![A stack](https://images.unsplash.com/photo-1530021853947-7d73da7acb70?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=634&q=80)
[source: Toa Heftiba](https://images.unsplash.com/photo-1530021853947-7d73da7acb70?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=634&q=80)

## Stacks

Rather than storing data in a node as a list does, stacks store a pointer to the data in memory.

All operations in a stack start at the top and work in sequential order. This is useful if you need to follow a set of rules; PEMDAS for example is a set of rules for interpreting mathmatical equations. This would be a good usecase for stacks.

![Stack diagram](https://media.geeksforgeeks.org/wp-content/uploads/20190917225800/StackADT.jpg)
[source: Geeks for Geeks](https://www.geeksforgeeks.org/abstract-data-types/)

It can perform:

- push() - insert and element at the top of the stack

- pop() - remove and return the top element

- peek() - return the top element without removing it

- size() - return the number of elements in the stack

- isEmpty() - return true if stack is empty

- isFull() - !isEmpty()

This is a simple stack implementation in javascript:

```JS
const stack = [];
stack.push(2);       // stack is now [2]
stack.push(5);       // stack is now [2, 5]
let i = stack.pop(); // stack is now [2]
alert(i);            // displays 5
```

[source: Corey Ballou](https://stackoverflow.com/questions/1590247/how-do-you-implement-a-stack-and-a-queue-in-javascript)

---

![A line of people](https://images.unsplash.com/photo-1586979816990-1819efcad0de?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1050&q=80)
[Source: Adrien Delforge](https://unsplash.com/@adriendlf)

## Queues

There are two primary differences between a stack and a queue. A stack is vertical, whereas a queue is horizontal. A queue operates on the principle of First in First out (FIFO). Stacks use the principle of Last in Last out (LIFO).

Imagine this; if you're always serving the most recent person in a line before everyone else, then everybody else will have to wait longer. This is the difference between a stack and a queue at the level of implentation.

```JS
const queue = [];
queue.push(2);         // queue is now [2]
queue.push(5);         // queue is now [2, 5]
let i = queue.shift(); // queue is now [5]
alert(i);              // displays 2
```

[source: Corey Ballou](https://stackoverflow.com/questions/1590247/how-do-you-implement-a-stack-and-a-queue-in-javascript)


Some queue operations:

- enqueue() - insert an element at the end of the queue (equivalent to shift())

- dequeue() - remove and return the first element (equivalent to unshift())

- peek() - return the first element without removing it

- size() - return the number of elements in the queue

- isEmpty() - return true if the queue is empty

- isFull() - !isEmpty()

---

## Conclusion

The notion of ADTs (Abstract Data Types) is reliant data structures as a basis. Lists, stacks, queues and etc are ADTs; they are implementation agnostic. you might use them for calculators or to facilitate back and forward functions on a browser. Each of them, however, has a set of descriptors and operations that define them under the hood.

## references

[Abstract Data Types (Geeks for Geeks)](https://www.geeksforgeeks.org/abstract-data-types/)

[Abstract Data types (Wikipedia)](https://en.wikipedia.org/wiki/Abstract_data_type)

[Corey Ballou](https://stackoverflow.com/users/185882/corey-ballou) on [Stack Overflow](https://stackoverflow.com/questions/1590247/how-do-you-implement-a-stack-and-a-queue-in-javascript)

[Data Structures (Wikipedia)](https://en.wikipedia.org/wiki/Data_structure)

[Pavindu Lakshan](https://pavindulakshan.medium.com/) on [Medium](https://medium.com/javarevisited/introduction-to-stacks-71dfad8782ef)

[Premarj](https://stackoverflow.com/users/1697099/premraj) on [Stack Overflow](https://stackoverflow.com/questions/10267084/what-is-adt-abstract-data-type)
