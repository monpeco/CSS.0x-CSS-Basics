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