## Destructuring

**Destructuring helps us to breaking down a complex structure into simpler parts.** In JavaScript, this complex structure is usually an object or an array.

### Destrcturing Arrays 
Let's say we have an array with three elements:
```js
const array = [‘cat’, ‘monkey’, ‘elephant’];
```
If we wanted to assign the values to variables we should do it like this:
```js
var first = array[0];
var second = array[1];
var third = array[2];
```
But with destructuring:
```js
const [a,b,c] = array;
//a = 'cat'
//b = 'monkey'
//c = 'elephant'
```
Quite simpler and more readable, right? Great!

### Destructuring Objects
```js
const obj = {
     player: 'Steve',
     experience: 100,
     wizardLevel: false
}
```
If we had an object like the example above and we wanted to assign the properties of objects to variables, we should do it like this:
```js
const player = obj.player;
const experience= obj.experience;
let wizardLevel = obj.wizardLevel;
```
It was a lot of typing to acces these properties, uh? Well,  with destructuring assignment, the equivalent code becomes more concise and readable:
```js
const { player, experience } = obj;
let { wizardLevel } = obj;
//player= 'Steve'
//experience= '100'
//wizardLevel= 'false'
```
So much cleaner!
