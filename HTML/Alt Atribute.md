## Adding Alt Text To An Image

Sometimes it can happen that an image cannot be displayed. There can be several reasons (Due to an old browser, slow connection, an error in the src attribute, etc...)

To solve this problem, if an image is not displayed, a good practice that we can apply is the **ALT attribute**, which will provide *alternative text* (image description) instead of the image.

Code Example without Alt attribute
```html
<img src="giraffe.jpg"/>
```
![notimage](https://user-images.githubusercontent.com/59721315/88453468-818c3d80-ce3d-11ea-8547-0da1e58184be.jpg)

Code with Alt attribute
```html
<img src="giraffe.jpg" alt="Giraffe" />
```
![textalternative](https://user-images.githubusercontent.com/59721315/88453493-c57f4280-ce3d-11ea-8e83-e2d70b010339.jpg)


The alt description is also very helpful for users with visual disability. So, we can make images more accessible *for everyone* by providing the alternative text!
