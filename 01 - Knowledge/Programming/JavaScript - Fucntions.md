# JavaScript Functions

> [!abstract] Day 4  
> Functions allow us to package logic into reusable pieces of code.
> 
> **Core idea:** Instead of writing the same instructions repeatedly, we define a function once and call it whenever we need it.

---

# 1. What Is a Function?

A **function** is a reusable block of code designed to perform a particular task.

For example:

```js
function greet() {
    console.log("Hello!");
}
```

This creates a function called `greet`.

However, defining a function does **not** execute it.

To execute it, we **call** the function:

```js
greet();
```

Output:

```text
Hello!
```

### The distinction

```js
function greet() {
    console.log("Hello!");
}
```

This is **defining** the function.

```js
greet();
```

This is **calling** the function.

Think of it as:

```text
Define → Create the machine
Call   → Turn the machine on
```

---

# 2. Why Do We Use Functions?

Functions solve several important problems.

## Repetition

Without functions:

```js
console.log("Welcome Jubert");
console.log("Welcome Layla");
console.log("Welcome John");
```

With a function:

```js
function welcome(name) {
    console.log("Welcome " + name);
}

welcome("Jubert");
welcome("Layla");
welcome("John");
```

The logic only has to be written once.

---

## Organization

A large program can become difficult to understand when everything is written in one giant block.

Functions allow us to separate responsibilities:

```text
Program
│
├── getUserInput()
├── calculateTotal()
├── displayResults()
└── saveData()
```

Each function has a specific job.

This becomes increasingly important as programs become larger.

---

# 3. Function Syntax

The basic structure is:

```js
function functionName() {
    // code
}
```

Example:

```js
function sayHello() {
    console.log("Hello");
}
```

The important parts are:

```text
function       → tells JavaScript we're defining a function

sayHello       → function name

()             → parameters go here

{ }            → function body
```

---

# 4. Calling a Function

Once a function exists, we can call it:

```js
sayHello();
```

A function can be called multiple times:

```js
sayHello();
sayHello();
sayHello();
```

Output:

```text
Hello
Hello
Hello
```

The same instructions are reused each time.

---

# 5. Parameters

Functions become much more useful when they can receive information.

A **parameter** is a variable placed inside the function definition that represents incoming data.

```js
function greet(name) {
    console.log("Hello " + name);
}
```

Here:

```text
name
```

is a parameter.

We can provide a value when calling the function:

```js
greet("Jubert");
```

Output:

```text
Hello Jubert
```

We can use a different value:

```js
greet("Layla");
```

Output:

```text
Hello Layla
```

The function itself hasn't changed.

Only the data going into it changed.

---

# 6. Parameters vs Arguments

These two terms are related but technically different.

### Parameter

The variable in the function definition:

```js
function greet(name) {
    console.log("Hello " + name);
}
```

`name` is the **parameter**.

### Argument

The actual value supplied when calling the function:

```js
greet("Jubert");
```

`"Jubert"` is the **argument**.

Mental model:

```text
function greet(name)
              ↑
          parameter

greet("Jubert")
       ↑
     argument
```

---

# 7. Multiple Parameters

A function can accept more than one parameter.

```js
function add(a, b) {
    console.log(a + b);
}
```

Calling it:

```js
add(5, 3);
```

Output:

```text
8
```

Another example:

```js
function introduce(name, age) {
    console.log("My name is " + name);
    console.log("I am " + age + " years old");
}
```

Calling:

```js
introduce("Jubert", 20);
```

---

# 8. Return Values

One of the most important ideas about functions is that they can **return a value**.

Example:

```js
function add(a, b) {
    return a + b;
}
```

When we call:

```js
add(5, 3);
```

the function produces:

```text
8
```

But unlike `console.log()`, the result isn't automatically displayed.

We can store the returned value:

```js
const result = add(5, 3);

console.log(result);
```

Output:

```text
8
```

---

# 9. `console.log()` vs `return`

These are **not the same thing**.

### `console.log()`

Displays something in the terminal:

```js
function add(a, b) {
    console.log(a + b);
}
```

### `return`

Sends a value back to whoever called the function:

```js
function add(a, b) {
    return a + b;
}
```

This distinction is extremely important.

Consider:

```js
function add(a, b) {
    return a + b;
}

const total = add(10, 5);
```

Now `total` contains:

```text
15
```

We can do more with it:

```js
const total = add(10, 5);

if (total > 10) {
    console.log("Large number");
}
```

The function produced a value that the rest of the program can use.

---

# 10. `return` Stops the Function

When JavaScript reaches a `return`, the function immediately stops executing.

Example:

```js
function test() {
    console.log("One");
    return;
    console.log("Two");
}
```

Calling:

```js
test();
```

Output:

```text
One
```

`"Two"` never runs because the function already returned.

---

# 11. Returning Different Types

A function can return different types of values.

Number:

```js
function getAge() {
    return 20;
}
```

String:

```js
function getName() {
    return "Jubert";
}
```

Boolean:

```js
function isAdult(age) {
    return age >= 18;
}
```

The last function can be used like this:

```js
const result = isAdult(20);

console.log(result);
```

Output:

```text
true
```

This connects directly to what we learned on Day 2.

A function can perform a calculation or decision and return the result.

---

# 12. Functions + Conditions

Functions can contain everything we've already learned.

For example:

```js
function checkAge(age) {
    if (age >= 18) {
        return "Adult";
    } else {
        return "Minor";
    }
}
```

Then:

```js
console.log(checkAge(20));
console.log(checkAge(15));
```

Output:

```text
Adult
Minor
```

The function packages the decision-making logic into a reusable unit.

---

# 13. Functions + Loops

Functions can also contain loops.

```js
function countToFive() {
    for (let i = 1; i <= 5; i++) {
        console.log(i);
    }
}
```

Calling:

```js
countToFive();
```

Output:

```text
1
2
3
4
5
```

This is where the concepts we've learned start connecting:

```text
Functions
    ↓
contain
    ↓
Variables
Conditions
Loops
Calculations
```

---

# 14. Functions Can Call Other Functions

A function can use another function.

```js
function add(a, b) {
    return a + b;
}

function showTotal() {
    const total = add(10, 20);
    console.log(total);
}
```

Calling:

```js
showTotal();
```

Output:

```text
30
```

This allows programs to be built from smaller pieces.

---

# 15. Function Composition

When we combine functions so that one function uses the result of another, we are doing a basic form of **function composition**.

Example:

```js
function add(a, b) {
    return a + b;
}

function double(number) {
    return number * 2;
}

const result = double(add(5, 3));

console.log(result);
```

First:

```text
add(5, 3)
```

produces:

```text
8
```

Then:

```text
double(8)
```

produces:

```text
16
```

So the final result is:

```text
16
```

The important idea is that functions can become building blocks for other functions.

---

# 16. Local Variables

Variables created inside a function generally belong to that function.

Example:

```js
function calculate() {
    const total = 100;
    console.log(total);
}
```

`total` exists inside `calculate()`.

Trying to use it outside:

```js
console.log(total);
```

will not work because `total` was created inside the function.

This is related to **scope**.

---

# 17. Scope

**Scope** determines where a variable can be accessed.

Example:

```js
const name = "Jubert";

function greet() {
    console.log(name);
}
```

The function can access `name` because it exists outside the function.

But:

```js
function greet() {
    const message = "Hello";
}

console.log(message);
```

does not work because `message` was created inside the function.

Mental model:

```text
Outside
│
│   const name = "Jubert"
│
└── Function
    │
    └── const message = "Hello"
```

The function can generally see variables available from its surrounding scope, but the outside cannot automatically see variables created inside the function.

---

# 18. Avoid Unnecessary Global Variables

This is a common beginner mistake:

```js
let total = 0;

function calculate() {
    total = 500;
}
```

The function is modifying something outside itself.

Sometimes that is intentional, but often it makes programs harder to understand.

Prefer passing information into functions and returning results:

```js
function calculate(price, quantity) {
    return price * quantity;
}

const total = calculate(500, 2);
```

Now the function has a clear relationship:

```text
Input
 ↓
Function
 ↓
Output
```

---

# 19. Functions Should Usually Have One Clear Responsibility

A function should ideally have a clear job.

Less organized:

```js
function doEverything() {
    // get input
    // calculate expenses
    // save file
    // print menu
    // validate password
    // display results
}
```

Better:

```text
getInput()
calculateExpenses()
saveExpenses()
displayMenu()
validatePassword()
displayResults()
```

This idea is called **separation of concerns**.

We'll explore it more deeply later in the foundation.

For now:

> A function should have a reason to exist.

---

# 20. Naming Functions

Function names should describe what the function does.

Good:

```js
calculateTotal()
checkAge()
getUserName()
saveExpenses()
displayMenu()
findContact()
```

Less useful:

```js
thing()
stuff()
doIt()
function1()
abc()
```

A good function name should make the code easier to understand without needing to inspect the function immediately.

---

# 21. Function Parameters Should Also Be Meaningful

Prefer:

```js
function calculateTotal(price, quantity) {
    return price * quantity;
}
```

over:

```js
function calculateTotal(x, y) {
    return x * y;
}
```

Both work.

The first communicates intent better.

---

# 22. Functions and the Problem-Solving Process

Functions aren't just a JavaScript feature.

They are a **problem-solving tool**.

Suppose the problem is:

> Build a program that calculates the total expenses for a user.

Instead of thinking about the whole program at once:

```text
"How do I build the expense tracker?"
```

break the problem down:

```text
Get expenses
    ↓
Calculate total
    ↓
Display total
```

Then:

```js
getExpenses()
calculateTotal()
displayTotal()
```

The functions become a map of the problem.

This is one of the most important habits we're building.

---

# 23. A Function Is Not Automatically Better

Don't create functions just for the sake of creating functions.

This:

```js
function printHello() {
    console.log("Hello");
}

printHello();
```

is technically valid, but if the function is only used once and adds no meaningful organization, it may not provide much benefit.

Functions become particularly useful when they:

- remove repetition
    
- isolate a task
    
- make code easier to understand
    
- allow reuse
    
- make testing easier
    
- reduce complexity
    

---

# 24. Common Mistakes

## Mistake 1: Forgetting to call the function

```js
function greet() {
    console.log("Hello");
}
```

Nothing happens until:

```js
greet();
```

---

## Mistake 2: Confusing `return` and `console.log`

```js
function add(a, b) {
    console.log(a + b);
}

const result = add(5, 3);
```

`result` will not contain `8`.

The function displayed the result but did not return it.

---

## Mistake 3: Returning too early

```js
function example() {
    return 10;
    return 20;
}
```

The second return can never be reached.

---

## Mistake 4: Forgetting parameters

```js
function greet(name) {
    console.log("Hello " + name);
}

greet();
```

If no argument is provided, `name` does not contain the expected string.

---

## Mistake 5: Overly large functions

A function containing hundreds of lines is often a sign that the task could be divided into smaller responsibilities.

We'll learn how to recognize and refactor this later.

---

# 25. Mental Model

When you see:

```js
function calculateTotal(price, quantity) {
    return price * quantity;
}
```

think:

```text
             price
               ↓
            ┌───────┐
quantity →  │  ×    │
            └───┬───┘
                ↓
              total
```

Or more generally:

```text
Input
  ↓
[ Function ]
  ↓
Output
```

The function is a small piece of logic with a defined interface.

---

# 26. Exercises

Complete these independently.

## Exercise 1: Greeting Function

Create a function called `greet` that accepts a name and prints:

```text
Hello Jubert
```

when called with:

```js
greet("Jubert");
```

---

## Exercise 2: Add Two Numbers

Create:

```text
add(a, b)
```

It should return the sum of two numbers.

Example:

```js
const result = add(10, 5);

console.log(result);
```

Expected:

```text
15
```

---

## Exercise 3: Even Number Checker

Create:

```text
isEven(number)
```

The function should return `true` if the number is even and `false` if it is odd.

Example:

```js
console.log(isEven(10));
console.log(isEven(7));
```

Expected:

```text
true
false
```

---

## Exercise 4: Age Checker

Create:

```text
checkAge(age)
```

It should return:

```text
"Adult"
```

when the age is 18 or above, and:

```text
"Minor"
```

otherwise.

---

## Exercise 5: Calculate Expense

Create:

```text
calculateExpense(price, quantity)
```

It should return:

```text
price × quantity
```

Example:

```js
const total = calculateExpense(500, 3);

console.log(total);
```

Expected:

```text
1500
```

---

# 27. Mini-Project: Number Utilities

Build a small program containing several functions that work with numbers.

Your program should have functions that can:

```text
1. Add two numbers
2. Subtract two numbers
3. Multiply two numbers
4. Divide two numbers
5. Check whether a number is even
6. Check whether a number is positive, negative, or zero
```

For example, conceptually:

```text
add()
subtract()
multiply()
divide()
isEven()
classifyNumber()
```

You should decide how the functions work and how the program interacts with the user.

### Important

Don't try to make this sophisticated.

The purpose is to practice:

- defining functions
    
- calling functions
    
- parameters
    
- arguments
    
- return values
    
- conditions inside functions
    
- using returned values
    
- combining functions
    

---

# 28. Day 4 Mastery Check

Before considering Day 4 complete, you should be able to explain these in your own words:

1. What is a function? 
    
2. What is the difference between defining and calling a function? 
    
3. What is a parameter? 
    
4. What is an argument?  
    
5. What does `return` do? 
    
6. What is the difference between `return` and `console.log()`? 
    
7. What happens after JavaScript reaches a `return`?  
    
8. What is scope? 
    
9. Why are local variables useful? 
    
10. Why should functions generally have clear responsibilities? 
    
11. How can functions help break a large problem into smaller problems?
    
12. Can a function call another function? 
    
13. Can a function contain conditions and loops? 
    
14. Why might returning a value be more useful than simply printing it? 
    

---

# 29. Practice Log

Record:

```text
Date:
Time spent:

Topics studied:
- Functions
- Parameters
- Arguments
- Return values
- Scope
- Function composition

Exercises completed:

What I understood:

What confused me:

What I struggled with:

What I learned by debugging/researching:

What I can now do without help:

AI used:
- Yes / No

If yes, how:
```

---

# 30. Key Principle

> **A function packages a piece of logic so that it can be understood, reused, and combined with other pieces of logic.**

The deeper progression we're building is:

```text
Variables
    ↓
Conditions
    ↓
Loops
    ↓
Functions
    ↓
Functions + Data
    ↓
Programs
```

Functions are where our programs start becoming less like a list of instructions and more like a collection of cooperating parts.

---

# Day 4 Goal

By the end of today, you should be able to look at a problem and naturally think:

```text
"What pieces of this problem can become functions?"
```

Not:

```text
"How do I write the entire program?"
```

That shift is the real lesson.