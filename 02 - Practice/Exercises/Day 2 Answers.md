#03-09-2026 [[JavaScript - Conditional Statements]]
1. A boolean is a variable that can only stores 2 values, either True or false
2. I checks if a conditions has been met before executing a block of code
3. This runs if the condition of the if statement has not been met
4. This adds other conditions for other code blocks to run if met
5. This is the 'AND' symbol, and it makes sure that all conditions are met before code executes
6. This is the 'OR' symbol it makes sure that at least one condition has been met before running a code block
7. This is a 'NOT' symbol it check if a condition is not met before a code block runs
8. '=' is used to assign values to variables and the '=== ' used to compare if two values are equal 
9. A truthy value is a value with weight like a full string and falsy value are mainly empty values like 0, null
10.  The order of if / else if conditions matters because the conditions are evaluated top-to-bottom, and the first true condition “wins”, its block runs and the rest of the chain is skipped.

```js
//Exercise 1
const readline = require('readline');
const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout
});
  
rl.question('Enter your age: ', (age) => {
    const ageNum = Number(age);
    if (ageNum >= 18){
        console.log('You are Eligible');
    }
    else{
        console.log('You are not Eligible');
    }
    rl.close();
});

//Exercise 2
rl.question('Enter a Number: ', (num) => {
    const num1 = Number(num);
    if (num1 > 0){
        console.log('The number is Positive');
    }
    else if (num1 < 0){
        console.log('The number is Negative');
    }
    else{
        console.log('The number is Zero');
    }
    rl.close();
});

//Exercise 3
const password = "Jubert123";
const username = "Jubert";

rl.question('Enter username: ', (user) => {
    rl.question('Enter password: ', (pass) => {
        if (user === username && pass === password){
            console.log('Login Successful');
        }
        else {
            console.log('Login Failed');
        }
        rl.close();
    });
});

//Exercise 4
rl.question('Enter your Grade: ', (grade1) => {
    const grade = Number(grade1);
    if (grade >= 80){
        console.log('Excellent');
    }
    else if(grade >= 60 && grade <= 79){
        console.log('Good');
    }
    else if(grade >= 50 && grade <= 59){
        console.log('Pass');
    }
    else{
        console.log('Fail');
    }
    rl.close();
});
```