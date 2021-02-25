# reading 07

Notes from reading 07: Programming with Javascript (2.25.21)

----

## how javascript makes the web interactive

Java script is what describes the functionality of webpages. It can be used to access information like the text from input boxes, or the contents of a specific HTML element; JS can then interact with that content directly, even writing original html into the pages structure and modifying existing content. It can also define parameters for certain interactions such as how much an image should increase in size when clicked. JS is also aysnchronus, which means that it can be ran at anytime regardless of when the user interacts, this timing is programmed through the use of events; we say do something when the user clicks this thing, mouses over that thing, and types this. It's dynamic.

## what's a script

A script is a set of instructions for the computer to follow, and that's it. The computer will do *exactly* what we write, so it's important to prevent any misinterpretation. It's a bit like a genie; you wish for something ambigous, and what you get isn't exactly what you want.

when writing scripts it's important to write with a goal. What do you want the robot to do? Then write out the script with each step clearly defined. Edgar Allen Poe once said of writing mysteries that you start from the end and write backwards. Afterall, you have to know who did it. Maybe you can write scripts like that too. Start with a goal and work backwards until you're back where you started. 

What does that look like? How might a computer solve a murder mystery? We have to look at this logically. Remember that a computer works in binary; its calculations and movements are very simple. But at its most basic form, this is really just a series of yes:no, true:false, off:on, 1:0 questions. Reduce everything a few levels on the complexity scale, and imagine a flow chart. Is there a body: yes or no? If yes, is this a crime... you can see this gets very complex very quickly.

## javascript vocab 

An expression evaluates into a single value. An expression has two essential types. One assigns a value:

````js
//this expression assigns a value to variable 'cats'
let cats = 'Mittens and Socks';

/* 
let = keyword
cats = variable name
'Mittens and Socks' = value 
*/
````


Another expression uses a number of values to create one:

````js
//this expression uses two numbers to create a single one
let sum = 8 + 10; 
//sum = 18;
````

Both of these expressions use operators. Specifically, the assignment operator ('='). The other additionally uses a arithmetic operator ('+, -, /, *, ++, --, %'). There are also comparison ('==, ===, <, >, !==, !===, <=, >=') and and logical operators ('||, &&, !' ).

Arithmetic operators:

````js 
// + = addition
// - = subtraction
// / = division
// * = multiplication
// % = remainder
// ++ = increment
// -- = decrement
````

The '+' operator can also act on strings. 'Center' + ' Jenny' evaluates to 'Center Jenny' for instance.

