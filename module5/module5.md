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