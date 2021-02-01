# Spread Operator

### The spread operator is a tool that lets you spread out all the elements of an array or object. This can be used to create new objects or arrays that are clones.

The spread syntax is denoted by three periods before the object. { ...obj }

Why would we use the spread operator? Well, allow me to introduce you to **immutability**. (In software development, we use the term immutable to refer to values whose state cannot change over time.)

JavaScript has a peculiar behavior when it comes to Arrays and Objects, they are mutable. This can become a big problem. Here's an example:

```js
const cat = {
  name: 'cuty patotie',
  age: 5
};

const cate2 = cat;
cat2. name = "lala";

console.log(cat); //Result: { name: 'lala', age: 5}
```
As you can see in the previous code fragment, we have an object called cat. Our cat has a name of Cutie Patotie and a age of 5.

Since we want another cat, we declare the variable cat2,  assigning our original cat as its value. And we change the name of cat2 to lala. But if we want to check the values of out original cat, we console.log and we can see that the name has changed! What hapenned here? JavaScript mutation.
Let me explain what's going on. 

When we assign an object (or an array) to a variable, a copy is not created but a reference to the original is saved, therefore, any modification in the assigned variable will also affect the original object or array.

To avoid the accidental mutation of variables, what we have to do is create a new instance of our Array/Object.  We basically create a clone. How do we achieve this? With the spread operator!
```js
const cat = {
  name: 'cuty patotie',
  age: 5
};

const cate2 = {...cat};
cat2. name = "lala";

console.log(cat); //Result: { name: 'cutie patotie', age: 5}
console.log(cat2); //Result: { name: 'lala', age: 5}
```
**But beware!** If we attempt to clone an *object that contains an array*, for example, the array inside the cloned object will contain a reference to the memory address where the original array is stored… This means that, *while our object is immutable, the array inside it isn't*.

 Here's an example:
```js
const person = {
  name: 'Mika',
  pets: ['lala', 'bobby']
};

const personClone = { ...person };
person.name = 'Chandler';
person.pets.push('lola');

console.log(personClone);// { name: 'Mika', pets: [ 'lala', 'bobby', 'lola' ] }
```
As you can see, our personClone has been cloned immutably. When we change the name property of the original person object to 'Chandler', our personClone isn't affected, its name property isn't mutated.

But when we add a new pet to the pets property of the original person object, our personClone's pets are affected by the change. Because *the pets property is a reference data type, it isn't cloned immutably.*

One of the solutions to this problem would be to use the spread operator to clone the nested properties:
```js
const person = {
  name: 'Mika',
  pets: ['lala', 'bobby']
};

const personClone = { ...person, pets: [...person.pets] };
person.name = 'Chandler';
person.pets.push('lola');

console.log(personClone); //Result: {  name: 'Mika', pets: [ 'lala', 'bobby' ] }
```


### Spread Operator also gives us the possibility to concatenate arrays or add values to a given array (or objets).
```js
const numbers = [1, 2, 3];

const newNumbers = [...numbers, 4, 5]

console.log(newNumbers) //Result [1, 2, 3, 4, 5]
```

```js
const person = {
  name: 'Mika'
};

const pets = ['lala', 'bobby'];
const personModified = pets ? { ...person, pets } : person;

console.log(personModified); //  {  name: 'Mika', pets: [ 'lala', 'bobby' ] }
```
### We can also use the spread operator to pass elements of an array as parameters of a function.
```js
var arr = [22, 3, 68, 0];

var max = Math.max(…arr);

Console.log(max)  //Result: 68
```
### The rest parameter (…)

The rest parameter can be used when destructuring. It allows us to obtain the *remaining properties in an object*, and store them in an array. 

```js
const person = {
  name: 'Mika',
  age:23,
  pets: ['lala', 'bobby']
};

const { name, ...rest } = person;

console.log(rest); //Result: { age: 23, pets:['lala', 'bobby']  }
```