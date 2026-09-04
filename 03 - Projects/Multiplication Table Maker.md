```js
  

rl.question('Enter a number: ', (num) => {

    const num1 = Number(num);

    for (i = 1; i <= 10; i++){

        console.log(num1 + ' X ' + i + ' = ' + num1*i);

    }

})
```