I needed to change the color of some paragraphs on my web page. How I made it? Well, first of all I went to the HTML document and **added classes on the p tags that I wanted to styled it**. Then in the CSS file I used those classes and attached to them the color that I wanted.

Here's an example:

```
<body>
	<h1>Hello</h1>
	<p class="red">example of changing paragraph color</p>
	<p>example of changing paragraph color</p>
	<p class="blue">example of changing paragraph color</p>
</body>
```
In my CSS:

```
.red{
	color: red;
}

.blue{
	color:blue;
}
```
Result:

![color](https://user-images.githubusercontent.com/59721315/87748429-397d7300-c7cc-11ea-8490-ff3891efe7fd.jpg)
