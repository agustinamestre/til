## Linear Gradients 

*We can use the **linear-gradient** function to style a cool background with a linear gradient between two (or more) colors*.

To create a linear gradient, you set a direction and you must also specify at least two colors in which the effect will be applied.


The following example shows a linear gradient that goes **top to bottom** (this is default):

![top to bottom](https://user-images.githubusercontent.com/59721315/88475789-7b639300-cf09-11ea-86da-c66c310e057d.png)

Here is what the CSS looks like:
```css
body {
  background: linear-gradient(red, pink, yellow);
}
```


In this other example, the transition is from **left to right**:

![linear gradient](https://user-images.githubusercontent.com/59721315/88475744-20ca3700-cf09-11ea-978e-4149398dd8e7.png)

CSS:
```css
body {
  background: linear-gradient(to right, red, pink, yellow);
}
```


You can also make a **diagonal gradient** by specifying the vertical and horizontal starting position. For example:

![diagonal](https://user-images.githubusercontent.com/59721315/88476094-fe85e880-cf0b-11ea-8612-b23ef8d9d7fd.png)

CSS:
```css
body {
 background: linear-gradient(to bottom right, red, pink, yellow);
}
```


And and if you want more control over the direction of the gradient, you can define an **angle**. For example:

![angle](https://user-images.githubusercontent.com/59721315/88476241-5113d480-cf0d-11ea-8a45-700c0984932f.png)

CSS:
```css
body {
 background: linear-gradient(103deg, red, pink, yellow);
}
```



If you need more information, you can go to [CSS Gradients](https://www.w3schools.com/css/css3_gradients.asp)!




