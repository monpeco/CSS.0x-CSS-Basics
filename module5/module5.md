#### Module 5: Designing your Web site for your audience   5.1 Introduction   Welcome to Module 5

# Welcome to Module 5

In this module, we'll...

Learn how to apply basic design principals based on the context of your HTML elements
Explore CSS and HTML's accessibility features and how you can design your page to accommodate a diverse audience
Introduce you to features to help internationalize your page and make it easier for those viewing it in different languages
Discuss the lessons learned from historical Web design trends and give you the new tech we use instead
Meet the newest fashions in Web design to help you give your Web pages a modern look and feel

---

#### Module 5: Designing your Web site for your audience   5.1 Introduction   The importance of design

#   The importance of design

### Web stats

Numerous studies have been done to determine exactly how important Web design is. Here are a few interesting stats to guide you:

38% of people will stop engaging with a website if the content/layout is unattractive (see [source](http://wwwimages.adobe.com/content/dam/Adobe/en/max/2015/pdfs/state-of-content-oct.pdf) - pdf file),
2 out of every 3 minutes spent on the Web are via a mobile device (see [source](https://www.comscore.com/Insights/Presentations-and-Whitepapers/2016/2016-US-Cross-Platform-Future-in-Focus))

---

#### Module 5: Designing your Web site for your audience   5.1 Introduction   CSS best practices

# CSS best practices

CSS best practices

You will find below an excerpt of CSS best practices (see the full slide set) that were written by  Elika J. Etemad (also known as fantasai). Elika is an expert on the W3C CSS Working Group (since 2004!) and a longtime contributor to the Mozilla Project. In addition to editing many of the CSS3 specifications, she’s worked on layout engine testing and development for Gecko and managing the CSS test suites at W3C.

### Executive summary

* Logical source order: 

The order of the HTML content should make sense even without the CSS: for accessibility, mobile optimization, device adaptability, and long-term maintainability.

* Liquid layouts and relativity: 

Use smart relative sizing: to optimize layouts while minimizing media query code forks.

* Media queries: 

Adapt to screen size changes; get font size adaptation free by using ems.

* Prevent zombie code:

Dead code may come alive as CSS changes. Delete it before it does, and ruins your layout.

* Test in multiple browsers: 

Your favorite browser is not always right.

* Don't use proprietary features!

Keep the Web open to everyone! Don't rely on the latest -WebKit- invention.

* Turn off CSS:

A well-coded page will be understandable without it.

### Foundations

* Indent your code for readability ease
* Learn how to code CSS before relying on frameworks (such as Bootstrap, etc.)
* Separate content and style
  * Use semantic markup, ie., "classes for meaning, not for show". 
  * The following article is helpful to understand this concept: Meaningful CSS: Style Like You Mean It (Tim Baxter, May 2016 - A list apart). It is also fully described in the HTML5&CSS Fundamentals course.
* Use `<table>` for tabular data: don't use tables for layout, but if your content is tabular like a catalog, a calendar, or a price list, then the table element is the correct markup.
* Linearized logical source order
* The order of the HTML content should make sense even without the CSS. 
* Benefits are numerous as it works best:
* for long-term site maintainability
* for mobile
* for accessibility
* as a foundation for device adaptation (media queries)
* Linguistic variations: set the language correctly for better typography (see the section entitled "why Internationalization is important")

### Testing

* Test without CSS: turn off CSS, and if the page makes no sense, fix your markup.
* Test in multiple environments:

* Resize the window
* Zoom the text
* Try a mobile browser
* Navigate by keyboard
* Test in multiple browsers: remember that just testing in Chrome does not work for everyone!  ;)

### Adaptability

* Media queries: set media query breakpoints in em or ch, not always in px.
* Liquid layouts and relativity: what is your sizing based on?
* Containing block size? → Use percents.
* Viewport size? → Use viewport units: vw, vh, vmin, vmax
* Font height? → Use em or rem.
* Font pitch? → Use em or ch.
* Content size? → Use auto or min-content/max-content.
* Combination of the above? → Use the appropriate layout formulas: flex, min-width, max-width, etc.
* Absolute units are usually the wrong answer.

### Defensive Coding

* !important means never override- to use with caution
* Use !important to define overriding rules, not for fixups
* Duplicate selectors if you need to increase specificity, or
* Simplify selectors if you need to decrease specificity
* Don't over-escalate: understand your code, and don't overkill.
* For example, avoid:
        . z-index: 9999999999999999999999999999999999999;
        . position: absolute; left: -10000000000px

* Drop dead code: you tried something and it didn't work? Delete it right away!
* Code to Standard
* Don't rely on proprietary extensions
* Don't use experimental features in production or commit to keeping up-to-date.
* Provide fallbacks / use @supports.

---

### Module 5: Designing your Web site for your audience   5.1 Introduction   The W3C CSS WG

# The W3C CSS WG

The W3C CSS Working Group

The CSS Working Group (Cascading Style Sheets Working Group) is a working group created by the W3C in 1997 to tackle issues that had not been addressed with CSS level 1. The number of members reaches 125 in April 2017!

The CSS WG meeting in Lisbon, November 2016. The working group is co-chaired by Rossen Atanassov and Alan Stearns. (Photo credit: Marie-Claire Forgue)
The CSS WG members are working on a whole range of specifications, but their core document is CSS snapshot 2017. This document collects together into one definition all the specs that together form the current state of Cascading Style Sheets (CSS) as of 2017. The primary audience is CSS implementers, not CSS authors, as this definition includes modules by specification stability, not Web browser adoption rate.

---

#### Module 5: Designing your Web site for your audience   5.2 The basics of design   Applying basic design principals

# Applying basic design principals

Often it's hard to pull apart the pieces of a design that are "good" or "bad", most of that is subjective. Instead, it's better to think of individual pieces of a design as "effective" or "ineffective" according to the demographic and the task they are trying to achieve. 

Web sites can become pretty complicated if you add many design elements, and it can be intimidating to figure out how to get started when thinking about how to present your Web page. One of the best ways to get started is to think about each of the individual HTML elements we've learned how to style so far, and how to style according to your specific goals. 

In this module, we'll discuss how to style the three most fundamental design aspects of a Web page: typography, color, and white space.

---

#### Module 5: Designing your Web site for your audience   5.2 The basics of design   Typography

# Typography

A good rule of thumb when designing your Web site is to use no more than two different typefaces per page. Typically 
this means that you select 1 bold typeface for titles or other eye-catching pieces of text, and a neutral typeface 
for large blocks or the body text of your page. 

There is no official taxonomy of fonts, and not all browsers support all fonts, so it can be difficult to get your 
font looking exactly the way you want on all platforms. While you're starting out, it's best to stick to the most 
popular and commonly used fonts. [Here is a good list](https://www.w3.org/Style/Examples/007/fonts.en.html) of fonts for English pages and the appropriate fall-backs to 
get you started. On the Web, you can find other lists of available system fonts for non-Latin scripts, such as [this 
one](https://r12a.github.io/scripts/fontlist/).

As you get more comfortable, you can branch out to more exotic fonts. Remember that, when you are building your 
font-family set, you will want to always include a Web safe font alternative for an exotic font in case the user's 
device doesn't support it. 

```css
body {
   font-family: "Segoe UI", Helvetica, sans-serif;
}
```
When choosing your font, probably the biggest choice you'll make is what category of font to use. There are 5 basic categories of font: 

![](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/f5e20435f76b92b0a061c54c18a06264/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/5-2-2_font_categories.PNG)

* sans-serif - These are the most popular fonts for Web pages. This means the letters do not have added flourishes, so the typefaces are simpler. Their simplicity makes them easier to display on computer screens as their resolution is much lower than a printed document. It is often suggested you choose a sans-serif font for large blocks of digital text.
Examples: Helvetica, Verdana, Arial, Tahoma
* serif - These fonts are the second most popular typefaces. "Serif" refers to the small flourish lines at the edges of letters and symbols. "Serifs" make each character more distinct, making text easier to read in print. This is why these fonts might remind you of a text from a typewriter, or of the fonts you see in printed books, newspapers or magazines. These typefaces can often be used effectively for titles or emphasis.
Examples: Times New Roman, Book Antiqua, Georgia
* monospace - These fonts guarantee that all letters have the same fixed width. This is similar to a manual typewriter, or how computer code appears in editors. These fonts were designed for the ease of the technology, not humans, so they should be used sparingly. The most effective time to use these is when showing snippets of code. 
Example: Courier New 
* cursive - These fonts mimic human handwriting often by joining letters or having an italic slant. For some languages, these fonts are extra effective such as Arabic. Other than for specific languages, these fonts in English can be rather complex so they are best use extremely sparingly. 
Example: Comic Sans MS
* fantasy - This is the most diverse category of fonts and includes all of those that are particularly decorative. These can make really great top headers as they can give your Web page a very distinct visual identity. Rarely will you want to use these for anything other than titles. It is also good to note that few of these are widely supported, so to use these you'll probably want to download them from a font service to make them available for your user.
Example: Impact

### External resource

Here is the W3C documentation for all of CSS's font properties: [CSS Fonts Module Level 3](https://www.w3.org/TR/css-fonts-3/).

---

#### Module 5: Designing your Web site for your audience   5.2 The basics of design   Color

# Color

One of the most important design decisions you can make is your Web site's color palette. You should choose a palette before you begin designing to keep a cohesive visual identity. A common mistake it to use too many colors on a page. As you are starting out, it is best to limit yourself to just a few colors per page.

For a consistent look and feel your users will recognize, you will want to limit yourself to around 4 colors for all non-graphic content like text, backgrounds, borders, etc. There are different color palette tools on the Web you can play around with, but one of the best ways is to find a site you like the look and feel of and see if you can identify what color palette they are using.

When getting into design, it's a good idea to brush up on the basics of color theory, but just in case here's a short refresher. This is the color wheel:

![Color Wheel](https://www.w3.org/wiki/images/d/d2/10000000.jpg)

#### Colors make other colors

* The historical color wheel is organized around the three primary colors: red, yellow and blue.
* The secondary colors are the combinations of these primary colors: orange, green and purple.
* You can follow this pattern of varying the amount of each primary color to create infinite intermediary colors.
* However, as you've seen for the Web, we define all colors as combinations of Red, Green and Blue (green not yellow). The short answer for this is because that is how the human eye perceives color, something that was unknown when the historical color wheel was made.


#### Build a palette based on the color wheel

* Colors that are across the wheel are called "complementary", blue and orange, red and green, etc.
* Colors that are next to one another are considered  "analogous" like navy, blue and teal or lime, green and hunter.
* When picking a color palette, you should generally pick between one that is comprised mostly of analogous colors, or mostly of complementary colors. Thankfully, there are lots of wonderful tools to help you do this! One we suggest is http://www.paletton.com/, where you can choose a starting color. It will generate for you a set of other colors that according to color theory will look pleasing together.

In your 4 colors, you'll want to keep a consistent tone so that your colors look good together. You'll want at least 1 very light color and 1 dark color. Avoid having all dark colors or all light, as often having contrast is important for readability. Also keep in mind not all users have full-color vision, so try to avoid too many similar colors. We will discuss how to choose inclusive colors in more detail in a later section.

#### External resource

Here is a good article that goes into detail about [color theory](https://www.w3.org/wiki/Colour_theory).

---

#### Module 5: Designing your Web site for your audience   5.2 The basics of design   White space

# White space

It can be difficult to strike a good balance of white space. The most common mistake beginner Web designers make is to not leave enough white space or empty space between HTML elements. 

You will want to make liberal use of paddings and margins to make sure that your site has plenty of empty space. Empty space makes it easier for a user's eyes to move around your page. You will want to ensure there is space between your HTML elements as well as between your elements and the edge of the page. 

Good balance between content and white space prevents your user from becoming fatigued while looking at your site. For example, when lines of text are very long, it is difficult to read without losing track of where you are. It is also fatiguing when the lines of text are too short because the user has to read vertically too much. There is considerable research on the topic, but a good rule of thumb is to limit lines of text to 50-75 characters wide.

---

#### Module 5: Designing your Web site for your audience   5.2 The basics of design   Activity 5.2 and discussion

# Activity 5.2 and discussion

###Activity 5.2 - Breaking design guidelines

For this activity, you'll need to find a Web site that violates one of the following design guidelines:

* Uses more than 2 different font-faces within a single page
* Uses more than 4 different colors within the same page
* Displays text wider than 50-75 characters across

Once you have found a site, please share it in the discussion and answer the following questions:

* Which of the 3 design guidelines are violated? More than 1 guideline?
* Do you think that violation is a problem in this design?
* How you you improve the design overall? 

---

#### Module 5: Designing your Web site for your audience   5.3 Designing for your audience   Intro to Web accessibility

# Intro to Web accessibility

### What is Web accessibility?

> The power of the Web is in its universality.
> Access by everyone regardless of disability is an essential aspect.
**Tim Berners-Lee, W3C Director and inventor of the World Wide Web**

The Web has become an essential aspect of our daily lives, and everyone should have access to this technology. Web accessibility focuses on ensuring equivalent access for people with disabilities. It is increasingly important to many organizations and governments from around the world, and has many business benefits. Access to information, including on the Web, is also recognized by the UN Convention on the Rights of Persons with Disabilities (CRPD).

### Who is impacted?

Web accessibility addresses all disabilities, including hearing, learning and cognitive, neurological, physical, speech, and visual disabilities. Some examples of Web accessibility features include:
* Captions on audio and multimedia content for people who are hard of hearing;
* Clear and consistent layout for people with learning and cognitive disabilities;
* Keyboard support for people with physical disabilities and do not use a mouse;
* Text alternatives for people with visual disabilities and using screen readers;

### Web accessibility benefits people with and without disabilities

Web accessibility features also benefit many more users, such as:

* People with temporary situational limitations, such as a broken arm;
* People using mobile devices, televisions, and other access channels;
* People using older computers, with low bandwidth, and other limitations;
* People who are new to computers, to the Web, or to your own website;
* People who are not fluent in the language of your particular website;

The Web is an increasingly important resource in many aspects of life: education, employment, government, commerce, health care, recreation, and more. When Web pages, Web technologies, Web tools, or Web applications are badly designed, they can create barriers that exclude people from using the Web. More information is available in the W3C Accessibility overview.

Curso   Module 5: Designing your Web site for your audience   5.3 Designing for your audience   Intro to Web accessibility
 Anterior

other Intro to Web accessibility 

other Inclusive design 

other What is internationalization? 

other Activity 5.3 and discussion Siguiente 
Intro to Web accessibility
 Bookmark this page
What is Web accessibility?

The power of the Web is in its universality.
Access by everyone regardless of disability is an essential aspect.
Tim Berners-Lee, W3C Director and inventor of the World Wide Web

WAI Web page displayed on a laptop's screen

The Web has become an essential aspect of our daily lives, and everyone should have access to this technology. Web accessibility focuses on ensuring equivalent access for people with disabilities. It is increasingly important to many organizations and governments from around the world, and has many business benefits. Access to information, including on the Web, is also recognized by the UN Convention on the Rights of Persons with Disabilities (CRPD).

Who is impacted?

Web accessibility addresses all disabilities, including hearing, learning and cognitive, neurological, physical, speech, and visual disabilities. Some examples of Web accessibility features include:

Captions on audio and multimedia content for people who are hard of hearing;
Clear and consistent layout for people with learning and cognitive disabilities;
Keyboard support for people with physical disabilities and do not use a mouse;
Text alternatives for people with visual disabilities and using screen readers;
Web accessibility benefits people with and without disabilities

Web accessibility features also benefit many more users, such as:

People with temporary situational limitations, such as a broken arm;
People using mobile devices, televisions, and other access channels;
People using older computers, with low bandwidth, and other limitations;
People who are new to computers, to the Web, or to your own website;
People who are not fluent in the language of your particular website;

The Web is an increasingly important resource in many aspects of life: education, employment, government, commerce, health care, recreation, and more. When Web pages, Web technologies, Web tools, or Web applications are badly designed, they can create barriers that exclude people from using the Web. More information is available in the W3C Accessibility overview.

### First steps in Web accessibility

There are many simple Web accessibility improvements that you can implement and check right away, even when you are 
new to this topic. Two example excerpts are provided below on this page but you can find more tips and information 
from W3C/WAI:

* [Tips for Getting Started with Web Accessibility](https://www.w3.org/WAI/gettingstarted/tips/)
* [Easy Checks - A First Review of Web Accessibility](https://www.w3.org/WAI/eval/preliminary)

### Example 1: page title

Good page titles are particularly important for orientation — to help people know where they are and move between 
pages open in their browser. The first thing screen readers say when the user goes to a different Web page is the 
page title. In the Web page markup, they are the `<title>` within the `<head>`.

#### Check #1: There is a title that adequately and briefly describes the content of a page, and that it distinguishes the page from other Web pages.

Example:
```html
<head>
...
   <title>Web Accessibility Initiative (WAI) - home page</title>
...
</head>
```

### Example 2: image text alternatives ("ALT TEXT")

Text alternatives ("alt text") are a primary way of making visual information accessible, because they can be rendered through any sensory modality (for example, visual, auditory or tactile) to match the needs of the user. Providing text alternatives allows the information to be rendered in a variety of ways by a variety of user agents. For example, a person who cannot see a picture can have the text alternative read aloud using synthesized speech.

#### Check #2: Every image has alt with appropriate alternative text.

Example: See the W3C logo below. It contains a link that points to the W3C Web site. The text alternative is going to be a brief description of the link target.

```html
<a href="http://w3.org">
   <img src="images/w3c_home.png" width="72" height="48" alt="W3C Web site">
</a>
```

---

#### Module 5: Designing your Web site for your audience   5.3 Designing for your audience   Inclusive design

# Inclusive design