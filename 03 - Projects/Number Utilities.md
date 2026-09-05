```js
//Mini-Project
const readline = require('readline');
  
const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout
});
  
rl.question('Enter Number 1: ', (num1) => {
    rl.question('Enter Number 2: ', (num2) => {
        const number1 = Number(num1);
        const number2 = Number(num2);
        function add(a, b){
            return a + b;
        };
        function substract(a, b){
            return a - b;
        };
        function multiply(a, b){
            return a * b;
        };
        function divide(a, b){
            if (b === 0){
                console.log("Cannot divide by 0");
            }
            else{
                return a/b;
            }
        };
        function isEven(a, b){
            if (a % 2 === 0 && b % 2 === 0){
                return a + " and " + b + " are Even numbers";
            }
            else if (a % 2 === 0 && b % 2 !== 0){
                return a + " Is Even and " + b + " is Odd";
            }
            else if(a % 2 !== 0 && b % 2 === 0){
                return a + " Is Odd and " + b + " Is Even";
            }
            else{
                return "They are both Odd";
            }
        };
        function classifyNumber(a, b){
            if(a > 0 && b > 0){
                return "They are both Positive Numbers";
            }
            else if(a > 0 && b < 0){
                return a + " Is a Positive Number and " + b + " Is negative Number";
            }
            else if(a < 0 && b > 0){
                return a + " Is a Negative Number and " + b + " Is Positive Number";
            }
            else if(a === 0 && b < 0){
                return a + " Is Zero and " + b + " is Negative";
            }
            else if(a === 0 && b > 0){
                return a + " Is Zero and " + b + " is Positive";
            }
            else if(a < 0 && b === 0){
                return a + " Is a Negative Number " + b + " is Zero";
            }
            else if(a > 0 && b === 0){
                return a + " Is a Positive Number " + b + " is Zero";
            }
            else{
                return "They are both Negative Numbers";
            }
        }
        console.log(add(number1, number2));
        console.log(substract(number1, number2));
        console.log(multiply(number1, number2));
        console.log(divide(number1, number2));
        console.log(isEven(number1, number2));
        console.log(classifyNumber(number1, number2));
        rl.close();
    });
});
```
```