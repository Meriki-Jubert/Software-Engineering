#05-09-2026 [[JavaScript - Fucntions]]
1. A Function is a block of reusable code
2. Defining the function is simply writing the logic and what the function does and calling the function, runs the code.
3. It a a variable to store values used by a function
4. It is the value a function uses
5. I enables the product of a function to be be stored in other variables
6. return allows the function to pass on it's products while console.log just prints out the function's product
7. It stops the function from running further
8. This is the accessibility of a variable across the the code
9. They help maintain code readability and avoid unnecessary lines of code
10. So as to prevent overcomplication of logic and better code understandability.
11. By dividing the problems logic into easier blocks of code
12. Yes
13. Yes
14. Because returning a value allows the value to be used by other functions and parts of the code

```js
//Exercise 1
function greet(name){
    console.log("Hello " + name);
}

greet("Jubert");
 

//Exercise 2
function add(num1, num2){
    return num1 + num2;
};

console.log(add(3, 2));


//Exercise 3
function isEven(number){
    if (number % 2 === 0){
        return true;
    }
    else{
        return false;
    }
};
  
console.log(isEven(30));

//Exercise 4
function isAdult(age){
    if (age >= 18){
        return "Adult";
    }
    else{
        return "Minor";
    }
}

console.log(isAdult(20));
  
//Exercise 5
function calculateExpense(price, quantity){
    const total = price * quantity;
    return total;
};
  
console.log(calculateExpense(500, 3));
```