# Map()

### The map method iterates over an array and executes a function without altering the initial array.

Consider a scenario in which we have multiple records of students and each student record has a name, ID, and marks attribute.
```js
let studentRecords = [ 
          {name: 'Anna', id: 56498, marks : 98 },
          {name: 'John', id: 12469, marks : 54 },
          {name: 'Malika', id: 26475, marks : 68 },
         ] 
```
**Problem Statement**: We are interested in retrieving only the name of the students and all the names should be in caps.

Expected Result:
```js
['ANNA', 'JOHN', 'MALIKA']
```
There are multiple ways to achieve this. Let’s go through some of them:

**Traditional for() loop**
```js
let names = [];
for (let i = 0; i < studentRecords.length; i++){
     names.push(studentRecords[i].name.toUpperCase());
}
console.log(names); // logs:['ANNA', 'JOHN', 'MALIKA']
```
**forEach() loop**
```js
let names = []
studentRecords.forEach( student => {
     names.push(student.name.toUpperCase());
})
console.log(names); // logs: ['ANNA', 'JOHN', 'MALIKA']
```

In the above-mentioned approaches, we have to first create an empty array to save our result.

 ## Solution using map() :
```js
let names = studentRecords.map( student => student.name.toUpperCase());

console.log(names); // logs: ['ANNA', 'JOHN', 'MALIKA']
```
Much simpler and easier  to read, right?

The map method does not need an auxiliary array and the use of the push method as we saw in previous examples, it is enough to store the result in a variable or constant.

### Working of map():

### **Array.map( callback, thisValue )**

map() takes two arguments, callback and optional object value.
map() executes the provided callback at each element of an array and returns the new value to the resultant array.
When thisValue is not provided, the callback function will bind itself to the object which called it. In our example “thisValue” will bind itself to “studentRecords”.

**callback** :Function that will produce an element of the new array, receives three arguments:

   **currentValue**: The current element of the array being processed.

   **index**:The index of the current element within the array.

   **array**:The array on which map is called. 

### Pro Tip:
map () always requires a **return** for its correct execution, otherwise it will return an array full of *undefined*. Knowing this can save you debugging time.


## Looping through arrays of objects

map () is a method that can iterate over any array, even arrays of objects.

**Problem Statement**: We have an array of objects that stores information about the users of an application and we want to obtain the full name of all users:

```js
const users = [
    {firstName:"Anna", lastName:"Smith", age: 32, active: true},
    {firstName:"John", lastName:"Miller", age: 52, active: false},
    {firstName:"Malika", lastName:"Jones", age: 19, active: true}
]
```
### Solution using Map() :

```js
const getFullName = users.map(user => (`${user.firstName} ${user.lastName}`));

console.log(getFullName) //output: ["Anna Smith", "John Miller", "Malika Jones"]
```
We go through the entire arrangement of objects and with the use of backticks (``) we concatenate the user's first name and last name to later display it on the screen.





