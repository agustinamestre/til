# reduce()

The reduce() method executes a reducer function on each element of an array, returning a single value as a result.

### Syntax
``` js
array.reduce((acc, item, index, arr) => { body of the function }, accumulator initiator)
```
### Parameters

**Callback:** function to execute on each element of the array. Receives four parameters:

- **Accumulator**: accumulates the value returned by the callback function. It is the accumulated value returned in the last callback invocation

- **Item**: current element of the array to be iterated.

- **Index**: the index of the current element that is being processed in the array.

- **Arr**: The array on which the reduce() method was called.

In practice, almost for any case only the variables acc and item are used, so a more condensed syntax would look like this:
```js
array.reduce((acc, item) => {  body of the function }, accumulator initiator)
```

### Let's start with the most common example

We have an array of numbers and we want to add all their values.
```js
const numbers = [5,15,9,85,2];
const sum = numbers.reduce((acc, number) => acc + number);
console.log(sum); // output: 116
```

By not using an initialization value, acc = 5, as it is the first element of our array.

The iteration of the array, therefore, will start from index 1, that is, number 15.
~~~
First call
acc = 5, number= 15   //20

Second call
acc= 20, number = 9  //29

Third call
acc = 29, number= 85  //114

Fourth call
acc= 114, number= 2  //116

Return Value: 116 
~~~
The array on which reduce is called is always the object  [5,15,9,85,2]

And if we *provide an initial value*, the result would be like this:

```js
const numbers = [5,15,9,85,2];
const sum = numbers.reduce((acc, number) => acc + number, 15);
console.log(sum); // output: 131
```
~~~
First call
acc = 15, number= 5   //20

Second call
acc= 20, number = 15  //35

Third call
acc = 35, number= 9  //44

Fourth call
acc= 44, number= 85  //129

acc= 129, number= 2  //131

Return Value: 131
~~~

### Let's see another example:

Let's imagine that we have an arrangement of objects that contain food orders, then the chef asks us to indicate how many orders whose main dish is "pasta".

```js
const orders = [
   {entry: 'cucumber salad', main: 'pasta', dessert: "banana"},
   {entry: 'tomato salad', main: 'pizza', dessert: "ice cream"},
   {entry: 'simple salad', main: 'sushi', dessert: "yogurt"},
   {entry: 'simple salad', main: 'pasta', dessert: "yogurt"},
   {entry: 'tomato salad', main: 'sushi', dessert: null}
];
```
 ### Solution using reduce()

```js 
const mainPasta = orders.reduce((acc, order) => {
   if (order.main === "pasta")
     return acc + 1;
   else
     return acc;
}, 0)

console.log(mainPasta); // output: 2
```
### Another example:

Find the minimum or maximum:

```js
const numbers = [5,55,6,7,88,64,21];

const maximum = numbers.reduce((acc, number) => acc > number ? acc : number)

console.log(maximum) //88

```
```js
const numbers = [5,55,6,7,88,64,21];

const maximum = numbers.reduce((acc, number) => acc < number ? acc : number)

console.log(maximum) //5
```