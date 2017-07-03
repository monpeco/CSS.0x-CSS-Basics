#### Module 1: Getting started with CSS   1.1 Introduction   Welcome to Module 1

# Welcome to Module 1


#### Module 1: Getting started with CSS   1.2 What is CSS?   Definitions

# Definitions

CSS, or Cascading Style Sheets, is a style sheet language used to describe the way an HTML or XML document should look to a user. CSS is where you specifiy the color, size, spacing, font and other visual aspects of the content that you create in your markup language document.

Most often you will see CSS used alongside HTML to describe the way a Web page looks and feels. You can have a Web page without CSS, but it would be very difficult to make it look the way you want with just HTML. This is why almost every Web page is a combination of HTML and CSS.

#### CSS • /si-ɛs-ɛs/ • noun 

Stands for "Cascading Style Sheets". A style sheet language for describing how to display an HTML document.

Sample CSS document:

```css
body {
   background-color: #d0e4fe;
}
h1 {
   color: orange;
   text-align: center;
}
p {
   font-family: "Times New Roman";
   font-size: 20px;
}
```
#### HTML • /eɪʧ-ti-ɛm-ɛl/ • noun 

Stands for "HyperText Markup Language", and it is the primary document format on the Web. It is a standardized system for tagging content on a web page so that a web browser knows how to present it properly to the viewer. It is a standardized way to describe a document's structure and the roles of the different parts of that document. 

Sample HTML document:

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="utf-8">
        <title>My HTML page</title>
    </head>
    <body>
        <p> This is an HTML document </p>
    </body>
</html>
```
#### Web page • /wɛb peɪʤ/ • noun 
A hypertext document connected to the World Wide Web.
synonyms: website, home page, landing page

#### Internet
A global system of computer networks that connect to one another so that billions of different devices all over the world can share data. The internet is a collection of smaller networks that all combined create one large, all-inclusive global network.

#### World Wide Web
A collection of documents linked together by hypertext links, addressed using Uniform Resource Locators (URLs) accessible on the Internet. The World Wide Web is an application of the internet. 
abbreviated as WWW or "the Web"

#### Web browser • /wɛb ˈbraʊzər/ • noun 
A software application for retrieving, presenting and traversing information resources on the World Wide Web.
examples: edge, chrome, Firefox, internet explorer, safari, opera

#### HTTP
Stands for "Hypertext Transfer Protocol". It is a protocol managed by the W3C to dictate the manner in which Web pages share data on the World Wide Web. You might recognize this from the start of many Web addresses.

#### HTTPS
Stands for "Hypertext Transfer Protocol Secure". It  is the secure version of HTTP, the protocol over which data is sent between your browser and the Web site that you are connected to. It means all communications between your browser and the Web site are encrypted. Some examples of sites that use HTTPS include the W3C and Microsoft Web sites: https://www.microsoft.com/ - https://www.w3.org/

---

#### Module 1: Getting started with CSS   1.2 What is CSS?   Activity 1.2 and discussion

# Activity 1.2 and discussion

Now it's your turn to do some exploration! For this activity, your job is to find examples of Web sites before and after CSS.

A great place to start is at archive.org (aka, the "WayBack machine") which stores copies of web pages throughout history. You can search for some of your favorite websites and see if they have stored copies older than 1996. You should find that any Web page made before 1996 will look very different than Web sites we typically see today. When you find a real retro gem, please share it in this week's discussion (see below).

Here's one of my personal favorite vintage sites (which is still live!): http://www.warnerbros.com/archive/spacejam/movie/jam.htm

---

#### Module 1: Getting started with CSS   1.3 Why CSS is important   Separating content from presentation

# Up until now, we have been discussing CSS's role within a Web site as the "presentation" component, but what is that and why is it so important?

From the history of CSS, we learned why CSS came about, but the short answer is simply because HTML was never designed to describe the way a Web page was supposed to look. When we use HTML for what it was intended to do, describe content, it leaves space for CSS to properly control a page's visuals. This makes it very easy to update or add content without having to even touch the style. 

#### Some benefits of CSS:

* CSS has a host of specialized tools to give you powerful control over the look and feel of your Web site, much more powerful than the tools provided by HTML.
* Designers can style many HTML pages with a single CSS document for a consistent look and feel across an entire Web page and less code to maintain.
* Separation of content and presentation makes Web site maintenance much simpler as you can address updates in isolation.
* Over time more and more devices have become internet-capable, and now there are so many different orientations in which your user can view your content. With CSS, you can specifically cater the style to each device to ensure an optimal experience.
* Some users have specific presentation needs based on personal or technological limitations or preferences. Separating content from presentation allows these users the option to control how they view content.
* Before CSS visual elements were almost always achieved with static images, which can have a big affect on network performance. CSS provides an optimized way to style your page so it can load complex visuals quickly. 

#### External resources:

* [CSS design principles](https://www.w3.org/TR/CSS22/intro.html#design-principles)
* [Effective Use of Style Sheets (updated regularly since 1997!)](https://www.nngroup.com/articles/effective-use-of-style-sheets/)
* [Repurposing of content](https://www.w3.org/People/Bos/DesignGuide/repurposing)
* 
---

#### Module 1: Getting started with CSS   1.3 Why CSS is important   Meet CSS Zen Garden

# Meet CSS Zen Garden

These videos will introduce you to a web project titled "CSS Zen Garden". You can explore the project here: http://www.csszengarden.com/

Here is a bit about the project in their own words:

> "CSS Zen Garden is a demonstration of what can be accomplished through CSS-based design. Littering a dark and dreary road lay the past relics of browser-specific tags, incompatible DOMs, broken CSS support, and abandoned browsers. We must clear the mind of the past. Web enlightenment has been achieved thanks to the tireless efforts of folk like the W3C, WASP, and the major browser creators. There is a continuing need to show the power of CSS. The Zen Garden aims to excite, inspire, and encourage participation".
> - Dave Shea, Creator of CSS Zen Garden


Video: Meet CSS Zen Garden

!> Missing video/transcrip

Live coding video: CSS Zen Garden Demo

!> Missing video/transcrip

#### View source and browser tools

In the above demo, you saw me using what is called the "developer tool" within my Edge Web browser to inspect and real-time change the style of a page's CSS. You can actually right click on any site and choose to look at the code that creates it. This feature exists in both Chrome and Firefox. Here is what I see when I right click on a Web page in my browser.

As you can see, in this right click menu, there are two options: "Inspect element" and "View source". When you select view source, you can see the HTML and CSS powering that Web page. Here is what it looks like when I view the source of W3C's Web site:

You can see a window that popped up from the bottom with all the HTML code for that site. Other Web browsers might pop this up in a separate window. 

You can also get more specific and look at individual HTML elements with the "Inspect element" option. Here is what it looks like in Edge when I inspect a specific title:

As you can see, not only is the element highlighted on the page, but this also highlights the HTML code and shows you the CSS for that element on the right-hand side. In the video above, you can see me use this view to change the CSS and HTML real-time, which can be a very convenient way to play around with your designs.

As you work in your own sites you might want to use both of these features of your browser to understand what is happening in your own code, or in Web pages you find on the internet.

---

#### Module 1: Getting started with CSS   1.3 Why CSS is important   Activity 1.3 and discussion

# Activity 1.3 and discussion

#### Activity 1.3 - CSS Zen Garden critique

Now that you’ve gotten a good idea of what CSS Zen Garden is, take a closer look. Go to http://www.mezzoblue.com/zengarden/alldesigns/ and look through the different CSS Zen Garden designs for inspiration. Which is your favorite design? Pick one design and share your critiques with the discussion. 

For your chosen design, please answer the following questions:

* What made this design stand out to you?
* What do you like best about this design?
* What is one thing you don't like about this design?
 

---

#### Module 1: Getting started with CSS   1.4 Project - your first CSS   "Hello beautiful world"

# "Hello beautiful world"

#### Video: "Hello beautiful world" Intro
!> Missing video/transcrip

#### Live coding video: "Hello beautiful world" Demo
!> Missing video/transcrip

https://codepen.io/techie4good/pen/oxQaVN

```html
<body>
    <p>
        Hello Beautiful World
    </p>
</body>
```


```css
p {
    color: blue;
    font-family:Helvetica;
}
```

---

#### Module 1: Getting started with CSS   1.4 Project - your first CSS   Comments

# Comments

As you write your CSS, you might end up with a pretty large document that can be hard to manage, or you might find yourself working on a team and having to read CSS someone else has written. In these cases, it helps to leave "notes" for the humans that read the file. 

There is a way to leave notes that the Web browser will ignore when it is reading your CSS code, they're called **"comments"**. In fact, leaving comments in your code is considered a best practice by developers and is a habit we highly recommend you develop now. 

To add comments to your CSS file, you need to surround any text you want the computer to ignore with a set of slashes and asterisks like so:

```css
/* those two symbols start my comment block
 I can have more comment text here
and the following two symbols end my comment */
```

As you can see, you can put as much text between the open and close symbols as you need, you can even have multiple lines. If you are working in an editor like Visual Studio code, you will notice that when you turn text into a comment, it turns green to indicate that the computer ignores that code.

Generally, it is a good idea to put a comment at the top of each CSS rule, or at the very least at the top of sets of rules that apply to a single category or section of your Web page. 

---

#### Module 1: Getting started with CSS   1.4 Project - your first CSS   Module 1 project - Hello your world

# Module 1 project - Hello your world