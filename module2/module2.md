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