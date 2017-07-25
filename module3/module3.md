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

Here is some HTML and CSS. As you can see it's not too interesting, because not all of the styles are applied to the HTML.

```css
body {
   background-color: #00ccff;
   color: white;
   font-family: Helvetica, sans-serif;
   margin: 35px 25px 0px 25px;
}
p,h2 {
   padding: 10px;
}
.topSection{
   background-color: #3300cc;
   color: #cccccc;
}
.bottomSection {
   background-color: #cccccc;
   color: #3300cc;
}
#importantItem {
   text-decoration: underline;
   color: #99ff99;
}
#unimportantItem {
   color: gray;
}
```
https://codepen.io/techie4good/pen/VKkJYd

In this activity, your job is to add the HTML id and class attributes to the correct elements so that you get a final result that looks like this:

![activity32](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/2d0d454c1dd43e5cc10ca355082a61bc/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/3-2-2_activity.PNG)

---

#### Module 3: Specific HTML element targeting with CSS selectors   3.3 CSS pseudo-classes   Meet CSS pseudo-classes

# Meet CSS pseudo-classes

`Pseudo-classes` are a way to select HTML elements based on their state as opposed to their HTML structure. 
You can read more about pseudo-classes [here](https://www.w3.org/TR/CSS22/selector.html#pseudo-elements).

Pseudo-classes must always be applied to an existing selector. Their **flag character** is the colon (`:`), 
as you can see used in the below examples. Here are some of the most popular pseudo-classes.

### **:link** and **:visited**

```css
a:visited {
   color: gray;
   font-style: italic;
}
```
These pseudo classes are the ones you are probably most familiar with. Even on this page you've probably 
noticed that links have different style than paragraph text. The `<a>` tag by default sets the text color 
to blue with an underline, but have you ever seen a purple link? This is the `visited` pseudo-class that 
applies a different style to links that the user has already clicked. The opposite of visited is `link` 
which is a link a user has not yet clicked. These two states are mutually exclusive, meaning a link cannot 
be both at the same time.

[Documentation](https://www.w3.org/TR/CSS22/selector.html#link-pseudo-elements)

### **:hover**

```css
li:hover {
   background-color: yellow;
}
```
The hover pseudo-class is applied when the user points at an object but doesn't activate it, most commonly 
when they let their mouse cursor lay on top of an element without clicking. Some form factors don't support 
this, such as touch devices or pen surfaces. This is a really good way to encourage a user to click a link 
and you will often see it used in navigation bars. 

### **:focus**

```css
input:focus {
   background-color: blue;
}
```
The focus pseudo class is when a user has chosen to begin interacting with an element, often when the click 
into a form input such that the input is then ready to accept keyboard input.

### **:active**

```css
p:active {
   color: red;
}
```
The active pseudo-class applies when an element is activated. This happens in the time between when the user clicks their mouse and they release it.

[Documentation](https://www.w3.org/TR/CSS22/selector.html#dynamic-pseudo-classes)

https://codepen.io/techie4good/pen/RGNbdx

```html
    <!DOCTYPE html> 
<!--It's a best practice to always declare DOCTYPE!-->
    <html lang="en">
        <head>
            <meta charset="utf-8">
        </head>
<body>
  <p>Pseudo-classes are a way to select HTML elements based on their state as opposed to their HTML structure. You can read more about pseudo-classes here.

Pseudo-classes must always be applied to an existing selector. Their "flag character" is the colon (":"), as you can see used in the below examples. Here are some of the most popular pseudo-classes.
  </p>
  <a href="https://www.microsoft.com">www.microsoft.com</a>
    <br />
  <a href="http://www.w3.org">www.w3.org</a>
  <ul>
    <li>item 1</li>
    <li>item 2</li>
    <li>item 3</li>
    <li>item 4</li>
  </ul>
    <input />
</body>  
</html>

```

```css
li:hover {
  background-color: yellow;
}
a:link {
  color: green;
}
a:visited {
  color: gray;
}
input:focus {
  background-color: blue;
}
p:active {
  color: red;
}
```

---

#### Module 3: Specific HTML element targeting with CSS selectors   3.3 CSS pseudo-classes   Activity 3.3 and discussion

# Activity 3.3 and discussion

Now it's your turn to try out some pseudo classes. Here is a Web page.

See the Pen Practice with Pseudoclasses
https://codepen.io/techie4good/pen/rraNJr/

```css
body {
   background-color: #006666;
   color: white;
}
h1 {
   text-decoration: underline;
}
input {
   border: 3px white solid;
}
input {
   border: 3px yellow solid;
}
input {
   background-color: yellow;
   border: 3px yellow solid;
}
button {
   background-color: white;
   color: #006666;
   border: 3px white solid;
}
button {
   background-color: #006666;
   color: white;
}
button {
   background-color: #33cc99;
}
li {
   background-color: white;
   color: #006666;
}
li {
   background-color: #33cc99;
   color: white;
}
a {
   color: white;
}
a {
   color: #33cc99;
}
```
If you look at the CSS for this page you'll notice there are multiple CSS rules with the same selectors. 
That is because some of these rules need to have pseudo classes applied.

Please add pseudo-classes to the existing rules so that:

* The title is underlined when the user hovers their mouse over the text
* The input box gets a yellow border when the user hovers their mouse over the box
* The input box has a yellow background when the user clicks inside the box
* When the user hovers over the button it gets a background color of #006666 (dark green) and a text color of white
* When the user clicks the button it gets a background color of #33cc99 (light green)
* The background color of the list elements turns white and the text turns #006666 (dark green) when the user hover overs them
* When clicked, the list elements get a background color of #33cc99 (light green) while the text stays white
* The links at the bottom of the page start out as white in color and then when they are clicked they turn #33cc99 (light green)

The resulting output should look like this when the user has not interacted with the page in any way:

![pseudo-classes](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/17c251eec9c7e28a5214a2888df27bef/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/3-3_activity.PNG)

---

#### Module 3: Specific HTML element targeting with CSS selectors   3.4 Combining selectors   Meet contextual selectors

# Meet contextual selectors

When you use two selectors separated by a space on a rule, you scope the rule to the elements that correspond 
to the selector on the right that are INSIDE the elements that correspond to the selector on the left. Let's 
say we have the following HTML:

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="utf-8">
    </head>
    <body>
        <img src="images/pic1.jpg" alt="pic 1" />
        <p>
            This is my paragraph full of useful information
            <img src="images/pic2.jpg" alt="pic 2" />
            Since there is text around these images they should be styled a little differently.
            <img src="images/pic3.jpg" alt="pic 3" />
        </p>
        <img src="images/pic4.jpg" alt="pic 4" />
    </body>
</html>
```

If we applied the following CSS rule then the images INSIDE the paragraph would be set to a 
width of 100px, but that rule would not apply to the images outside the paragraph. 

```css
p img {
    width: 100px;
}
```
Below is a diagram of the given HTML with the two imgs that will styled by the above rule are indicated by the red arrows. 
![contextual-selector](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/8a65bf214939ba9bec2a0b48674f222b/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/3-3-1_combinging_selectors.PNG)

As your Web pages get more complex, contextual selectors become more important, because it won't scale to 
apply classes and IDs to each individual item. Contextual selection becomes especially useful when you 
structure your HTML with section tags like header, section, article and footer. 

Pay attention to the styles of the paragraphs and lists in the following example:
https://codepen.io/techie4good/pen/PGwwwo

```html
<!DOCTYPE html>
<!--It's a best practice to always declare DOCTYPE!-->
<html lang="en">
    <head>
        <meta charset="utf-8">
    </head>
  <body>
    <header>
    <h1>Title</h1>
    <ol>
      <li>Blog Post 1</li>
      <li>Blog Post 2</li>
      <li>Blog Post 3</li>      
    </ol>
    <p>
     When you use two selectors separated by a space on a rule, you scope the rule to the elements that correspond to the selector on the right that are INSIDE the elements that correspond to the selector on the left. Let's say we have the following HTML:
    </p>
    </header>
    <section>
        <h2>Blog Post 1</h2>
      <p>
        If we applied the following CSS rule then the images INSIDE the paragraph would be set to a width of 100px, but that rule would not apply to the images outside the paragraph. 
      </p>  
      <ol>
            <li>Below is a diagram of the given HTML</li>
            <li>with the two imgs that will styled by the above rule are indicated by the red arrows</li>
            <li>As your Web pages get more complex, contextual selectors become more important</li>
        </ol>
      </section>
      <section>        
        <h2>Blog Post 2</h2>
        <p>
     because it won't scale to apply classes and IDs to each individual item. Contextual selection becomes especially useful when you structure your HTML with section tags like header, section, article and footer. 
        </p>
        <ol>
            <li>Here is some code where you can see contextual selectors in action</li>
            <li>Note that there are differences between p elements and also differences between ol elements.</li>
        </ol>
    </section>
  </body>
</html>
```

```css
p {
  color: red;
}

section p {
  color: blue;
}

ol {
  list-style-type: upper-roman;
}
section ol {
  list-style-type: lower-roman;
}
```
![contextual](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/c5e971447c473f55ca8f0b39e3ab624b/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/3-4_contextual_selectors.PNG)

---

#### Module 3: Specific HTML element targeting with CSS selectors   3.4 Combining selectors   Activity 3.4.1 and discussion

# Activity 3.4.1 - Contextual selectors

For practice, we are going to learn how to better scope CSS without the crutch of classes and IDs. 

https://codepen.io/techie4good/pen/qaERNj

```html
<!DOCTYPE html>
<!--It's a best practice to always declare DOCTYPE!-->
<html lang="en">
    <head>
        <meta charset="utf-8">
    </head>
<body>
  <header>
  <h1>Title</h1>
  <p>
    When you use two selectors separated by a space on a rule, you scope the rule to the elements that correspond to the selector on the right that are INSIDE the elements that correspond to the selector on the left. Let's say we have the following HTML:
  </p>
  <ol>
    <li>Secton 1</li>
    <li>Secton 2</li>
  </ol>
  </header>
  <article>
    <h1>Section 1</h1>
    <ol>
      <li>item 1</li>
      <li>
        item 2
        <ol>
          <li> sub item 1 </li>
          <li> sub item 2 </li>
          <li> sub item 3 </li>
          <li> sub item 4 </li>
        </ol>
      </li>
      <li>item 3</li>
    </ol>
    <p>
     If we applied the following CSS rule then the images INSIDE the paragraph would be set to a width of 100px, but that rule would not apply to the images outside the paragraph. Below is a diagram of the given HTML with the two imgs that will styled by the above rule are indicated by the red arrows. 
    </p>
  </article>
    <article>
    <h1>Section 2</h1>
    <ol>
      <li>
        item 1
        <ol>
          <li> sub item 1 </li>
          <li> sub item 2 </li>
        </ol>
      </li>
      <li>item 2</li>
    </ol>
    <p>
      As your Web pages get more complex, contextual selectors become more important, because it won't scale to apply classes and IDs to each individual item. Contextual selection becomes especially useful when you structure your HTML with section tags like header, section, article and footer. 

Pay attention to the styles of the paragraphs and lists in the following example:
    </p>
  </article>
  <footer>
    <h1>Footer</h1>
    <ol>
      <li>link 1</li>
      <li>link 2</li>
      <li>link 3</li>
      <li>link 4</li>
    </ol>
  </footer>
</body>
</html>
```

```css
body {
  font-family: Tahoma, sans-serif; 
}

header, article, footer {
  border: 10px #E9B000 solid;
  margin: 30px;
}

h1 {
  color: #E86E80;
}

h1 {
  background-color: #E86E80;
  color: #FFFFFF;
}

p {
  background-color: #008F95;
  color: #FFFFFF;
}

p {
  background-color: #FFFFFF;
  color: #008F95;
}

ol {
  background-color: #E24E43;
  color: #FFFFFF;
}

ol {
  background-color: #FFFFFF;
  color: #E24E43;
}

ol {
  border: 5px solid #E24E43;
}
```


---

#### Module 3: Specific HTML element targeting with CSS selectors   3.4 Combining selectors   Cascading styles

# Cascading styles

### Video: C is for "Cascading"

https://youtu.be/A6tm_dPgzVQ

### Cascading styles

Now that you've learned all these different selectors, you've probably noticed that there is nothing preventing 
one from creating rules that overlap, meaning creating rules that apply style to the same HTML elements. In fact, 
it's very common for HTML elements on a page to have multiple CSS rules competing for importance. 

Thanks to the "cascading" part of "Cascading Style Sheets", this isn't a problem. That is because CSS has a way 
to figure out which rule "wins" when styles are conflicting. CSS actually computes a "weight" for each style rule 
and the one with the greatest weight wins. If you want all the specifics on how this weight is computed you can 
read more [here](https://www.w3.org/TR/CSS22/cascade.html). For simplicity's sake, the most specific rule wins! 

* A rule is generally more specific if it applies to a fewer number of elements than another rule that encompasses those elements. The more facets a rule has the more specific it is.
* When pseudo-classes are applied this is more specific than without the pseudo-class. For example, p:hover will win over just p. 
* Contextual selection is more specific because it scopes the rule to elements within a certain subset of those on the page. For example, a rule that applies to all the paragraphs within articles is more specific than a rule that applies to all the paragraphs on the page.
* IDs are most specific because you are directly applying them to the desired HTML element. The rule based on an ID will always win over other rules
* If two rules have the exact same weight, the one that comes later in the CSS document is what is applied.
* You can use the "!important" modifier on a CSS property so that it will guarantee that style will be applied. This is a way for you to override the calculated weight.

Look at the corresponding HTML and CSS, where code showing how Cascading order applies with many overlapping rules:

https://codepen.io/techie4good/pen/YGPNVL

```html
<!DOCTYPE html>
<!--It's a best practice to always declare DOCTYPE!-->
<html lang="en">
    <head>
        <meta charset="utf-8">
    </head>
  <body>
    <section>
      <h3>Section 1</h3>
      Now that you've learned all these different selectors, you've probably noticed that there is nothing preventing one from creating rules that overlap, meaning creating rules that apply style to the same HTML elements. In fact, it's very common for HTML elements on a page to have multiple CSS rules competing for importance.
    </section>
    <section>
      <h3>Section 2</h3>
      Thanks to the "cascading" part of "Cascading Style Sheets", this isn't a problem. That is because CSS has a way to figure out which rule "wins" when styles are conflicting. CSS actually computes a "weight" for each style rule and the one with the greatest weight wins. If you want all the specifics on how this weight is computed you can read more here. For simplicity's sake, the most specific rule wins!  
      <section>
        <h3>Section 3</h3>
        A rule is generally more specific if it applies to a fewer number of elements than another rule that encompasses those elements. The more facets a rule has the more specific it is.
        <section>
          <h3>Section 4</h3>
          When pseudo-classes are applied this is more specific than without the pseudo-class. For example, p:hover will win over just p.
        </section>
      </section>
    </section>
    <section id="section">
      <h3>Section 5</h3>
      Contextual selection is more specific because it scopes the rule to elements within a certain subset of those on the page. For example, a rule that applies to all the paragraphs within articles is more specific than a rule that applies to all the paragraphs on the page.
    </section>
  </body>
</html>
```

```css
section {
  color: red;
}
section section {
  color: orange;
}
section section section {
  color: green;
}
#section {
  color: blue;
}
section:hover {
  color: purple;
}
section:hover section:hover {
  color: pink;
}
section:hover section:hover section:hover {
  color: yellow;
}
```
![rules](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/763b325de4e1aa809898376c050a0edb/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/3-4-3_cascading.PNG)

Things to observe about the above:

* the rule based on an ID isn't even overwritten by the pseudo class
* when you hover over the sections within other sections, multiple hover rules apply!

---

#### Module 3: Specific HTML element targeting with CSS selectors   3.4 Combining selectors   Activity 3.4.2 and discussion

# Activity 3.4.2 and discussion

### Activity 3.4.2 - Cascading order

Cascading order can be difficult to manage.

Look at the corresponding some HTML and CSS:

https://codepen.io/techie4good/pen/BLypxg

```html
<!DOCTYPE html>
<!--It's a best practice to always declare DOCTYPE!-->
<html lang="en">
    <head>
        <meta charset="utf-8">
    </head>
  <body>
    <header>
      <h1>paragraph 1</h1>
      <p>
        Now that you've learned all these different selectors, you've probably noticed that there is nothing preventing one from creating rules that overlap, meaning creating rules that apply style to the same HTML elements. In fact, it's very common for HTML elements on a page to have multiple CSS rules competing for importance. 
      </p>
    </header>
    <section>
      <h1>paragraph 2</h1>
      <p>
        Thanks to the "cascading" part of "Cascading Style Sheets", this isn't a problem. That is because CSS has a way to figure out which rule "wins" when styles are conflicting. CSS actually computes a "weight" for each style rule and the one with the greatest weight wins. If you want all the specifics on how this weight is computed you can read more here. For simplicity's sake, the most specific rule wins! 
      </p>
      <article>
        <h1>paragraph 3</h1>
        <p>
          A rule is generally more specific if it applies to a fewer number of elements than another rule that encompasses those elements. The more facets a rule has the more specific it is.
When pseudo-classes are applied this is more specific than without the pseudo-class. For example, p:hover will win over just p. 
        </p>
        <h1>paragraph 4</h1>
        <p id="specific">
Contextual selection is more specific because it scopes the rule to elements within a certain subset of those on the page. For example, a rule that applies to all the paragraphs within articles is more specific than a rule that applies to all the paragraphs on the page.
IDs are most specific because you are directly applying them to the desired HTML element. The rule based on an ID will always win over other rules
        </p>
      </article>
    </section>
    <footer>
      <h1>paragraph 5</h1>
      <p>
If two rules have the exact same weight, the one that comes later in the CSS document is what is applied.
You can use the "!important" modifier on a CSS property so that it will guarantee that style will be applied. This is a way for you to override the calculated weight.
      </p>
    </footer>
  </body>
</html>
```

```css
body {
  background-color: #F8EEE7;
}
p {
  background-color: #F4DECB;
}
p {
  background-color: #94618E;
  color: #F8EEE7;
}
p {
  background-color: #49274A;  
}
p {
  background-color: #FFFFFF;
  color: #49274A;
}
p {
  background-color: #B4DBC0 !important;
  border: 2px dashed black;
}
```
As you can see, there are a lot of repeat CSS rules. For this activity, you cannot change any of the HTML 
(meaning you cannot add any IDs), but you'll need to change the CSS to make some of the rules more specific so 
that you achieve this final result:

![Activity 3.4.2](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/9900678ca1c8c341096eae766d6f2268/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/3-4-4_sol_1.PNG)

---

#### Module 3: Specific HTML element targeting with CSS selectors   3.5 Style studies   Images

# Images