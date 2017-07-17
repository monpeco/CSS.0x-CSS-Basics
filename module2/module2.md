#### Module 2: Building CSS rules   2.1 Introduction   Welcome to Module 2

# Welcome to Module 2

#### Video: Welcome to Module 2

>! Missing Video/transcrip

#### In this module, we will...

* Review the basics of HTML
* Introduce you to the anatomy of a CSS **"rule"**
* Introduce you to the concept of a **property** and give you a set of properties to get started
* Introduce you to **selectors** and how you can directly attach them to HTML tags
* Finally, for your module project, you'll get a get a chance to build the CSS for an HTML page from scratch

---

#### Module 2: Building CSS rules   2.2 HTML review   HTML to get you started

# HTML to get you started

### Video: What is HTML?

>! Missing Video/Transcript

HTML (Hyper Text Markup Language) documents are made up of content and tags. These tags describe the content so that the web browser understands the structure of the page. HTML tags typically come in pairs, an opening tag before and a closing tag after content like so:

```html
<tagname>
    My content
</tagname>
```
When these three pieces are combined (start tag, content, and end tag), you have what is called an HTML element. 

Here is a sample HTML doc:

```html
<!DOCTYPE html> <!-- Doctype declares the document to be HTML 5 type-->
<html lang="en"> <!--All your HTML content must be within this tag-->
    <head> <!--Anything in the header provides information about the document, no content here-->
        <meta charset="utf-8">
        <title>Page Title</title> <!--This text will show up on the tab of the browser for this page-->
    </head> <!--end for the header section-->
    <body> <!--start tag for the body section, this is where to put all your content to be displayed-->
        <h1>My First Heading</h1> <!--content in a h1 tag is a “heading” of the top level-->
        <p>My first paragraph.</p> <!--content in a p tag is normal or “paragraph” level text-->
    </body>
</html>
```
*NOTE: In the code above, the red text contained within the <!-- and --> start and end sequences are comments. Each of them is explaining each tag.

Tags can be nested inside of other tags. This creates a parent/child relationship between HTML elements and forms the overall structure of your HTML document into a tree. This structure has a big affect on your CSS as styles are typically inherited from parent to child. We will take a closer look at style inheritance later in this unit. 

![nested tags](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/62899e355f2553adbc85f3484da304dc/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/2-2-1_html_review.PNG)

There are other types of tags that are called "self-closing", meaning they don't come in an open/close pair. Typically self-closing tags insert content into your page as opposed to surround content. They look like this:

```html
<img src="images/pic1.png" alt="pic1" />
```
As you can see these types of tags rely on "attributes", these are added modifiers on the tag that have their own values. In the above example, we use the src attribute to set the source for the image. You will also see attributes on the start tags of tag pairs and they can include a wide variety of added functionality for a tag.

---

#### Module 2: Building CSS rules   2.2 HTML review   Common HTML tags

# Common HTML tags

There are many HTML tags to choose from depending on what elements you want to structure on your page. You can always look up HTML tags here. However, here is a [short list](https://www.w3.org/TR/2016/WD-html52-20160818/) of some of the most common HTML tags, ones you'll see us use throughout this course.

#### <html>

The root element of a document is `<html>`, and this is the first tag you'll need in your document (after the DOCTYPE, of course!). All your other HTML tags should go inside this one, meaning all HTML documents should start with `<html>` at the top and end with `</html>` at the bottom.

You'll notice in the below code that we set the language to English (`<html lang="en">`) . You can [set another language](https://www.w3.org/International/tutorials/language-decl/#Slide0140) of the text in your page using language attributes (see also [this resource](https://www.w3.org/International/questions/qa-html-language-declarations)).

It is important that you take care to use the lang attribute to indicate the actual language of text in your page because many CSS features will function differently, depending on what language is declared here.


```html
<!DOCTYPE html>
<html lang="en">
   <body>
      <p> Hello World</p>
   </body>
</html>
```
https://www.w3.org/TR/2016/WD-html52-20160818/semantics.html#the-html-element

#### <head>

This is the element that contains all the metadata for your site, such as your link to your CSS, the page's title and links to other files. This should be the first tag in your document, and there should only be one per document.

Note that this is where you will also set the charset to "utf-8" (`<meta charset="utf-8">`). This shows that you saved the markup using the UTF-8 character encoding, which has many characters outside English, so it should be able to display characters not in the English alphabet.

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="utf-8">
        <title>My First Page</title>
    </head>
    <body>
        <p> Hello World</p>
    </body>
</html>
```
https://www.w3.org/TR/2016/WD-html52-20160818/document-metadata.html#the-head-element

#### <body>

The section element that contains all the visible content for your site like your text, images, links etc. There should only be one body tag per document and it should come after the head tag.

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="utf-8">
        <title>My First Page</title>
        <link rel="stylesheet" href="styles.css">
    </head>
    <body>
        <p> Hello World</p>
    </body>
</html>
```
https://www.w3.org/TR/2016/WD-html52-20160818/sections.html#the-body-element

#### <p>

"p" stands for "paragraph" which is a block of text that is physically separated from adjacent blocks through blank lines. This is the most basic way to group text content.

```html
<p>
   This is my introductory paragraph to my Web page! This text will wrap around in a single block and then after the paragraph is done there will be a line of white space.
</p>
```
https://www.w3.org/TR/2016/WD-html52-20160818/grouping-content.html#the-p-element

#### <a>

By surrounding text with an `<a>` tag you turn it into a hyperlink. You will want to use the "href" attribute to indicate to which target the link should take the user when clicked. The default style of the a tag is to turn the text blue and underlined, and then change the color to purple after you have clicked the link. You can adjust all these styles with CSS.

```html
<a href="http://www.microsoft.com">Microsoft Main Page</a>
```
https://www.w3.org/TR/2016/WD-html52-20160818/textlevel-semantics.html#elementdef-a

#### <img />

This tag will insert an image based on the source you provide via the "src" attribute. If the source is inaccessible, you can also specify "fall back" options via the "alt" attribute. You will always want to specify the "alt" attribute with a short phrase describing the image. This text is what will be read aloud if your user is using a screen reader, or will be displayed if the user's browser will not load images. Note that this is an example of a "self-closing" tag meaning there is no closing tag, you just end the opening tag with a forward slash. 

```html
<img src="images/proPic.jpg" alt="a headshot of the instructor" />
```
https://www.w3.org/TR/2016/WD-html52-20160818/semantics-embedded-content.html#the-img-element

#### <ul> 

The UL tag creates an "unordered list" element, meaning a collection of elements in which the order is meaningless. This is a tag that sets the framework for you to add list elements inside it. You will want to add your elements within the ul tag each surrounded your content with list item or `<li>` tags like in the below example.

```html
<ul>
   <li>This is one element in the list</li>
   <li>One of the elements</li>
   <li>Another element</li>
</ul>
```
https://www.w3.org/TR/2016/WD-html52-20160818/grouping-content.html#the-ul-element

#### <ol>

The OL tag works exactly like the UL tag, except that the list element order matters. OL stands for "ordered list" and by default, the list element items are displayed with a number preceding them.

```html
<ol>
   <li>This is the first element</li>
   <li>The second element</li>
   <li>Finally, this is the third element</li>
</ol>
```
https://www.w3.org/TR/2016/WD-html52-20160818/grouping-content.html#the-ol-element

#### <br />

The br element is a self-closing tag that inserts a line break. This is most evident when placed in a block of text as it essentially represents a carriage return or hitting the "enter" key. 

```html
<p>
   this is my text.
   <br />
   this text will appear on the next line down.
</p>
```
https://www.w3.org/TR/2016/WD-html52-20160818/textlevel-semantics.html#the-br-element

<header>

The header tag is one of the section elements, it's role is to group other HTML elements according to their role on their page. The header element contains all the introductory content on the page typically a title and tagline or navigational elements. 

```html
<body>
   <header>
      <h1> Welcome to my page!</h1>
      <h2> My very first web page</h2>
   </header>
</body>
```
https://www.w3.org/TR/2016/WD-html52-20160818/sections.html#the-header-element

#### <section>

Another sectioning element, the "section" tag is a general-purpose grouping element. It most often should include a header tag at the top. This typically will come after a header tag and before a footer tag.

```html
<body>
   <header>
      <h1> My Page </h1>
   </header>
   <section>
      <h2> My Blog </h2>
   </section>
</body>
```
https://www.w3.org/TR/2016/WD-html52-20160818/sections.html#the-section-element

#### <footer>

Another sectioning element, the "footer" tag is supposed to organize the final content on the page such as the credits or contact info. 

```html
<body>
   <header>
      <h1>My Page</h1>
   </header>
   <section>
      <h2>My Blog</h2>
   </section>
   <footer>
      <p>
         copyright 2016
      </p>
   </footer>
</body>
```
https://www.w3.org/TR/2016/WD-html52-20160818/sections.html#the-footer-element

#### <div>

The div element is a generic element to hold content. It is considered a last resort, for when no other element is suitable but is often used to collect together large portions of a site that contain multiple different types of content. 

```html
<div>
   <h1> Title for Content </h1>
   <img src="images/contentImage.jpg" />
   <p> This is a paragraph explaining this section of content associated with the above image and title </p>
</div>
```
https://www.w3.org/TR/2016/WD-html52-20160818/grouping-content.html#the-div-element


---

#### Module 2: Building CSS rules   2.2 HTML review   Next steps - learn more HTML

# Next steps - learn more HTML

Note that, as this CSS Introduction course focuses on CSS, we will always provide you with the complete HTML for whatever content you will be asked to style. However, to become proficient in Web development, you are going to need a good handle on HTML. You can start by looking into some of these links:

* [Introduction section of the W3C HTML5 specification](https://www.w3.org/TR/html5/introduction.html#introduction)
* [HTML educational material for beginners](https://www.w3.org/community/webed/wiki/HTML/Training) (W3C resource)

Or of you are looking for more in-depth training, we suggest you check out one of these other W3Cx courses to better understand how to structure your pages with HTML and more:

* HTML5&CSS Fundamentals (beginner level)
* HTML5 Coding Essentials and Best Practices (intermediate level)
* HTML5 Apps and Games: Advanced Techniques (advanced level)

---

#### Module 2: Building CSS rules   2.2 HTML review   Activity 2.2 and discussion

# Activity 2.2 and discussion

Practice with HTML Validator

HTML has been available to the public since 1991, but since then a lot has changed. One of the ways to make sure your HTML is well structured and up to date is to use the W3C HTML Validator. As you are developing your pages, it's a good idea to regularly check if your HTML is written according to W3C standards.

You can find the validator here: https://validator.w3.org/

You can pass any URL on the Web into the validator, and it will tell you how the HTML for that page stacks up against Web Standards. If you pass in https://www.w3.org (the W3C's homepage), you see the following:


If you start to try out other URLs, you might find this is a very rare result ;) 
Try passing in your favorite Web address and see what comes up. For example, If you pass in https://www.microsoft.com/en-us/, you get 567 warnings and errors! 

One of the more common errors is using an HTML tag that is considered obsolete. Often the error points you to this wiki page "[Use CSS instead](https://wiki.whatwg.org/wiki/Presentational_elements_and_attributes)".

For this activity, please try out some of your favorite Web addresses in this validator and see what happens. Find a page that has one of these types of errors and answer the following questions in the discussion board:

* What URL gave you errors?
* How many warnings and errors does this site have?
* What HTML attribute does it use when it should use CSS instead?

---

#### Module 2: Building CSS rules   2.3 Building a CSS rule   The anatomy of a CSS rule

# The anatomy of a CSS rule

!> Missing Video/Transcript

### Live coding video: The anatomy of a CSS rule - Demo

!> Missing Video/Transcript

Here's the code from the video in a Code Pen for you to play around with

https://codepen.io/techie4good/pen/JXwWvr

The HTML code is shown below:

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="utf-8">
        <title>My HTML page</title>
        <link rel="stylesheet" href="style.css">
    </head>
    <body>
        <h1> Welcome to my first CSS Website</h1>
        <h2> I'm glad you're here</h2>
        <img src="designer.png" alt="designer"/>
        <p>
            This is my first site using CSS, or Cascading Style Sheets. I'm still learning and I have a long way to go, but doesn't it still look nice?
It's amazing what a different just some colors and fonts can make!
        </p>
    </body>
</html>
```
And the attached CSS file (style.css):

```css
body {
    background-color: #83AF9B;
    text-align: center;
    font-family: Arial;
    padding: 0;
    margin: 0;
}
h1 {
    background-color: #FE4365;
    color: #F9CDAD;
    font-size: 8em;
    padding: 50px;
}
h2 {
    color: #FE4365;
    background-color: #F9CDAD;
}
img {
    height: 250px;
}
p {
    background-color: #FC9D9A;
    color: white;
    padding: 50px;
    font-size: 2em;
}
```

---

#### Module 2: Building CSS rules   2.3 Building a CSS rule   Constructing your CSS rules

# Constructing your CSS rules

Here is an example CSS "rule":

```css
p {
    color: blue;
}
```
This rule tells the browser to make all text within a paragraph tag blue. A CSS rule is broken into two parts: the selector and the property

![CSS rule](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/39ef39b8e6685b816badb923520fa827/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/2-3-1_css_anatomy.PNG)

#### Selector

This is the portion of the rule before the first open curly brace ( `{` character). This is what tells the browser what HTML tags this rule 
applies to. Often, you'll just see a selector that matches an HTML tag, like in this instance- our selector is just "p". However, as we get further 
into this course, you'll find that there are many ways to target specific HTML elements and many different ways to structure selectors so that you 
are targeting exactly the part of your site you want to style.

#### Property

This is the portion of the rule between the two curly braces. This is what tells the browser how to style the HTML tag that has been selected. 
This can be as many lines of code as you choose, each of which has two parts- the property and the value you want that property to be. For our 
example, "color" is the property and "blue" is the value, but we could also have had a value of "black" or "#FFFFFF" (which is HEX code for white). 
Each property line is constructed so:

![property line](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/989b2e8ecef6fec3fcc6fd02a5baed58/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/2-3-1_property_anatomy.PNG)

The style for your page will consist of a list of many CSS rules put together. As we move through this course we will help you build up these rules to style your entire page.

---

#### Module 2: Building CSS rules   2.3 Building a CSS rule   Activity 2.3 - Building your first CSS rule set

# Activity 2.3 - Building your first CSS rule set

Now that you have a basic understanding of how to put the pieces of a CSS rule together, let's do some practice. Here is some HTML for a page you will style:

https://codepen.io/w3devcampus/pen/zovzwE

```html
<!DOCTYPE html>
<html lang="en">
   <head>
      <meta charset="utf-8">
      <title>My HTML page</title>
      <link rel="stylesheet" href="style.css">
   </head>
   <body>
      <h1>My H1 header</h1>
      <p> This is a block of text to represent a paragraph that you will want to style. This might be an explanation of of the list that follows, it is all contained within a single paragraph tag.
      </p>
      <ul>
         <li>This is list item 1</li>
         <li>Item 2 in the list</li>
         <li>The third item in the list</li>
         <li>Item 4 completes the list</li>
      </ul>
   </body>
</html>
```

Your goal is to get this HTML to look like the following image in the browser:

![how to look](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/281e5aca6aa05f7826bc32210e8200a4/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/css-intro-2-3-1-final.png)

To do so, you will need to write 4 CSS Rules. You will need to use the following 4 selectors:

* body
* h1
* p
* ul

And you will need the following properties:

* background-color: silver;
* background-color: purple;
* color: white;
* color: fuchsia; 


Now it's up to you to combine these selectors and properties into 4 rules to achieve the final style. 


```css
body {
  background-color : purple;
}

h1{
  color : white;
}

ul{
  background-color : silver;
}

p{
  color : fuchsia;
}
```

---

#### Module 2: Building CSS rules   2.4 Attaching CSS to HTML using selectors   What is a selector?

# What is a selector?

In unit 2.3, we defined a CSS selector as the portion of the CSS rule that tells the browser on which HTML element to apply the defined style.

When your HTML is simple, the selectors can be simple as well. The most basic selectors simply mirror the HTML tag. For example "p" attaches to all `<p>` tags, "img" will attach to all `<img>` tags and so on. As you can imagine, there will often be times when you don't want every single HTML element of a particular type to have identical style. In Module 3, we'll discuss a variety of ways to use selectors to attach to specific HTML elements. 

In unit 2.2, we briefly mentioned the fact that properties apply to the entire hierarchy of HTML elements to which they are attached. This means that you will have to be very careful which selectors you choose to use in combination with your chosen style. When choosing your selector you might want to keep the following aspects of an HTML element in mind:

* How many of these HTML elements are on my page? Do I want this style to apply to every one of these elements?
* What are this HTML element's children, and do I want this style to apply to them as well?
* Is this element a block element or an inline element, and does this style make sense in that context?

It is possible to independently target every HTML element on the page using selectors, but for this module we are going to stick to basics and only use selectors that match the HTML tag name. For example, here are some example selectors we'll use in this module:


```css
a {
 /* style for a tags */
}
```
This would affect the style of all link tags on the page.

```css
p {
 /* style for p tags */
}
```
This would affect the style of all paragraph tags on the page and the style of elements contained within the paragraph tag. 

```css
body {
 /* style for all elements in the body */
}
```
This would apply style to the body tag as well as allow the elements inside the body tag to inherit certain styles applied here. 

Here is a Code Pen that demonstrates how styles apply to different selectors.
https://codepen.io/techie4good/pen/pEzLrd

HTML code:

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="utf-8">
        <title>My HTML page</title>
        <link rel="stylesheet" href="style.css">
    </head>
    <body>
        <h1>Title</h1>
        <p>In unit 2.3, we defined a CSS selector as the portion of the CSS rule that tells the browser on which HTML element to apply the defined style.
            <a href="http://www.microsoft.com">Click Here!</a>
        </p>
        <ul>
            <li>When your HTML is simple, the selectors can be simple as well</li>
            <li>he most basic selectors simply mirror the HTML tag</li>
            <li>For example "p" attaches to all tags, "img" will attach to all tags and so on</li>
            <li>As you can imagine, there will often be times</li>
            <li>when you don't want every single HTML element of a particular type to have identical style</li>
        </ul>
        <p>           
In Module 3, we'll discuss a variety of ways to use selectors to attach to specific HTML elements. 
In unit 2.2, we briefly mentioned the fact that properties apply to the entire hierarchy of HTML elements to which they are attached. This means that you will have to be very careful which selectors you choose to use in combination with your chosen style 
 <br />
<a href="http://www.w3.org">Check this out</a>
It is possible to independently target every HTML element on the page using selectors, but for this module we are going to stick to basics and only use selectors that match the HTML tag name. For example, here are some example selectors we'll use in this module:
        </p>
        <ol>
            <li>This would affect the style of all link tags on the page</li>
            <li>This would affect the style of all paragraph tags on the page</li>
            <li>and the style of elements contained within the paragraph tag</li>
            <li>This would apply style to the body tag</li>
            <li>as well as allow the elements inside the body tag to inherit certain styles applied here. </li>
        </ol>
    </body>
</html>
```


```css
body {
    color: red; /* every element inherits this except those with more specific style */
}
ul {
    color: blue;/* li elements inherit this color */
}
p {
    font-style: italic; /* this even the a tags inherit within the paragraphs */
}
li {
    text-decoration: line-through; /* applies to all li elements, in both ul and ol tags */
}
```

---

#### Module 2: Building CSS rules   2.4 Attaching CSS to HTML using selectors   Inheriting style

# Inheriting style

Part of the reason a well structured HTML document is so important is because HTML elements inherit stylistic properties. 

Let's say we have an HTML document (see the corresponding Code Pen). 
https://codepen.io/techie4good/pen/mAVVkY?editors=1100#0


```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="utf-8">
        <title>My HTML page</title>
        <link rel="stylesheet" href="style.css">
    </head>
    <body>
        <header>
            <h1> Title </h1>
            <h2> sub title </h2>
        </header>
        <section>
            <p> This is my paragraph text </p>
            <ul>
                <li> list item 1 </li>
                <li> list item 2 </li>
                <li> list item 3 </li>
            </ul>
        </section>
    </body>
</html>
```
You can see it's basic structure from the way I have formatted the tags with tabbing, but here is a more visual representation of the hierarchy of tags. Tags that contain other tags are parents, and the tags inside of them are their children in the following tree representation:

![tree](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/c3441bd3d744e14d5d1c0c663d7ad1dc/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/2-4-2_inheritance_tree.PNG)

Through inheritance, CSS property values set on one element will be transferred down the tree to that element's children. In this example, every element gets the same font because we applied it to the body tag. Since the body element is a common parent for all visible elements is a convenient selector for when you want to set stylistic rules for the entire document.

Then, we applied different styles at different levels of the tree so that the "li" or list element tag ends up with three different styles (font, underline and green) without us actually applying any style directly to that tag. 


```css
body {
   font-family: "Century Gothic", sans-serif;
}
header {
   font-style: italic;
}
section {
   text-decoration: underline;
}
ul {
   color: green;
}
```
Not every property is inherited, but many are. The CSS specification tell you, for each property, whether it is inheritable. It's a good idea to keep in mind the structure of your HTML document when choosing your selectors so you can use inheritance to your advantage by applying styles to the top most element and save yourself extra CSS code.

Output:

![view](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/0eec708dce63466019c5b9d6988caa65/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/css-intro-2-4-2.png)

---

#### Module 2: Building CSS rules   2.4 Attaching CSS to HTML using selectors   Combining multiple selectors

# Combining multiple selectors

You can imagine that multiple HTML elements on your page will have similar style. If you write a separate CSS rule with the same properties for each of these elements, your CSS file can get very large and hard to manage. When designing CSS, the authors wanted to help make it as easy as possible to write and edit style sheets "by hand", so there are a number of features that help keep your styles succinct.

For example, what if you want to change the font that is consistent across many elements? You would have to change it in many places. Instead, you can combine multiple selectors on the same rule like so:


```css
p, ul, ol {
   color: blue;
   background-color: pink;
}
```
The comma means that each of these elements should have the same, duplicated style. No need to have repeated style! Of course, you could simply apply this style to an element that contains all of these, say the body element, but **not all properties are inherited** so using the comma is a direct way to apply consistent style across multiple categories of HTML elements.

Here is a Code Pen that explores using the comma to combine selectors.
https://codepen.io/techie4good/pen/RGbyLR

HTML code:

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="utf-8">
        <title>My HTML page</title>
        <link rel="stylesheet" href="style.css">
    </head>
    <body>
        <h1>Title 1</h1>
        <h2>Title 2</h2>
        <ul>
            <li>art of the reason a well structured HTML document is so important</li>
            <li>is because HTML elements inherit stylistic properties</li>
            <li>You can see it's basic structure from the way I have formatted the tags with tabbing</li>
        </ul>
        <h3>Title 3</h3>
        <ol>
            <li>but here is a more visual representation of the hierarchy of tags</li>
            <li>Tags that contain other tags are parents</li>
            <li>and the tags inside of them are their children in the following tree representation</li>
        </ol>
    </body>
</html>
```


```css
body {
    color: #660099;
}
 
h1,h2,h3 {
    font-family: Impact, sans-serif;
}
 
ul,ol {
    font-family: helvetica, sans-serif;
}
 
h2,ul {
    font-style: italic;
}
 
h3,ol {
    text-decoration: underline;
}
```
Output:

![](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/5ec613c3818f6c12089c5073749b4cbb/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/2-4-3_combining_selectors.PNG)

##Review with CH

---

#### Module 2: Building CSS rules   2.4 Attaching CSS to HTML using selectors   Activity 2.4 - Apply your own selectors

# Activity 2.4 - Apply your own selectors

Now it's your turn to practice with some selectors of your own. 

Let's say you have the following HTML and CSS (see the Code Pen with Code Stub), or see below:

See the Pen RoKLKE by W3Cx (@w3devcampus) on CodePen.

HTML code:

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="utf-8">
        <title>My HTML page</title>
        <link rel="stylesheet" href="style.css">
    </head>
    <body>
        <h1>Main Title</h1>
        <p>          
In unit 2.3, we defined a CSS selector as the portion of the CSS rule that tells the browser on which HTML element to apply the defined style. When your HTML is simple, the selectors can be simple as well. The most basic selectors simply mirror the HTML tag. For example "p" attaches to all &lt;p&gt; tags, "img" will attach to all &lt;img&gt; tags and so on. As you can imagine, there will often be times when you don't want every single HTML element of a particular type to have identical style. In Module 3, we'll discuss a variety of ways to use selectors to attach to specific HTML elements.
In unit 2.2, we briefly mentioned the fact that properties apply to the entire hierarchy of HTML elements to which they are attached. This means that you will have to be very careful which selectors you choose to use in combination with your chosen style. When choosing your selector you might want to keep the following aspects of an HTML element in mind
            </p>
            <h2>Sub Title 1</h2>
            <ul>
                <li>How many of these HTML elements are on my page?</li>
                <li>Do I want this style to apply to every one of these elements?</li>
                <li>What are this HTML element's children</li>
            </ul>
            <h2>Sub Title 2</h2>
            <ol>
                <li>and do I want this style to apply to them as well?</li>
                <li>Is this element a block element or an inline element</li>
                <li>and does this style make sense in that context?</li>
            </ol>
    </body>
</html>
```

```css
/*selector here*/  {
    background-color: #ccffcc;
    color: #336600;
}
 
/*selector here*/  {
    background-color: #336600;
    color: #ccffcc;
}
 
/*selector here*/  {
    border: 3px solid;
}
 
/*selector here*/  {
    background-color: #ffff99;
}
 
/*selector here*/  {
    text-decoration: underline;
}
```

As you can see, there is HTML and some CSS rules, but the rules are missing their selectors. 
You will need to figure out which selectors belong on top of each of the 5 rules so that your final site looks exactly like this:

![own-selector](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/7a94f41eeffe7790d4fa52b20165a4d4/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/2-4-4_sol.PNG)

HINT: Some of the rules require multiple comma separated selectors.

---

#### Module 2: Building CSS rules   2.5 Applying styles using CSS properties   What is a property?

# What is a property?

In unit 2.3, we briefly introduced you to "properties", the part of the CSS rule that tells the browser how to style specific aspects of the 
selected HTML element.

There is a huge array of different aspects you can style: color, font, size, spacing and much more! You can find the complete list of CSS 
properties at the [W3C's official site here](https://www.w3.org/Style/CSS/all-properties#list), or check out [Meiert's list here](https://meiert.com/en/indices/css-properties/).

Every property has its own collection of possible values. Some require text input, some specific keywords, some numerical input, etc.

Here are some examples of properties that each accept a different style of value:
https://codepen.io/techie4good/pen/bwbLJP

```css
body {
    background-color: purple; /* key word */
    color: #FFFFFF; /* HEX code */
    width: 60%; /* percentage */
    font-size: 20pt; /* numerical value */
}
```
Sometimes the easiest way to learn about different properties is to explore the style on one of your favorite Web sites. You can use your browser tool to inspect an HTML element. Here is an example of inspecting a title:

![the easiest way](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/93820e63bdf7f44e865bffb7126582f9/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/2-5-1_browser_tool.png)

If you are not sure how to do this, please refer to the demo in unit 1.3 to see this in action while inspecting CSS Zen Garden designs. 

As you can see, the browser tools display the value of the properties, and if you click into that space it will even give you some of the 
different value options and you can even change them and watch the Web site update dynamically. 

---

#### Module 2: Building CSS rules   2.5 Applying styles using CSS properties   Color properties

# Color properties

Color is one of the first things you'll want to explore when designing your Web site. Thankfully, CSS provides a wide array of tools for you to control the color of different HTML elements. There are basic color properties:

#### color

This property sets the foreground color of an element's text content. By default, all text content will be set to black. If you set the color on one HTML element it will be inherited by all HTML elements within that. For example, if you set the color property on the body tag to blue, all text on your web page will be changed to blue, unless that text has a more specific color property that will override it. 

[Documentation](https://www.w3.org/TR/css3-color/#foreground)

#### background-color

This property sets the background color of an element. This color then represents the exact space the element takes up, which is always a rectangular area. The default value is 'transparent' which means whatever is behind the element will shine through. Note that background-color is one example of a property that is not inherited, so you will have to directly set the background-color on each element. To set the overall color of your page, apply a background color to the body tag, and since all other element's background colors will be transparent by default, it will appear as if everything has that same background color. 

[Documentation](https://www.w3.org/TR/css3-background/#the-background-color)


#### color as a value

These color properties take in a color as their value, and there are three different ways you can define that color: **keyword**, a **HEX code** or an **rgb value**.

#### 1. keyword

Probably the simplest and least flexible way to set colors is using a keyword. A keyword is one of the predefined colors like "blue" or "green". 

```css
body {
   background-color: teal; 
}
```
There are 16 predefined colors based on keywords: aqua, black, blue, fuchsia,gray, green, lime, maroon, navy, olive, purple, red, silver, teal, yellow, white and orange. 
You can read more about these keyword colors [here](https://www.w3.org/TR/CSS22/syndata.html#value-def-color)

#### 2. HEX

A HEX code is a 6 character code to represent the color, giving you a lot more options. The 6 characters of the code are broken into 3 sets of 2, where each set of 2 represents the amount of either red, green or blue that makes up the color. These sets are hexadecimal numbers, which means that each ranges between 00 to FF where 00 means no color and FF means all of that color. Thus #000000 represents pure black and #FFFFFF represents pure white.

When using a hex code in CSS you must put a hash character in front of the 6 characters like so:

```css
body {
   background-color: #00CC00; /* green */
}
```

#### decimal

You can also specify colors using rgb in decimal form like so:
```css
body {
   background-color: rgb(0,204,0); /*same green as above*/
}
```
This will give you the same range as HEX values. This method is a less common, but it's up to you which method of specifying colors you prefer. 

[Documentation](https://www.w3.org/TR/CSS22/syndata.html#value-def-color)

Here are some of the colors you can use, and the three different ways you can set their value in the color or color-background property:

![color table](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/f3568defc277a8c99de86bd557a17f68/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/colors-rgb.png)

You can see these color properties in action using all three approaches to setting the value in this [CodePen](https://codepen.io/techie4good/pen/PGYRYL).

Other resources:

* We will discuss how to pick a good color palette for your site in Module 5, but in the mean time here is a good wiki article from the [W3C discussing the general use of colors on the Web](https://www.w3.org/wiki/Colour_theory).
* More color units are described in the [CSS3 specification](https://www.w3.org/TR/css3-color/#colorunits).

---

#### Module 2: Building CSS rules   2.5 Applying styles using CSS properties   Font properties

# Font properties

Font is an extremely important part of how you communicate content to your user. As you are likely aware there are many different aspects to 
font, and with CSS you can explicitly style each aspect. 
[Here is a quick reference for what the fonts look like with different properties](https://www.w3.org/Style/Examples/007/fonts).

#### font-family
```css
p {
   font-family: Helvetica, Verdana, sans-serif;
}
```
This property sets the font face. There are a collection of Web safe fonts that generally each browser has agreed to support, but there is an infinite number of different fonts. The problem is they might not all look the way you want them to on different browsers.

That is why this property "font-family" allows a list of fonts in the order of your preference. This comma-separated list orders your font preference from left to right. In our above example, our first choice is Helvetica, if the browser doesn't support that it will move to the next on the list, Verdana, and if it still doesn't support that it will just pick any sans-serif font it does support. You should always end your font family with fonts that are likely to be supported by the browser, this way I am guaranteed to have control over the font-family.

Something to keep in mind: some fonts have names with multiple words like `Times New Roman` or `Century Gothic`. When using these fonts you'll need to surround the entire name with quotes so the browser understands that is a single font name like so:

```css
p {
   font-family: "Times New Roman", "New Century Schoolbook", serif;
}
```
[Documentation](https://www.w3.org/TR/css-fonts/#font-family-prop       https://www.w3.org/Style/Examples/007/fonts.en.html))

#### font-size
```css
h1 {
   font-size: 2.5em;
}
```
Font-size sets the overall scale of your text. You can use a lot of different units to set the font size. Some of these units you are probably 
familiar with if you have used text editors before such as `pt` size or you can use `px` size. However, these methods are not advised because 
they are static and will not adapt based on screen size. 

The ideal way to set text size is to use `em`. **Em** is a way to set your text size based on the system settings of the device in which you 
are viewing that font. This becomes especially important for users who have special font preferences due to accessibility requirements. To use 
`em` do not set `font-size` on the body tag, but instead set the size for each element in relation to the user's default. For example, `1em` is 
the default, `2em` is twice as big, `0.5em` is half as big etc. 
[Here are some more font sizing tips and tricks](https://www.w3.org/Style/Examples/007/units.en.html).

```css

```
[Documentation](https://www.w3.org/TR/css-fonts/#font-size-prop)

#### font-style

```css
p {
   font-style: italic;
}
```
The font style property adjusts the angle of the letters in relation to the horizontal plane. Italic forms are generally cursive in nature while 
oblique faces are typically sloped versions of the regular face.

[Documentation](https://www.w3.org/TR/css-fonts/#font-style-prop)

#### text-decoration

```css
p {
   text-decoration: underline;
}
```
Text-decoration adds a line across your text. You can set this line to be underneath your text, underline, through your text, line-through, 
or on top, overline.

[Documentation](https://www.w3.org/TR/css-text-decor-3/#text-decoration-property)

#### Example:

Here is a CodePen exploring each of these styles.
https://codepen.io/techie4good/pen/ozvqxy

HTML code:

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="utf-8">
        <title>My HTML page</title>
        <link rel="stylesheet" href="style.css">
    </head>
    <body>
        <h1>Main title</h1>
        <h2>Sub title</h2>
        <p>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis lacinia consequat nibh, non commodo neque maximus semper. Vivamus non ultricies massa, vel convallis nunc. Aenean tempus risus at orci faucibus, eget hendrerit elit sodales. Quisque imperdiet diam nibh, ut semper enim dapibus et. Interdum et malesuada fames ac ante ipsum primis in faucibus. Aenean in feugiat neque. Nunc eget libero mauris. Maecenas condimentum luctus nulla.
Nulla a sem orci. Cras eget neque viverra, condimentum nulla et, tincidunt libero. In sit amet quam purus. Aliquam erat volutpat. Sed hendrerit urna quis sapien mattis dictum. Etiam vehicula tortor eu libero finibus dapibus. Mauris nunc neque, sodales nec est sed, gravida convallis sem. Nam vulputate sed est sed eleifend. Quisque sodales elit at ornare vulputate.
Morbi quis metus tortor. Cras dapibus nisl urna, et pretium risus rutrum at. Maecenas a sollicitudin elit. Ut suscipit neque ligula. Nam aliquam massa in pretium ullamcorper. Sed id nisl et mauris maximus suscipit. Suspendisse potenti. Nulla interdum, magna eu facilisis aliquam, tellus nulla luctus nisi, eu cursus magna sapien sed mi.
        </p>
    </body>
</html>
```

CSS code:

```css
body {
    font-family: Helvetica, Verdana, sans-serif;
    font-size: 12pt;
}
h1 {
    font-size: 3em;
    font-style: italic;
}
h2 {
    font-size: 2em;
    text-decoration: underline;
}
p {
    font-weight: bold;
}
```

External resources:

There are even more ways to adjust text appearance and you can read more about them here: 

* [CSS Fonts Module Level 3](https://www.w3.org/TR/css-fonts/)
* [CSS Text Decoration Module Level 3](https://www.w3.org/TR/css-text-decor/)

---

#### Module 2: Building CSS rules   2.5 Applying styles using CSS properties   Spacing properties

# Spacing properties