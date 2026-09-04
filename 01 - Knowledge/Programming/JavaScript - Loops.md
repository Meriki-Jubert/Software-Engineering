
# Overview

So far, programs have mostly executed instructions once:

```text
Input → Process → Output
```

Conditionals allowed the program to choose between different paths.

Loops add another ability:

> **Repeat a block of code while a condition or rule says to continue.**

Loops are useful whenever a program needs to perform an operation multiple times.

Examples:

- counting numbers
    
- processing items
    
- repeatedly asking for input
    
- searching through data
    
- calculating totals
    
- displaying menus
    
- performing an operation until a condition changes
    

---

# 1. The `for` Loop

A `for` loop is useful when you generally know how many times you want something to happen.

Basic structure:

```js
for (initialization; condition; update) {
    // code to repeat
}
```

Example:

```js
for (let i = 1; i <= 5; i++) {
    console.log(i);
}
```

Output:

```text
1
2
3
4
5
```

### The three parts

```js
for (let i = 1; i <= 5; i++)
```

### Initialization

```js
let i = 1
```

Creates the counter and gives it its starting value.

### Condition

```js
i <= 5
```

The loop continues while this is `true`.

### Update

```js
i++
```

Increases `i` by 1 after each iteration.

---

# 2. Iteration

One execution of a loop is called an **iteration**.

For:

```js
for (let i = 1; i <= 3; i++) {
    console.log(i);
}
```

There are three iterations:

```text
Iteration 1 → i = 1
Iteration 2 → i = 2
Iteration 3 → i = 3
```

After `i` becomes `4`, the condition:

```js
i <= 3
```

is false, so the loop stops.

---

# 3. Counters

A counter keeps track of how many times something has happened.

Example:

```js
let count = 0;

for (let i = 1; i <= 5; i++) {
    count++;
}
```

After the loop:

```text
count = 5
```

Counters are extremely common in programming.

---

# 4. Accumulators

A counter counts.

An **accumulator** collects a running result.

Example:

```js
let total = 0;

for (let i = 1; i <= 5; i++) {
    total = total + i;
}
```

The value changes after each iteration:

```text
0
0 + 1 = 1
1 + 2 = 3
3 + 3 = 6
6 + 4 = 10
10 + 5 = 15
```

Final result:

```text
15
```

A common shorthand is:

```js
total += i;
```

which means:

```js
total = total + i;
```

---

# 5. The `while` Loop

A `while` loop repeats code **while a condition remains true**.

Basic structure:

```js
while (condition) {
    // code
}
```

Example:

```js
let count = 1;

while (count <= 5) {
    console.log(count);
    count++;
}
```

Output:

```text
1
2
3
4
5
```

The important difference is that you manage the initialization and update yourself.

---

# 6. `for` vs `while`

A useful mental model:

### Use `for`

When you know or can naturally describe the number of repetitions.

```js
for (let i = 0; i < 10; i++) {
    // repeat 10 times
}
```

### Use `while`

When repetition depends more naturally on a condition.

```js
while (password !== correctPassword) {
    // keep asking
}
```

This isn't an absolute rule. Both can often accomplish the same task.

The goal is to understand **why one makes the problem clearer**.

---

# 7. The `do...while` Loop

A `do...while` loop is similar to `while`, but with one important difference:

> **The code runs at least once before the condition is checked.**

Structure:

```js
do {
    // code
} while (condition);
```

Example:

```js
let number;

do {
    number = 5;
    console.log(number);
} while (number < 3);
```

The code still runs once even though `5 < 3` is false.

Compare:

```js
while (number < 3) {
    // may never run
}
```

with:

```js
do {
    // runs at least once
} while (number < 3);
```

---

# 8. Looping with Conditions

Loops and conditionals can work together.

Example:

```js
for (let i = 1; i <= 10; i++) {
    if (i % 2 === 0) {
        console.log(i);
    }
}
```

The loop handles repetition.

The `if` decides what to do during each iteration.

Output:

```text
2
4
6
8
10
```

This combination is extremely important.

---

# 9. `break`

`break` immediately stops a loop.

Example:

```js
for (let i = 1; i <= 10; i++) {
    if (i === 5) {
        break;
    }

    console.log(i);
}
```

Output:

```text
1
2
3
4
```

When `i` becomes `5`, `break` ends the loop.

Use it when continuing the loop no longer makes sense.

---

# 10. `continue`

`continue` skips the current iteration and moves to the next one.

Example:

```js
for (let i = 1; i <= 5; i++) {
    if (i === 3) {
        continue;
    }

    console.log(i);
}
```

Output:

```text
1
2
4
5
```

The loop itself continues, but the iteration where `i === 3` is skipped.

---

# 11. Infinite Loops

A loop must eventually have a way to stop.

This is dangerous:

```js
let count = 1;

while (count <= 5) {
    console.log(count);
}
```

`count` never changes.

Therefore:

```text
count <= 5
```

always remains true.

The loop never ends.

This is called an **infinite loop**.

When writing a loop, always ask:

> **What changes that will eventually make my condition false?**

---

# 12. Nested Loops

A loop can exist inside another loop.

Example:

```js
for (let i = 1; i <= 3; i++) {
    for (let j = 1; j <= 2; j++) {
        console.log(i, j);
    }
}
```

The inner loop completes its repetitions for every iteration of the outer loop.

Conceptually:

```text
i = 1
    j = 1
    j = 2

i = 2
    j = 1
    j = 2

i = 3
    j = 1
    j = 2
```

Nested loops are useful for things like grids, tables, patterns, and multidimensional data.

They can also become expensive if used carelessly.

---

# 13. Loops as a Problem-Solving Tool

When you encounter a problem, look for repetition.

Ask:

> **What needs to happen more than once?**

For example:

> "Print all numbers from 1 to 100."

The repeated operation is:

```text
print a number
```

A loop is appropriate.

Another:

> "Keep asking the user for a password until they enter the correct one."

The repeated operation is:

```text
ask for password
```

A `while` or `do...while` loop may be appropriate.

---

# 14. Common Mistakes

### Mistake 1: Forgetting the update

```js
while (count < 10) {
    console.log(count);
}
```

If `count` never changes, the loop may never stop.

---

### Mistake 2: Off-by-one errors

Consider:

```js
for (let i = 0; i < 5; i++)
```

This runs with:

```text
0
1
2
3
4
```

That's **5 iterations**, not 6.

Pay attention to `<` versus `<=`.

---

### Mistake 3: Changing the wrong variable

```js
let count = 1;

while (count <= 5) {
    console.log(count);
    total++;
}
```

If `count` never changes, the condition never changes.

---

### Mistake 4: Creating an unnecessary loop

Not every repeated-looking task needs a loop.

First identify:

1. What is being repeated?
    
2. How many times?
    
3. When should repetition stop?
    
4. What changes after each iteration?
    

---

# 15. Mental Model

Think of a loop as a question being asked repeatedly:

```text
        ┌───────────────┐
        │ Is condition  │
        │    true?      │
        └───────┬───────┘
                │
          Yes   │   No
           ↓   │    ↓
      Run code │   Stop
           │
           ↓
      Update state
           │
           └──────────→ Ask again
```

The important concept is:

> **A loop repeatedly executes code while its stopping condition has not been reached.**

---

# Practice

## Exercise 1: Count to 10

Use a `for` loop to print:

```text
1
2
3
...
10
```

---

## Exercise 2: Even Numbers

Use a loop to print every even number between 1 and 20.

Expected output:

```text
2
4
6
...
20
```

---

## Exercise 3: Sum of Numbers

Calculate the sum of numbers from 1 to 100.

Expected result:

```text
5050
```

Do not manually calculate it and print `5050`.

Make the program calculate it.

---

## Exercise 4: Countdown

Use a loop to print:

```text
10
9
8
...
1
Blast off!
```

---

## Exercise 5: Password Attempts

Create a program that repeatedly asks the user for a password.

The correct password is:

```text
javascript123
```

Keep asking until the user enters the correct password.

When they succeed:

```text
Access granted.
```

Think about which type of loop makes the most sense.

---

# Day 3 Mini Challenge

Create a program that asks the user for a number and then prints its multiplication table from 1 to 10.

Example:

```text
Enter a number: 7

7 x 1 = 7
7 x 2 = 14
7 x 3 = 21
...
7 x 10 = 70
```

Requirements:

- use user input
    
- convert the input to a number
    
- use a loop
    
- calculate each result
    
- don't manually write ten separate calculations
    

---

# Mastery Check

Before considering loops understood, you should be able to explain:

1. What a loop is.
    
2. What an iteration is.
    
3. The three parts of a `for` loop. 
    
4. The difference between `for` and `while`. 
    
5. Why a loop can become infinite. 
    
6. What a counter is. 
    
7. What an accumulator is. 
    
8. What `break` does.
    
9. What `continue` does. 
    
10. Why `i < 5` and `i <= 5` produce different numbers of iterations. 
    

---

# Learning Principle

Don't memorize loop syntax in isolation.

When facing a problem, identify:

```text
What repeats?
        ↓
How many times / until when?
        ↓
What changes each time?
        ↓
What condition stops the repetition?
```

Then choose the loop.

> **Good programmers don't use loops because they know loops. They recognize when repetition exists inside a problem.**

---

# Practice Log

**Date:**  
**Topics studied:**  
**Exercises completed:**  
**What I understood:**  
**What confused me:**  
**What I struggled with:**  
**What I can now do independently:**  
**Questions for later:**