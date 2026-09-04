# JavaScript: Conditional Statements & Boolean Logic

## Overview

Programs often need to make decisions.

For example:

- If the user is logged in, show their account.
    
- If the balance is sufficient, allow a purchase.
    
- If the password is correct, allow access.
    
- If a number is even, do one thing; otherwise, do another.
    

JavaScript uses **conditional statements** and **boolean expressions** to make these decisions.

---

# 1. Boolean Values

A boolean can have only two values:

```js
true
false
```

Boolean values are useful for representing conditions.

```js
const isLoggedIn = true;
const hasPermission = false;
```

A comparison also produces a boolean:

```js
10 > 5
```

Result:

```text
true
```

And:

```js
10 < 5
```

Result:

```text
false
```

---

# 2. Comparison Operators

Comparison operators compare values.

|Operator|Meaning|
|---|---|
|`>`|greater than|
|`<`|less than|
|`>=`|greater than or equal to|
|`<=`|less than or equal to|
|`===`|strictly equal to|
|`!==`|strictly not equal to|

Examples:

```js
const age = 20;

age >= 18
age === 20
age < 30
```

Each expression produces either:

```text
true
```

or:

```text
false
```

---

# 3. `if`

An `if` statement allows a program to execute code only when a condition is true.

```js
if (condition) {
    // code to execute
}
```

Example:

```js
const age = 20;

if (age >= 18) {
    console.log("You are an adult.");
}
```

The program evaluates:

```js
age >= 18
```

which becomes:

```text
20 >= 18
↓
true
```

Because the condition is true, the code inside the `if` block runs.

---

# 4. `else`

`else` provides an alternative when the `if` condition is false.

```js
const age = 16;

if (age >= 18) {
    console.log("You are an adult.");
} else {
    console.log("You are not an adult.");
}
```

The flow is:

```text
          age >= 18?
           /     \
        true     false
         ↓         ↓
      if block   else block
```

Only one of the two branches executes.

---

# 5. `else if`

Sometimes there are more than two possibilities.

Use `else if` to check additional conditions.

```js
const score = 75;

if (score >= 80) {
    console.log("Excellent");
} else if (score >= 60) {
    console.log("Good");
} else {
    console.log("Needs improvement");
}
```

The conditions are evaluated from top to bottom.

Once JavaScript finds a true condition, its block executes and the remaining branches are skipped.

---

# 6. Order Matters

Consider:

```js
const score = 85;

if (score >= 50) {
    console.log("Pass");
} else if (score >= 80) {
    console.log("Excellent");
}
```

The output is:

```text
Pass
```

Why?

Because JavaScript checks the first condition:

```js
score >= 50
```

which is already true.

It never reaches the `else if`.

This means conditional branches should generally be arranged from the **most specific or restrictive condition to the more general ones**, depending on the problem.

---

# 7. Logical Operators

Logical operators allow us to combine or manipulate conditions.

## AND: `&&`

`&&` means **both conditions must be true**.

```js
age >= 18 && hasID === true
```

For the entire expression to be true:

```text
condition A → true
condition B → true
               ↓
             true
```

Example:

```js
const age = 20;
const hasID = true;

if (age >= 18 && hasID === true) {
    console.log("Access granted.");
}
```

If either condition is false, the whole `&&` expression is false.

---

## OR: `||`

`||` means **at least one condition must be true**.

```js
isAdmin || isTeacher
```

Possible outcomes:

|Condition A|Condition B|Result|
|---|---|---|
|false|false|false|
|true|false|true|
|false|true|true|
|true|true|true|

Example:

```js
if (isAdmin || isTeacher) {
    console.log("You can access this area.");
}
```

---

## NOT: `!`

`!` reverses a boolean value.

```js
!true
```

becomes:

```text
false
```

And:

```js
!false
```

becomes:

```text
true
```

Example:

```js
const isLoggedIn = false;

if (!isLoggedIn) {
    console.log("Please log in.");
}
```

The condition means:

> "If the user is **not** logged in."

---

# 8. Combining Conditions

Conditions can be combined.

```js
const age = 20;
const hasTicket = true;

if (age >= 18 && hasTicket) {
    console.log("You may enter.");
}
```

This requires both:

```text
age >= 18
AND
hasTicket
```

to be true.

---

# 9. Truthy and Falsy Values

JavaScript does not only treat `true` and `false` as conditions.

Many values can be evaluated as either **truthy** or **falsy**.

Common falsy values include:

```js
false
0
""
null
undefined
NaN
```

Many other values are truthy.

For example:

```js
if ("hello") {
    console.log("This runs.");
}
```

The string `"hello"` is truthy.

And:

```js
if (0) {
    console.log("This does not run.");
}
```

`0` is falsy.

### Important

Do not try to memorize every truthy/falsy rule immediately.

For now, understand:

> JavaScript can evaluate values in a boolean context.

---

# 10. Explicit Comparisons vs Truthiness

These are different styles:

```js
if (age >= 18) {
    // ...
}
```

and:

```js
if (isLoggedIn) {
    // ...
}
```

The first explicitly creates a comparison.

The second asks JavaScript to evaluate whether `isLoggedIn` is truthy.

Both are useful.

---

# 11. Nested Conditions

An `if` can contain another `if`.

```js
if (age >= 18) {
    if (hasID) {
        console.log("Access granted.");
    }
}
```

However, nested conditions can become difficult to read.

Often, related conditions can be combined:

```js
if (age >= 18 && hasID) {
    console.log("Access granted.");
}
```

Prefer the clearer version when both express the same logic.

---

# 12. Conditions as Questions

A useful mental model is to read conditions as questions.

```js
age >= 18
```

Read it as:

> "Is the age greater than or equal to 18?"

```js
balance >= price
```

Read it as:

> "Is the balance enough to pay for the price?"

```js
username === "Jubert"
```

Read it as:

> "Is the username exactly Jubert?"

This makes conditional logic easier to reason about.

---

# Common Mistakes

## Mistake 1: Confusing `=` with `===`

```js
=
```

is assignment.

```js
===
```

is strict equality comparison.

For example:

```js
const age = 20;

if (age === 20) {
    console.log("Correct.");
}
```

---

## Mistake 2: Forgetting that comparisons produce booleans

```js
age >= 18
```

doesn't produce a number.

It produces:

```text
true
```

or:

```text
false
```

---

## Mistake 3: Making conditions unnecessarily complicated

If:

```js
if (age >= 18 && hasID === true)
```

works, don't automatically turn it into several nested `if` statements.

Good code often expresses the logic directly.

---

## Mistake 4: Incorrect condition ordering

In an `if / else if / else` chain, JavaScript checks conditions from top to bottom.

The first true condition wins.

---

# Mental Models

### `if`

> "Run this code if this condition is true."

### `else`

> "Otherwise, run this code."

### `else if`

> "If the previous conditions weren't true, check this one."

### `&&`

> "Both must be true."

### `||`

> "At least one must be true."

### `!`

> "Reverse the boolean."

### Truthy / falsy

> "How JavaScript interprets a value when it expects a boolean."

---

# Practice

## Exercise 1: Age Checker

Create a program that asks the user for their age.

If the age is 18 or older:

```text
You are eligible.
```

Otherwise:

```text
You are not eligible.
```

---

## Exercise 2: Number Classifier

Ask the user for a number.

Determine whether the number is:

- positive
    
- negative
    
- zero
    

Example:

```text
Enter a number: -7

The number is negative.
```

---

## Exercise 3: Login Check

Create a program with:

```text
username
password
```

Ask the user to enter both.

If both match the expected values, print:

```text
Login successful.
```

Otherwise:

```text
Invalid username or password.
```

Use `&&`.

---

## Exercise 4: Grade Classifier

Ask the user for a score.

Use `if`, `else if`, and `else` to classify it.

For example:

```text
80-100 → Excellent
60-79  → Good
50-59  → Pass
Below 50 → Fail
```

Think carefully about the order of your conditions.

---

# Mini Project: Number Guessing Game

Build a simple number guessing game.

The program should:

1. Have a secret number stored in the program.
    
2. Ask the user to guess the number.
    
3. Tell them whether their guess is:
    
    - too high
        
    - too low
        
    - correct
        

Example:

```text
Guess the number: 7

Too low!
```

Another attempt:

```text
Guess the number: 13

Too high!
```

Correct:

```text
Guess the number: 10

Correct! 🎉
```

For the first version, use a fixed secret number.

Do **not** worry about random numbers yet.

That comes later.

---

# Day 2 Mastery Check

Before moving on, you should be able to explain:

1. What is a boolean? 
    
2. What does an `if` statement do? 
    
3. What is the purpose of `else`?
    
4. When would you use `else if`? 
    
5. What does `&&` mean? 
    
6. What does `||` mean? 
    
7. What does `!` do? 
    
8. What is the difference between `=` and `===`? 
    
9. What does it mean for a value to be truthy or falsy? 
    
10. Why does the order of `if / else if` conditions matter?  
    

---

# Practice Log

**Date:** #03-09-2026 

**Topics studied:**

- Boolean logic
    
- Conditional statements
    
- `if`
    
- `else`
    
- `else if`
    
- Comparison operators
    
- `&&`
    
- `||`
    
- `!`
    
- Truthy and falsy values
    

**What I understood:** Everything 

**What confused me:** The signs i kept writing "=>" which is an arrow function instead ">="

**What I struggled with:** Nothing

**What I built:** [[Simple Guessing Game]]

**What I can now do without help:** Write programs with simple conditions

**Questions to revisit:** None

---

# Key Principle

> **A conditional statement turns information into a decision.**

The program doesn't just store:

```text
age = 20
```

It can use that information:

```text
age >= 18
     ↓
   true
     ↓
execute this branch
```

This is one of the first steps from writing programs that merely **calculate** toward writing programs that actually **behave**.