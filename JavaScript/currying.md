# currying

**Currying is the process of converting a function that takes multiple arguments into a function that takes them one at a time.**

The way we normally write our functions is
```js
const divisible = (num, mod) => num % mod;
```
With Currying we called the function two times with one argument at a time
```js
const divisible = num => mod => num % mod;
```
To call this function we have two options:

Pass the arguments by executing the functions:
```js
divisible(10)(2); //0
```
Pass an argument and receive a function that remembers this argument
```js
const divisibleOn3 = divisible(3);

divisibleOn3(10); //3
```

The curry function will always be returning a new function each time until *all of the arguments* were received for each invocation. These arguments are able to live throughout the lifetime of the currying through **closure** and will all be used to execute the final function.

If we call the divisible function with only one argument, for example *divisible(10)*, this would return the function *mod => num % mod*, so the operation does not happen until all the arguments are supplied. 

But clearly this in itself doesn't gain us anything. Now I will show an example where using currying is very useful.

```js
const isDivisible = divider => number => !(number % divider);

console.log(isDivisible(2)(20)); // true
console.log(isDivisible(2)(55)); // false
```
We can see that the 2 parameter could have been reused. Curried functions can be used to *compose higher order functions* and helping us reuse some parameters that are common across function calls.

```js
const isDivisible = divider => number => !(number % divider);
const isDivisibleByTwo = isDivisible(2);

console.log(isDivisibleByTwo(20)); // true
console.log(isDivisibleByTwo(55)); // false
```