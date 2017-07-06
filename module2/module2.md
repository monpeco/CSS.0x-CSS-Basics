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
