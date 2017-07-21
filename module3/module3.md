#### Module 3: Specific HTML element targeting with CSS selectors   3.1 Introduction   Welcome to Module 3

# Welcome to Module 3

In this module, we'll learn:

* How to use classes and IDs to independently target HTML elements of the same type
* How to apply different style to the same element based on the way the user interacts with that element using pseudo-classes
* How to scope style rules using contextual selectors and the HTML inheritance structure of your document
* What the "Cascading" part of "Cascading Style Sheets" means
* 
---

#### Module 3: Specific HTML element targeting with CSS selectors   3.1 Introduction   The power of selectors

# The power of selectors

### Video: the power of selectors

[video](https://youtu.be/YemLYfI4H20)

Code mentioned in above video

```css
p {
    color: white;
    background-color: midnightblue;
    font-size: large;
}
.middle {
    color: darkviolet;
    background-color: lightgray;
    padding-left: 120px;
    padding-right: 120px;
    font-size: large;
}
#bottom {
    background-color: transparent;
    color: black;
    font-family: 'Franklin Gothic Medium';
}
```

---

#### Module 3: Specific HTML element targeting with CSS selectors   3.2 Using HTML classes and IDs   Meet IDs and classes

# Meet IDs and classes

Classes and IDs are "attribute selectors". This means that you can attach style to HTML elements based on 
that element's attributes. This empowers you to apply different style to items of the same HTML type.

### Classes

Classes are an HTML attribute that specifies a name for a group of elements on the page. You can apply 
the class name to as many elements as you like, even if they are of different HTML tag types. You can use the class name with a period in front as the selector like so:

```html
<p class="className">The intro paragraph</p>
```
**`Class` names must be single words**, but you can include digits and dashes as long as the name begins with a 
letter. Note that names are case sensitive. 

To apply a CSS rule to a class you use the class name preceeded by a period (`.`) like in the code below:

```css
.className {
    color: blue;
}
```
[Documentation](https://www.w3.org/TR/html52/dom.html#classes)

### IDs

An `ID` is an HTML attribute that specifies a name or unique identifier for a particular HTML element. They 
are like classes with a very important distinction: **the value of the ID attribute must be unique throughout 
the document**. This lets you target a single HTML element for styling. You use the name with a hashtag in 
front as the selector like so:

```html
<p id="MyFirstId"> This is an extra special paragraph </p>
```
ID names have the same rules as class names: start with a letter, can include numbers and dashes, no spaces. 
The way to create a selector for an ID is also similar to how you create a selector for a class, except you 
replace the period with a hash symbol (`#`) like in the code below:

```css
#MyFirstId {
    color: blue;
}
```
[Documentation](https://www.w3.org/TR/html52/dom.html#the-id-attribute)

https://codepen.io/techie4good/pen/PGYvRB

HTML code:

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="utf-8">
        <title>Classes and IDs</title>
        <link rel="stylesheet" href="style.css">
    </head>
    <body>
        <h1>Title</h1>
        <p id="intro">
            Classes and IDs are "attribute selectors". This means that you can attach style to HTML elements based on that element's attributes. This empowers you to apply different style to items of the same HTML type.
        </p>
        <p class="odd">
            Classes are an HTML attribute that specifies a name for a group of elements on the page. You can apply the class name to as many elements as you like, even if they are of different HTML tag types. You can use the class name with a period in front as the selector like so:
        </p>
        <p class="even">
            
Class names must be single words, but you can include digits and dashes as long as the name begins with a letter. Note that names are case sensitive. 
To apply a CSS rule to a class you use the class name preceeded by a period (".") like in the code below:
        </p>
        <p class="odd">
            An ID is an HTML attribute that specifies a name or unique identifier for a particular HTML element. They are like classes with a very important distinction: the value of the ID attribute must be unique throughout the document. This lets you target a single HTML element for styling. You use the name with a hashtag in front as the selector like so:
        </p>
        <p class="even">
            ID names have the same rules as class names: start with a letter, can include numbers and dashes, no spaces. The way to create a selector for an ID is also similar to how you create a selector for a class, except you replace the period with a hash symbol ("#") like in the code below:
        </p>
    </body>
</html>
```

CSS code:

```css
#intro {
    color: green;
}
.odd {
    color: blue;
}
.even {
    color: red;
}
```

Output:

![output](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/1a0cf9e0b83dc19c7e6fb78286ceb5bc/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/3-2_output.PNG)

---

#### Module 3: Specific HTML element targeting with CSS selectors   3.2 Using HTML classes and IDs   Activity 3.2 and discussion

# Activity 3.2 and discussion