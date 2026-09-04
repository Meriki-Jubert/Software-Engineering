#04-09-2026 [[Day 3]] [[JavaScript - Loops]]
1. A block of code that runs until a particular condition is met
2. The number of times a loop runs 
3. Initialization, Condition and Update
4. For loop is used when the exact number of iterations are known and the while loop is used when the number of iteration required are unknown.
5. When the condition for it to stop is not defined or can not be met
6. A counter is a variable that stores the number of iterations a loop has run
7. An accumulator is a variable that collects results of a loop
8. It forces the loop to end
9. It skips an iteration in a loop
10. Because the loop ends when i<5 and does not include 5 in the results because 5 is not less than itself while i<=5 includes 5 in the results because 5 meets it's conditions.

```js
//Exercise 1
for (i = 1; i<=10; i++){
    console.log(i);
};
  
//Exercise 2
for (i = 1; i<=20; i++){
    if (i % 2 === 0){
        console.log(i);
    };
};
  
//Exercise 3
total = 0;
  
for (i = 1; i<=100; i++){
    total += i;
};
console.log(total);
  
//Exercise 4
i = 10;
  
while(i >= 1){
    console.log(i);
    i--;
};

//Exercise 5
const readline = require('readline');

const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout
});

/*const password = "javascript123";
let pass;
while(pass !== password){
    rl.question('Enter Your Password: ', (input) => {
        pass = input;
        if (pass !== password){
            console.log('Access Denied');
        }
        else{
            console.log('Access Granted');
            rl.close();
        }
    });
}*/
  
// Mini Challange
  
rl.question('Enter a number: ', (num) => {
    const num1 = Number(num);
    for (i = 1; i <= 10; i++){
        console.log(num1 + ' X ' + i + ' = ' + num1*i);
    }
})
```
```