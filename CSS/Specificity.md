## CSS Specificity

Why does a code that is at the top of the style sheet apply to the one that is at the bottom? And why is it sometimes not possible to rewrite an element? The answer is: **Specificity** in CSS. 

**The specificity will determine which styles are applied over others.** Although CSS is applied from top to bottom in your style sheet, in some cases it is not enough and the more specific a selector it will “win” over others to apply.

There are three distinct categories which define the specificity level of a given selector:
1. Elements and pseudo-elements. (Score of 1)
2. Classes, attributes and pseudo-classes. (Score of 10)
3. IDs. (Score of 100)

To explain it better I will show a very simple example
As you can see in the code below, there are two styles that refer to the paragraph (the ID #paragraph and the class .paragraph), and since the class .paragraph is in last place, it should be the style that ends up being applied. But we can see that this does not happen. Why? Well, specificity comes into play here. So since an ID has more specificity than a class, the ID style is finally applied.
```html
 <p id="paragraph" class="paragraph"> Specificity Example </p>
```
In my CSS:
```css
#paragraph {
  color: yellow;
}
 
.paragraph {
  color: green;
}
```  
  Result:
  
  ![ccs1](https://user-images.githubusercontent.com/59721315/88144643-a67b7900-cbcf-11ea-8a61-ef8f9cfde002.jpg)
  

And one of the last things that I learned is that inline styles will overwrite any style from external CSS pages, so **I highly recommend not using inline styles on your web pages!.**