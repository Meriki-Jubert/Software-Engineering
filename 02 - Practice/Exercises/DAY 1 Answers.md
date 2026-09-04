#02-09-2026 [[JavaScript Fundamentals Variables, Types & Operators]]
Mastery questions
===

1. A variable is a container used to store values
    
2. let can be changed in the future as the program runs while const is a constant variable
    
3. "20" is a string while 20 is a number or integer
    
4. typeof helps determine the data type stored of a value in a variable
    
5. % calculates the remainder of two numbers
    
6. === is a comparison sign used to compare values, strictly used to compare if two values are equal.
    
7. To help convert the sting input to a number
    
8. Because "5" is a string and the + sign is can be used to concatenate strings together while the - sign can not do that so the system automatically converts the string to number
    
9. It is asking for input from the user
    
10. Deciding what variables are present and each data type needed before moving to the logic


Exercises
===

```js
//Exercise 1

const name = "Jubert";

const age = 20;

const favAnime = "Naruto";

const favFootballer = "Messi";

  

console.log("Name: " + name);

console.log("Age: " + age);

console.log("Favourite Anime: " + favAnime);

console.log("Favourite Footballer: " + favFootballer);

  

//Exercise 2 same variables from exercise 1 with just new variables

const likeAnime = true;

const height = 5.7;

  

console.log(typeof name);

console.log(typeof age);

console.log(typeof favAnime);

console.log(typeof favFootballer);

console.log(typeof likeAnime);

console.log(typeof height);

  

//Exercise 3

let balance = 5000;

let food = 500;

let transport = 800;

  
  

let totalExpenses = food + transport;

let newBalance = balance - totalExpenses;

let isGoodBalance = newBalance >= 3000;

  

console.log("Total Expenses: " + totalExpenses);

console.log("New Balance: " + newBalance);

console.log("Is Balance at least 3000?: " + isGoodBalance);

  

//Exercise 4

const readline = require('readline');

  

const rl = readline.createInterface({

    input: process.stdin,

    output: process.stdout

});

  

rl.question('Enter your name: ', (name) => {

    rl.question('Enter your age: ', (age) => {

        rl.question('How many years into the future? ', (years) => {

            const futureAge = Number(age) + Number(years);

            console.log('Hello ' + name);

            console.log('In ' + years + ' years, you will be ' + futureAge + ' years old');

            rl.close();

        });

    });

});
```