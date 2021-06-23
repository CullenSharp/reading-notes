# Linked Lists

June 18th, 2021

## What are they

A linear sequence of objects that are linked / connected together (array/SQL/Callback => stack)

- Arrays: other languages have arrays that are fixed size
  - those languages used a linked list to add items to a larger linked list

> a Set is a mapping object.

```JS
const list = {
    head: {
        value: 6
        next: {
            value: 10                                        
            next: {
                value: 12
                next: {
                    value: 3
                    next: null,
                    }
                }
            }
        }
    }
};
```

Code for createing nodes

```JS
class Node {
  constructor(value) {
    this.value = value;
    this.next = null;
  }
}
```

for a list 

```JS
class List {
  constructor()
}
```

## Behaviors

- Linked lists traverse a linear sequence of Nodes. Not random access
- *Unlike Arrays*, `Nodes` are not stored in a particular memory location or index
- because `Nodes` contain references to other `Nodes`, linked lists are recursive
- `Nodes` can be easily added or removed from a linked list without changing the organization. You could say the structure is dynamic.

## Types

- `Singly`: Each Node contains a single pointer to the *next* Node in the list
- `Doubly`: Each Node contains two pointers to the next and previous Node
- `Circular`: The last Node contains a pointer to the first Node

## Terminology

- Node: something that holds data
  - `value`: stores the data value
  - `next`: (a pointer) stores a references point to another Node, or null // undef.
- Head: the entry point to a linked list

## unrelated tid bits

- `node file.js`: runs the code that
- console.log doesn't log objects that are **more than two layers deep**, so convert to json

```JS
const myObj = {
  another: {
    oneMore: {
      yetAnother: {
        okayComeOnNow: {
          thisIsExcessive: {
            yup: {
              justToBeSafe: {
                okayLastOne: {

                },
              },
            },
          },
        },
      },
    },
  },
}

console.log(myObj); // expect {another:{oneMore: [Object] }}
console.log(JSON.stringify(myObj));
```

## References & further reading

- [How to Implement a Linked List in JavaScript](https://www.freecodecamp.org/news/implementing-a-linked-list-in-javascript/)
