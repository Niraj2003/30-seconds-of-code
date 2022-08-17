---
title: Print all divisors of number
tags: array
expertise: medium
author: niraj2003
firstSeen: 2022-08-17T05:00:00-04:00
---

The function which generates Divisors of any Integer

- Created a list of consecutive integers from 1 to ‘n’.
- For any number ‘d’, iterate through all the multiples of ‘d’ i.e., d, 2d, 3d, … etc. Meanwhile push the divisor ‘d’ for every multiples.

```js
let MAX = 1e5;
// Initialize global divisor vector
// array of sequence container
let divisor = new Array(MAX + 1);
for (var i = 1; i <= MAX; i++)
    divisor[i] = [];
   
// Sieve based approach to pre-
// calculate all divisors of number
function sieve(){
    for (var i = 1; i <= MAX; ++i) {
        for (var j = i; j <= MAX; j += i)
            divisor[j].push(i);
    }
}
   
// Utility function to print divisors
// of given number
function printDivisor(n){
    for (var div of divisor[n])
        process.stdout.write(div + " ");
}
const divisors = (n) =>
  printDivisor(n);
```

```js
divisors(10)  // 1 2 5 10 
divisors(30)  // 1 2 3 5 6 10 15 303
```
