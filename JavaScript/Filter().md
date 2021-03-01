# filter()

### Create a new array from an existing one by filtering the elements by a given criteria.

Every element of the array is passed to the callback function. On each iteration, if the callback returns true, then that element will be added to the new array, otherwise, it is not added to the new array.

It does not alter the original array (code immutability).


**Syntax**
```js
const newArray = array.filter(function(currentValue, index, arr);
```

**array** is the array on which the corresponding filter will be made.

**filter** is the method itself.

**currentValue** is the iterator element. (Is the only required parameter)

**index** the current position of the iterator element.

**arr** is the array to iterate over.

 ## Filter an array

Let's imagine that we have an array of vegetables and we want to filter all those that have 6 or less characters, a possible solution using filter() would be

```js
const arrayVegetables = ["Carrot", "Pumpkin", "Onion", "Tomato", "Garlic"];
const newArrayVegetales = arrayVegetales.filter (vegetable => vegetable.length <= 6);

console.log(newArrayVegetables); // output: ["Carrot", "Onion", "Tomato", "Garlic"]
```

## Filter an array of objects

Suppose we have the following arrangement

```js
const users = [
  {
    name: "Ashley",
    age: 19,
    state: false
  },
  {
    name: "Melissa",
    age: 15,
    state: true
  },
  {
    name: "Brandon",
    age: 26,
    state: true
  }
];
```
**Problem Statement:** get the data of adult users and status true

```js
const newUsers = users.filter(user=>{
  if(user.age>=18 && user.state){
    return user;
  }
});
console.log(newUsers); //output: { name: "Brandon", age: 26, state : true }
```