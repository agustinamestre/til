## Closures

**A closure allows the scope of a parent function to be accessed from a child function.** In JavaScript, closures are created every time a function is created. 

-Here is an example:
```js
const first = () => {  //parent function
  const greet = "Hello";
  const second = () => { //child function
    console.log(greet);
  }
  second();
}
first();  
```
The first() function creates a local variable called greet and an internal function called second().

Second() is an internal function, so is only available inside first().

Since the inner functions have access to the variables of the outer functions, second() can access the variable name declared in the first() function.

Result:

![closure](https://user-images.githubusercontent.com/59721315/92328621-6580dc00-f038-11ea-8b70-022216aabfbd.png)

-Another example
```js
const first = () =>  {
  const greet = "Hi";
  const second = () => {
    console.log(greet);
  }
  return second;
}

const newFunc = first();
newFunc();
```
So much similar to the example above, uh? But what makes it different is that the second() inner function is returned from the outer function *before being executed!*

The solution to this puzzle is that newFunc has become a closure. **A closure is a special type of object that combines two things: a function, and the environment in which that function was created.**

The environment is made up of local variables that were in scope at the time the closure was created. In this case, newFunc is a closure that incorporates both the second() function and the string "Hi" that existed when the closure was created.

So, for this reason, when we call to newFunc() the variable greet remains available for use, and "Hi" is printed on the console.

Result:

![closure2](https://user-images.githubusercontent.com/59721315/92329698-80a31a00-f03f-11ea-8090-c032f92a2e90.png)