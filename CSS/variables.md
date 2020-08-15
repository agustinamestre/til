## CSS VARIABLES  

Complex web pages have huge amounts of CSS and often lots of repeating values. For example, the same color can be used in hundreds of different places. This problem was solved with the use of variables! **CSS variables allow a value to be stored in one place and then referenced in other places.** 

If somebody is asking us to make all of the buttons red instead of blue then just change the value of that CSS variable, and that’s it. You won’t have to search and replace all of the occurrences of that color. How cool is that?

### How to define and use CSS Variables 

Variables must be declared within a selector. (usually use **:root** to make the variable global). 
The name of the variable must begin with **two dashes (--)**(and is case sensitive!) 
And now, in order to use the value of the CSS variable, we can use the **var(…) function.**

Here I show you an example:
```css
:root {
--main-background-color: pink;
 --color-body: yellow;
 --color: red;
}

body {
  background-color: var(--main-background-color);
  color: var(--color-body);
}

h1, p {
  color: var(--color);
}
```
Result:

![html](https://user-images.githubusercontent.com/59721315/90304282-88323180-de8c-11ea-838f-6149b7c87220.png)

One last thing, **the standard cascade rules also apply to the CSS Variables.** So, if a variable is declared several times, the definition that is lower in the stylesheet is the one that will overwrite the others!

As we saw in the example above, all the elements of the body should be yellow, but instead, the h1s and paragraphs look red because we have used the cascade to redefine the value of the variable --color.
