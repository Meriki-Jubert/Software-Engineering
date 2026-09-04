```js
const readline = require('readline');

const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout
});

const num1 = 13;

rl.question('Guess the Number: ', (guess) => {
    const num2 = Number(guess);
    
    if (num2 === num1) {
        console.log('You guessed the number correctly');
    }
    else if (num2 > num1){
        console.log('too high');
    }
    else{
        console.log('too low');
    }
    rl.close();
});

```