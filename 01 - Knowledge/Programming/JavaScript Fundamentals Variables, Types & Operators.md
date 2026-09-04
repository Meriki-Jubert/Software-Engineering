
## Overview

JavaScript programs work by storing, manipulating, and producing information.

The first building blocks to understand are:

- Variables
    
- Values
    
- Data types
    
- Operators
    
- Output
    
- Basic input
    

The goal is not to memorize JavaScript syntax. The goal is to understand **how a program represents and works with information**.

---

## 1. Variables

A variable is a named reference to a value that a program can use.

```js
let age = 20;
const name = "Jubert";
```

Here:

- `age` refers to the value `20`
    
- `name` refers to the value `"Jubert"`
    

### `let`

Use `let` when you expect the variable to be reassigned.

```js
let score = 10;

score = 15;
```

The value associated with `score` can change.

### `const`

Use `const` when you do not intend to reassign the variable.

```js
const country = "Cameroon";
```

Trying to reassign it causes an error:

```js
country = "Nigeria";
```

### Mental model

Think of:

```text
let   → this value may be reassigned
const → this value should not be reassigned
```

Prefer `const` by default and use `let` when reassignment is actually needed.

---

## 2. Values

A variable is not the value itself.

For example:

```js
let age = 20;
```

There are three useful ideas here:

```text
variable name → age
value         → 20
type          → number
```

The value is the actual piece of information.

The variable gives us a way to refer to that information.

---

## 3. Primitive Data Types

JavaScript has several data types.

For now, focus on these primitive types:

### String

Used for text.

```js
const name = "Jubert";
const anime = "Naruto";
```

Strings can use single or double quotes:

```js
"hello"
'hello'
```

They represent text, not numbers.

```js
const age = "20";
```

The value above is a **string**, even though it contains digits.

---

### Number

Used for numeric values.

```js
const age = 20;
const price = 1500;
const temperature = 25.5;
```

JavaScript uses the `number` type for both integers and decimal numbers.

---

### Boolean

Represents one of two values:

```js
true
false
```

Example:

```js
const isStudent = true;
const isLoggedIn = false;
```

Booleans are especially important when programs need to make decisions.

---

## 4. Checking a Data Type

JavaScript provides `typeof` to determine the type of a value.

```js
console.log(typeof "hello");
console.log(typeof 20);
console.log(typeof true);
```

The results are:

```text
string
number
boolean
```

You can also use it with variables:

```js
const age = 20;

console.log(typeof age);
```

Output:

```text
number
```

---

## 5. `console.log()`

`console.log()` displays information in the terminal.

```js
console.log("Hello");
```

You can print variables:

```js
const name = "Jubert";

console.log(name);
```

You can also print multiple values:

```js
const name = "Jubert";
const age = 20;

console.log(name, age);
```

A useful way to think about `console.log()` is:

> **"Show me what this program currently knows."**

It is also one of the simplest debugging tools.

---

## 6. Arithmetic Operators

JavaScript can perform calculations using operators.

|Operator|Meaning|Example|
|---|---|---|
|`+`|Addition|`10 + 5`|
|`-`|Subtraction|`10 - 5`|
|`*`|Multiplication|`10 * 5`|
|`/`|Division|`10 / 5`|
|`%`|Remainder|`10 % 3`|

Examples:

```js
console.log(10 + 5);
console.log(10 - 5);
console.log(10 * 5);
console.log(10 / 5);
console.log(10 % 3);
```

### The remainder operator `%`

The `%` operator gives the remainder after division.

```js
10 % 3
```

The result is:

```text
1
```

because:

```text
3 × 3 = 9
10 - 9 = 1
```

The remainder operator becomes useful for things such as:

- checking whether numbers are even or odd
    
- cycling through values
    
- working with time
    
- distributing items
    
- solving algorithmic problems
    

---

## 7. Comparison Operators

Comparison operators compare values and produce a boolean.

```js
10 > 5
```

Result:

```text
true
```

Common comparison operators:

|Operator|Meaning|
|---|---|
|`>`|greater than|
|`<`|less than|
|`>=`|greater than or equal to|
|`<=`|less than or equal to|
|`===`|strictly equal|
|`!==`|strictly not equal|

Examples:

```js
console.log(10 > 5);
console.log(10 < 5);
console.log(10 === 10);
console.log(10 !== 5);
```

The results are booleans.

```text
true
false
true
true
```

### `===` vs `==`

For now, prefer:

```js
===
```

rather than:

```js
==
```

`===` performs strict equality checking and does not perform the same automatic type conversion that `==` can perform.

This is an important habit to establish early.

---

## 8. Type Conversion

Sometimes a value needs to be converted from one type to another.

For example:

```js
const age = "20";
```

This is a string.

It can be converted to a number:

```js
const age = Number("20");
```

Now:

```js
typeof age
```

produces:

```text
number
```

Other useful conversions include:

```js
String(20)
Number("20")
Boolean(1)
```

Type conversion becomes particularly important when receiving input from users.

---

## 9. Node.js and Input

JavaScript can run outside the browser using Node.js.

A Node.js program can receive input from the terminal.

One common approach is using Node's `readline` module.

Example:

```js
const readline = require("readline");

const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout
});

rl.question("What is your name? ", (name) => {
    console.log(`Hello, ${name}!`);
    rl.close();
});
```

The important idea is that the program can:

```text
ask for information
        ↓
receive input
        ↓
store it
        ↓
process it
        ↓
produce output
```

Don't worry about memorizing the `readline` code yet.

For now, understand the **flow**.

---

## 10. A Critical Detail About Input

User input commonly arrives as text.

For example, if someone enters:

```text
20
```

your program may receive:

```js
"20"
```

rather than:

```js
20
```

Those are different values.

```js
"20" // string
20   // number
```

This is why type conversion matters.

For example:

```js
const age = Number(input);
```

converts the input into a number.

---

# Common Mistakes

## Mistake 1: Forgetting quotes around strings

Incorrect:

```js
const name = Jubert;
```

JavaScript interprets `Jubert` as a variable name.

Correct:

```js
const name = "Jubert";
```

---

## Mistake 2: Treating a number stored as a string like a number

```js
const age = "20";
```

This is not the same as:

```js
const age = 20;
```

Always pay attention to the type of your data.

---

## Mistake 3: Using `let` everywhere

Not every variable needs to change.

Instead of:

```js
let name = "Jubert";
```

if the value will never be reassigned:

```js
const name = "Jubert";
```

is usually clearer.

---

## Mistake 4: Using `==` without understanding it

Prefer:

```js
===
```

for equality comparisons while learning JavaScript.

---

## Mistake 5: Writing code without knowing what each line does

A program that works is not necessarily a program you understand.

During the foundation month:

> **You should be able to explain every line of code you write.**

---

# Mental Models

### Variables

> A way for a program to keep track of information using names.

### Data types

> Categories describing what kind of value something is.

### Operators

> Symbols or constructs that allow a program to calculate or compare values.

### `console.log()`

> A way to display information from the program.

### Type conversion

> Changing a value from one data type into another.

---

# Practice

Complete these without looking for solutions.

## Exercise 1: Personal Information

Create variables containing:

- your name
    
- your age
    
- your favorite anime
    
- your favorite football player
    

Print them to the terminal.

---

## Exercise 2: Data Types

Create variables containing:

- your name
    
- your age
    
- whether you like anime
    
- your height
    

Use `typeof` to print the type of every value.

---

## Exercise 3: Simple Budget

A student has `5000 FCFA`.

They spend:

- `1200 FCFA` on food
    
- `800 FCFA` on transport
    

Write a program that calculates:

1. Total amount spent
    
2. Remaining money
    
3. Whether they still have at least `3000 FCFA`
    

---

# Mastery Check

Before considering this topic understood, you should be able to answer these without looking at your notes:

1. What is a variable?
    
2. What's the difference between `let` and `const`?
    
3. What is the difference between `"20"` and `20`?
    
4. What are strings, numbers, and booleans?
    
5. What does `typeof` do?
    
6. What does `console.log()` do?
    
7. What does `%` calculate?
    
8. What does `===` mean?
    
9. Why might user input need type conversion?
    
10. Why would a program need variables in the first place?
    

If you can explain these in your own words, you are moving from **"I've seen this syntax"** toward **"I understand what I'm doing."**

---

# Connections

These concepts lead directly into:

- [[JavaScript - Conditional Statements]]
    
- [[JavaScript - Loops]]
    
- [[JavaScript - Functions]]
    
- [[JavaScript - Arrays]]
    
- [[JavaScript - Objects]]
    
- [[JavaScript - Type Conversion]]
    
- [[Programming - Input and Output]]
    

---

# Practice Log

**Date:** 2026-09-02

**Topics studied:**

- Variables
    
- `let`
    
- `const`
    
- Primitive data types
    
- `typeof`
    
- `console.log()`
    
- Arithmetic operators
    
- Comparison operators
    
- Type conversion
    
- Basic Node.js input/output
    

**What I understood:**

**What confused me:**

**What I struggled with:**

**What I built:**

**What I can now do without help:**

**Questions to revisit:**

---

# Key Principle

> **Don't measure progress by how much syntax you can remember. Measure it by whether you can look at a problem and know how to begin.**