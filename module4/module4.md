#### Module 4: Layout and positioning   4.1 Introduction   Welcome to Module 4

# Video: Welcome to Module 4

In this module, you will learn:

* How to use padding and margin to position elements relative to each other and the window
* How to use alignment to control how your content sits within its HTML element
* How to use the float property to let multiple HTML elements share horizontal space
* How to use relative positioning to design your page so that it maintains its layout regardless of screen size
 
---

#### Module 4: Layout and positioning   4.1 Introduction   Meet the box model

# Meet the box model

The Box Model is how Web browsers see individual HTML elements. Each element is comprised of 4 areas: 
the **element**, the **padding**, the **border** and the **margin*.

We discussed how to adjust the white space of these areas in Module 2.5, but in this module we will be discussing 
these areas as a method to position elements on a page.

![boxmodel](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/e0c6338dd98e9176bf12088bb686892f/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/4-1_box_model.PNG)

* **element** - This is always contained within a square, even if it is a text block with jagged edges or a transparent image that isn't rectangular. Web browsers will impose a rectangle around the smallest area the HTML element's content actually occupies. Until now we've allowed the Web browser to determine the size of the element based solely on the content, but later in this section we'll learn how to adjust this sizing.
* **padding** - This is the white space just outside the element's content. You can set each of the four sides independently, and you can set the value to 0. If you set the element's background color, that color will apply to the padding as well.
* **border** - This is the area just outside the padding. Most HTML element's border default width is 0 and thus invisible. You can set each of the four sides independently. You can set a color, a pattern, even an image. This is a great way to add horizontal or vertical lines to an element on your page.
* **margin** - This is the space surrounding an element, outside the border. Margins are the part of HTML elements that interact with one another. When two margins interact the larger of the two wins meaning the smaller margin "collapses", thus the actual space between two elements is the larger of the two, not the sum of the margins.

https://codepen.io/techie4good/pen/jrEBJY

External resource:

Box model definition in the W3C's CSS2.1 specification: https://www.w3.org/TR/CSS2/box.html

---

#### Module 4: Layout and positioning   4.2 The basics of layout   The alignment property

# The alignment property

One of the simplest ways to align content is to use the direct text-align property. This can help you set the alignment of text or inline content within the 
context of their containing HTML element.

### text-align

[Documentation](https://www.w3.org/TR/CSS22/text.html#alignment-prop)

```css
h1 {
   text-align: center;
}
```
If you have used a text editor before, like Microsoft Word, you've probably used the different text-align properties: left (default for English), right, center and justify. Text-align in CSS works the same way. Left, center and right specify how the lines of text within the text block are arranged. Justify sets the left and right edges of the text flush with the container's edges, which stretches the white space between words so that the overall block fits in a perfect rectangle.

See below for examples of what each of these values will do to your text:
![align](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/8fa61e99d7f19f1e10862952f41a5128/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/4-2-3_text_align.PNG)

Note that this property can only apply to block elements like paragraphs, divs and headers.

### line-height

[Documentation](https://www.w3.org/TR/CSS22/visudet.html#line-height)

```css
h1 {
   line-height: 1.2;
}
```
You may have noticed that the text-align property sets the content's alignment horizontally, but it leaves its vertical alignment unchanged. Text lives 
within a specified vertical space, in which the text is drawn by default in the middle of that vertical space. If you change the height of the containing 
HTML block, the text will remain at the top of the block. However, if you instead use the "line-height" property, then the block will grow and the text 
will vertically center within it.

https://codepen.io/w3devcampus/pen/gWOBGY


```html
<!DOCTYPE html> 
<!--It's a best practice to always declare DOCTYPE!-->
<html lang="en">
  <head>
    <title>Aligning text </title>
    <meta charset="utf-8">
  </head>
  <body>
    <h1>this is a centered header</h1>
    <h2>this is a right aligned header</h2>
    <p>
      Here is a big block of text illustrating the usage of the text-align justify setting. As you can see it stretches the white space between the words so that the left and right edges of the paragraph fit well within a box. This can help your text look cleaner than a simple left alignment. Note that it does not stretch out the final line in the paragraph.
    </p>
    <h3>this header's line height is stretched to 1.2</h3>
    <h4>this header is alligned to the baseline of the line height within a stretched containing box</h4>
  </body>
</html>
```

```css
h1 {
  background-color: red;
  width: 500px;
  text-align: center;
}
h2 {
  background-color: orange;
  text-align: right;
}
p {
  background-color: yellow;
  width: 500px;
  padding: 10px;
  text-align: justify;
}
h3 {
  background-color: green;
  line-height: 1.2;
}
h4 {
  background-color: blue;
  height: 200px;
  line-height:4;
}
```

... and the resulting output:

![result](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/3de7c0b54bd64eeffcf209a9928a95f0/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/4-2-3_alignment-1.PNG)

### INTERNATIONAL CONSIDERATIONS

Please do not use text-align indiscriminately. If there's a possibility that your site will need to be translated into a language that uses the Arabic, Hebrew, 
or Thaana scripts (which read from right to left), it creates difficulties to have to change all the  right values to left and vice versa.

Most, but not yet all, major browsers support the values start and end. The start value aligns text with the side of the line where you start reading, 
whether that's on the left for English or the right for Urdu. They also make more sense for use with vertical text, such as for Japanese and Mongolian. 
Once these values are widely supported by browsers, they will often be a better choice than right and left, since there's no need to change the values 
for pages as the language changes.

Also, note that CSS will in the future provide better support for justification in languages where words are not separated by spaces, such as Chinese 
and Thai, or languages where words are separated by special marks, such as in Amharic. For more information about different approaches to justification, 
see this [article](https://www.w3.org/International/articles/typography/justification).

Once you finish this course, look out for these and other international features of CSS as you explore its features further.


---

#### Module 4: Layout and positioning   4.2 The basics of layout   Element width and height

# Element width and height

Element width and height

Until now we've let the browser decide how big the element is, but you can actually adjust its width and height manually.

### Width and height

Documentation: the [width](https://www.w3.org/TR/CSS22/visudet.html#the-width-property) property 
and the [height](https://www.w3.org/TR/CSS22/visudet.html#the-height-property) property

```css
p {
   width: 30%;
}
```
You can use pixel values for both width and height, but you'll most often want to use percentages to set these so that 
your elements grow and shrink as appropriate based on the screen size.

For example, if we set the width of a paragraph to 30% as you resize the browser window, you'll see how that element 
dynamically resizes. That's because when you use percentages, the size is computed based on the element's 
"[containing block](https://www.w3.org/TR/CSS22/visuren.html#containing-block)", or the element that contains the one 
you're styling. If your element is just within the body tag, 
the width is computed based on the relationship with the screen width.

Things are a bit more complicated with using a percentage to set an element's height. This is because typically the body's 
height is not specified, so if you use a percentage the size won't adjust.

### min-width, max-width, min-height, max-height
Documentation: [max and min width](https://www.w3.org/TR/CSS22/visudet.html#min-max-widths) and [max and min height](https://www.w3.org/TR/CSS22/visudet.html#min-max-heights)

Setting width and height with percentages will save you work because your design will automatically optimize for the 
user's screen size. However, some elements can't grow and shrink as dynamically as text can.

For example, images will get "pixelated" if you let them grow too large, and they can look really distorted. Thankfully, 
you can set max and min width and heights. This way, you can set a range for your image to grow and shrink where you 
know it will still look good. 


```css
img {
   width: 100%;
   max-width: 1024px;
}
```

https://codepen.io/techie4good/pen/JRoJXN

```html
<!DOCTYPE html> 
<!--It's a best practice to always declare DOCTYPE!-->
<html lang="en">
  <head>
    <title>Dynamic Width and Height</title>
    <meta charset="utf-8">
  </head>
  <body>
    <p id="width50">
      width 50%, no min or max
    </p>
    <p id="width80max">
      width 80%, max of 1000px
    </p>
    <p id="width30min">
      width 30%, min of 200px
    </p>
    <p class="heightSet">
      the height is set to 25%, but there is no affect
    </p>
    <div id="containingBlock">
      <p class="heightSet">
        this height is also set to 25%, and since it's within a div containing block who has a set height of 500px this p will resize in relation to that. 
      </p>
    </div>
  </body>
</html>
```

```css
#width50 {
  background-color:red;
  width: 50%;
}
#width80max {
  background-color: orange;
  width: 80%;
  max-width: 1000px;
}
#width30min {
  background-color: yellow;
  width: 30%;
  min-width: 200px;
}
.heightSet {
  background-color: green;
  height: 25%;
}
#containingBlock {
  height: 500px;
}
```
When you view the above example, the paragraphs will dynamically resize based on the size of your window. For example, 
here is what the code looks like in a wide window:

![full-width](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/433e61cced8e11e11f1478eb37983e5d/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/4-2-1_wide.PNG)

However, here is the exact same code viewed in a much narrower window:

![narrow-width](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/3d9b1840bdbdfaee3fcb0e6576da916f/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/4-2-1_narrow.PNG)

Here, you can see that the elements have resized accordingly, but have hit the limits of their min and max constraints. 
This is why using percentages for width and height are so important, it helps you write code that works for all screen sizes. 

---

####  Module 4: Layout and positioning   4.2 The basics of layout   Padding and margin

# Padding and margin

### Positioning with padding and margin

Whenever possible, it is ideal to position your elements by adjusting their padding and margins. Sometimes this isn't 
enough to get the element exactly where you'd like it to be, so we'll learn more tools later in this module. Regardless, 
you'll almost always want some padding and margin around your element so it's best to adjust these before progressing 
onto more complicated positioning methods.

Once you have set the width for your element, then you can set margins as a way to position your element relative to others. 
One of the most commonly used margin settings is "auto". That is because if you set an element's left and right margin to 
auto it will be dynamically centered within its containing block.

```css
div {
   width: 50%;
   margin-left: auto;
   margin-right: auto;
}
```
However, note that this only works for block HTML elements like paragraphs, divs and headers. If you want to use this to 
position an inline element, such as img or a, you will need to tell CSS to treat them as block elements by setting `display: block;`

```css
img {
   display: block;
   width: 200px;
   margin-left: auto;
   margin-right: auto;
}
```
https://codepen.io/techie4good/pen/ZpYyap

```html
<!DOCTYPE html> 
<!--It's a best practice to always declare DOCTYPE!-->
<html lang="en">
  <head>
    <meta charset="utf-8">
  </head>
  <body>
    <h1>this is a centered header</h1>
    <p>
      <a href="www.microsoft.com">centered link within a p</a>
    </p>
    <section>
      here is text in a centered section on top of the inner div
      <div>
        centered div text within a centered div
      </div>
      and here is text in a centered section below the inner div
    </section>
  </body>
</html>
```

```css
h1 {
  background-color: red;
  width: 50%;
  margin: 0 auto;
}
p {
  background-color: orange;
  width: 70%;
}
a {
  display: block;
  width: 100px;
  margin: 0 auto;
}
section {
  background-color: yellow;
  width: 70%;
  margin: 0 auto;
}
div {
  background-color: green;
  width: 50%;
  margin: 0 auto;
}
```

Here is what the above code looks like in a wide window:

![wide](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/8e7ce50235a81f6e65d0fe91084838bf/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/4-2-2_wide.PNG)

Now, if you resize the window, the elements remain centered no matter what. Here is the above code in a narrow window:

![narrow](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/e4842b904e93366d4b42b22e46440847/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/4-2-2_narrow.PNG)

#### External resources:

A W3C CSS tip: [CSS centering things](https://www.w3.org/Style/Examples/007/center), on different ways to center your content.
A "CSS Tricks" article on [What you should know about collapsing margins](https://css-tricks.com/what-you-should-know-about-collapsing-margins/)

---

#### Module 4: Layout and positioning   4.2 The basics of layout   Activity 4.2 and discussion

# Activity 4.2 and discussion

For this activity, you are going to practice some of the basic alignment properties you've learned in this unit.

Here is some HTML and CSS:

See the Pen [Practice with Alignment](https://codepen.io/techie4good/pen/PbKMqY) by Kasey Champion ([@techie4good](https://codepen.io/techie4good/)) on CodePen.

As it is, the given HTML and CSS codes produce the following Web page:
![Webpage](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/ac176f1517ec268dcb30bb52998246a1/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/4-2-4_before.PNG)

As you can see it's not very well aligned. Your goal is to add properties to the existing CSS rules so that the final page looks like this:
![styled](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/eaf30118ca2b8f2fe5fda30a25c2c3d2/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/4-2-4_after.PNG)

To do this you will need to:

* remove the margin at the very edges of the page so the header and footer touch the edges of the page.
* limit the size of the h1 title to 50% of the page's width, with horizontally centered text and vertically centered text within a height of 75px.
* stretch the height of the header p to 50px, but let the text remain top aligned
* limit the width of the section to 75% of the page, but never less than 500px. The section should be centered within the window.
* limit the width of the h2 to 30% of the section, centered within that container. It should have a padding of 30px all around it.
* limit the width of each article to 40% of the width of the section, with justified text. Each should have a margin of 50px all around it, a top padding of 10px, a left and right padding of 15px and a bottom padding of 30px. The h3 within each article should be aligned to the right.
* give the #leftP article a left margin of 10% of the section.
* give the #rightP article a left margin of 50% of the section.
* limit the footer height to 10% of the page, but no more than 50px and no less than 10px. It should have a padding of 10px and a margin between it and the section of 30px.

Use the discussion below to discuss your experiences.

---

#### Module 4: Layout and positioning   4.3 Floating elements   Meet the float property

# Meet the float property

If your elements are still not exactly where you want them to be after adjusting the padding, margins and alignment, then you 
can try out the float property. The "float" property is one of the most powerful tools you can master when learning CSS.

```css
h1 {
   width: 20em;
   float: right;
}
```

Up until now, we haven't moved elements very far from wherever the web browser automatically places them, but as you've probably noticed this has left our page very left side heavy. This is because, by default, elements are stacked one on top of the other, and they don't share horizontal space. With the float property, we can change this.

The float property liberates an element from its automatic position and lifts it up to "float" on top of other elements in the direction you specify.  You can specify float either right, left or the default of none. 

Elements underneath a floating object will automatically wrap themselves around the content. For example, if you float an image, the text underneath will wrap around it so that none of it is actually obscured underneath the image, but now both text and an image can share horizontal space.

![float](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/c631ba121850e9a7653d7b877f7ef05b/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/4-3_float_img.PNG)

You'll often want to set the width of a floating object so that you have tighter control over the space that object occupies. Remember that, by default, block HTML elements occupy the entire width of the page, even if there isn't actual content that extends that far. In this case, you'll want to set the width so that your element's size more accurately represents its content and you don't have unnecessary white space. 

The Clear Property

Once you have some elements floating things can get a little messy. Its easy for floating objects to overlap, and to prevent this you can use the "clear" property.

[Documentation](https://www.w3.org/TR/CSS22/visuren.html#propdef-clear)

```css
p {
   clear: both;
}
```
The clear property sets which sides of an element cannot be touching an earlier floating element. You can set clear to right, left, both or the default of none. Below you can see the example from above with an added header, but the header is also sharing horizontal space with the image like the paragraph text.

If you add a `clear:left` to this header you will prevent it from touching floating elements on its left side resulting in the following image:

https://codepen.io/techie4good/pen/mAymQq

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="utf-8">
    </head>
  <body>
   <div id="default">
   This div is not floating, has no width set.
   </div>
   <div id="floatRightNoWidth">
   This div is floating right, but no width is set.
   </div>
   <div id="floatRightTooWide">
   This div is floating right, but the text is very very very long. This makes the div fill the horizontal space of the page by default, so when it is floated it doesn't look like it goes anywhere.
   </div>
   <div id="noFloatWidthSet">
   This div isn't floating, and its width is set to 40%. Floating elements can overlap.
   </div>
 
   <div id="floatRightWidthSet">
   This div is floating right, and its width is set to 30%
   </div>
   <div id="noFloatClearRight">
   This div isn't floating, and it is set to clear to the right, so nothing can overlap.
   </div>
  </body>
</html>
```

```css
body {
   font-size: 24pt;
   font-family: helvetica, sans-serif;
}
div {
   margin-bottom: 10px;
}
#default {
   background-color: red;
}
#floatRightNoWidth {
   background-color: orange;
   float: right;
}
#floatRightTooWide {
   background-color: yellow;
   float: right;
}
#noFloatWidthSet {
   background-color: green;
   width: 40%;
}
#noFloatClearRight {
   background-color: purple;
   clear: right;
}
#floatRightWidthSet {
   background-color: blue;
   width: 30%;
   float: right;
}
```

![image](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/445a62ab3ed7255b919c73ceac322320/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/4-3_float.PNG)

---

#### Module 4: Layout and positioning   4.3 Floating elements   Activity 4.3 and discussion

# Activity 4.3 and discussion

One of the toughest parts of layouts with CSS is figuring out which elements to apply a float property to.

Here is some HTML and CSS:

https://codepen.io/techie4good/pen/xEbWrp


```html
<!DOCTYPE html> 
<!--It's a best practice to always declare DOCTYPE!-->
<html lang="en">
  <head>
    <title>Practice with Float</title>
      <meta charset="utf-8">
  </head>
  <body>
    <header>
      <h2>welcome greeting subtitle</h2>
      <h1>Homepage Title</h1>
    </header>
    <section id="navigation">
      <ul>
        <li>nav link 1</li>
        <li>nav link 2</li>
        <li>nav link 3</li>
        <li>nav link 4</li>
      </ul>
    </section>
    <section id="content">
      <div id="topRight">
        If your elements are still not exactly where you want them to be after adjusting the padding, margins and alignment, then you can try out the float property. The "float" property is one of the most powerful tools you can master when learning CSS.
      </div>
      <div id="topLeft">
        Up until now, we haven't moved elements very far from wherever the web browser automatically places them, but as you've probably noticed this has left our page very left side heavy. 
      </div>
      <div id="bottomRight">
        The float property liberates an element from its automatic position and lifts it up to "float" on top of other elements in the direction you specify.  You can specify float either right, left or the default of none.  
      </div>
      <div id="bottomLeft">
        Elements underneath a floating object will automatically wrap themselves around the content. For example, if you float an image, the text underneath will wrap around it so that none of it is actually obscured underneath the image.
      </div>
    </section>
  </body>
</html>

```

```css
body {
  background-color: #4ABDAC;
  color: #FFFFFF;
  font-family: Georgia, serif;
}
header {
  background-color: #F7B733;
  height: 75px;
}

h1 {
  padding: 15px;
}
#navigation {
  height: 30px;
  width: 30%;
  margin-left: auto;
  margin-right: auto;
}

#navigation li:hover {
  border-bottom: 1px #FC4A1A solid;
}
#content {
  background-color: #DFDCE3;
  width: 50%;
  margin: 0 auto;
}
div {
  background-color: #FC4A1A;
  width: 250px;
  height: 150px;
  padding: 10px;
  margin: 20px;
}

```

As you can see the layout is pretty messy. Your job in this activity is to decide which elements deserve a float property. You might also need to adjust some widths, margins and paddings to get everything looking like the final image below:

![messy](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/8fa8e85bccbafdea433ff8666300430e/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/4-3-2_activity_output.PNG)

HINT: Pay close attention to the IDs applied to the HTML elements

Use the discussion below to share your experiences.

---

#### Module 4: Layout and positioning   4.4 Relative positioning   Meet relative positioning

# Meet relative positioning

The "position" property sets the algorithm for how the Web browser will compute the way the HTML elements are placed on the page. There are four different value options for the position property: 

* **relative** - This is the position setting we will be discussing in detail as it is the best way to build on the dynamic layout methods we have learned thus far. This lets you specify where an HTML element should be relative to where it would be by default.
* **static** - This is the default setting and will place an element wherever the web browser computes it should be. 
* **fixed** - This places an element in a specific location within the window. You can use this to set an element to remain where it is regardless of scrolling. This was used heavily when "frames" were popular, however now it should be used very sparingly. 
* **absolute** - This allows you to position elements relative to their containing box. This removes an element from it's normal flow (just like a floating element) so it can be difficult to control and make a layout that is truly dynamic. 

[Documentation](https://www.w3.org/TR/CSS22/visuren.html#choose-position)
    
```css
div {
   position: relative;
}
```
Once you've set the position to "relative" that frees you up to set the top, right, bottom and left properties- otherwise known as the "box offsets". These properties specify the distance between this object and its normal static position and the corner of the box that we are specifying.

For example, if we set the "left" to be "30px", it will move the element 30px to the right away from the left of where it was placed by default.

```css
p {
   position: relative;
   left: 10px;
}
```
[Documentation](https://www.w3.org/TR/CSS22/visuren.html#position-props)

Note that position is not an inherited property so you will have to apply it individually to each element. Because of this it is 
best to use this approach to designing your layout sparingly and should only be used after you cannot achieve your desired layout with alignment or floating. 

https://codepen.io/techie4good/pen/kkYwmB

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
    <h2>welcome greeting subtitle</h2>
    <h1>Homepage Title</h1>
   </header>
  <section id="navigation">
   <ul>
    <li>nav link 1</li>
    <li>nav link 2</li>
    <li>nav link 3</li>
    <li>nav link 4</li>
    </ul>
   </section>
   <section id="content">
    <div id="topRight">
    If your elements are still not exactly where you want them to be after adjusting the padding, margins and alignment, then you can try out the float property. The "float" property is one of the most powerful tools you can master when learning CSS.
    </div>
    <div id="topLeft">
    Up until now, we haven't moved elements very far from wherever the web browser automatically places them, but as you've probably noticed this has left our page very left side heavy.
    </div>
    <div id="bottomRight">
    The float property liberates an element from its automatic position and lifts it up to "float" on top of other elements in the direction you specify.  You can specify float either right, left or the default of none.
    </div>
    <div id="bottomLeft">
    Elements underneath a floating object will automatically wrap themselves around the content. For example, if you float an image, the text underneath will wrap around it so that none of it is actually obscured underneath the image.
    </div>
   </section>
  </body>
</html>
```

```css
h1 {
  background-color: red;
  width: 300px;
  position: relative;
  left: 150px;
}
section {
  background-color: orange;
  height: 100px;
}
h2 {
  position: relative;
  top: 20px;
}
footer {
  background-color: yellow;
  height: 200px;
  width: 300px;
  position: relative;
  left: 50px;
  top: 50px;
}
h3 {
  position: relative;
  top: 50px;
  left: 10px;
}

```
.... gives this output:

![output](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/a4ce8d619c1e91db563362743d829e21/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/css-intro-4-4-position1.png)

Note that relative positioning can make elements overlap - check the following CSS code as a second example:

```css
h1 {
   background-color: red;
   width: 300px;
   position: relative;
   left: 150px;
}
section {
   background-color: orange;
   height: 100px;
}
h2 {
   position: relative;
   top: 20px;
}
footer {
   background-color: yellow;
   height: 200px;
   width: 300px;
   position: relative;
   left: 50px;
   top: -50px;
}
h3 {
   position: relative;
   top: 50px;
   left: 10px;
}
```
... that gives this different output:
![output2](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/fecd6b132ba6083f0694307af1dc85c0/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/css-intro-4-4-position2.png)

---

#### Module 4: Layout and positioning   4.4 Relative positioning   Activity 4.4 and discussion

# Activity 4.4 and discussion

### Activity 4.4 - Practice with relative positioning

For this activity, we are going to focus on using relative positioning to adjust how items sit on the page.

Here is some HTML and CSS:
https://codepen.io/techie4good/pen/KgwRwg

```html
<!DOCTYPE html> 
<!--It's a best practice to always declare DOCTYPE!-->
<html lang="en">
  <head>
    <title>Practice with Relative Positioning</title>
      <meta charset="utf-8">
  </head>
  <body>
    <h1>This is the main title</h1>
    <h2>this is the subtitle</h2>
    <section>
      <div>
      <h3>subsection title</h3>
          <p>
      The "position" property sets the algorithm for how the Web browser will compute the way the HTML elements are placed on the page. There are four different value options for the position property:
        </p>
    </div>
    <div>
      <h3>subsection title</h3>
      <p>
     Once you've set the position to "relative" that frees you up to set the top, right, bottom and left properties- otherwise known as the "box offsets". These properties specify the distance between this object and its normal static position and the corner of the box that we are specifying.

For example, if we set the "left" to be "30px", it will move the element 30px to the right away from the left of where it was placed by default.
      </p>
      </div>
    </section>
  </body>
</html>
```

```css
body {
  background-color: #EFEFEF;
  color: #A9A9A9;
  font-family: "Book Antiqua", serif; 
}
h1 {
  color: #FF3B3F;
}
h2 {
}
div {
  background-color: #CAEBF2;
  width: 80%;
}
h3 {
  color: #FF3B3F;
}
p {
  width: 90%;
}
```
Your task is to add CSS so that you achieve this final layout:
![layout](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/96e4824c9970225df71220b783177964/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/4-4_activity_output.PNG)

You can do this with padding and margins, but limit yourself to only add position, top and left properties. Try 
resizing your browser window, and if you've implemented everything correctly all the elements will stay in the 
same position relative to one another. 

Use the discussion below to share your experiences.

---

#### Module 4: Layout and positioning   4.5 Style studies   Menus

# Menus

One of the most important aspects of any Web site is the navigation menu. Over time, top level navigation has become fairly standardized so your user will be looking for some key elements that help them find their way around your site:

* A small group of descriptive links in a rectangular arrangement, often horizontally
* A hover style to give your user some amount of responsiveness
* A special style indicating the link for the page you are currently on

https://codepen.io/techie4good/pen/ObxErz


```html
<!DOCTYPE html> 
<!--It's a best practice to always declare DOCTYPE!-->
<html lang="en">
  <head>
    <title>Practice with Alignment</title>
    <meta charset="utf-8">
  </head>
  <body>
    <div id="menu1">
      <ul>
        <li class="currentPage"><a href="">Home</a></li>
        <li><a href="">About</a></li>
        <li><a href="">Blog</a></li>
        <li><a href="">Contact</a></li>
      </ul>
    </div>

    <div id="menu2">
      <ul>
        <li class="currentPage"><a href="">Home</a></li>
        <li><a href="">About</a></li>
        <li><a href="">Blog</a></li>
        <li><a href="">Contact</a></li>
      </ul>
      <section>
        <h1>Home Page</h1>
        <p>A bunch of page content </p>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
      </section>
    </div>

    <div id="menu3">
      <ul>
        <li class="currentPage"><a href="">Home</a></li>
        <li id="about">
          <a href="">About</a>
          <ul class="subitems">
            <li>subitem 1</li>
            <li>subitem 2</li>
          </ul>
        </li>
        <li><a href="">Blog</a></li>
        <li><a href="">Contact</a></li>
      </ul>
    </div>
  </body>
</html>
```

```css
div {
  clear: both;
  margin-bottom: 50px;
  padding: 30px;
  font-family: Arial;
}
ul {
  list-style: none;
  height: 50px;
}

a {
  text-decoration: none; 
}
#menu1 {
  background-color: #0E0B16;
}
#menu1 a {
  color: #E7DFDD;
}
#menu1 li {
  padding: 10px;
  float: left;
}
#menu1 a:hover {
  border-bottom: 2px #A239CA solid;
}
#menu1 .currentPage {
  background-color: #A239CA;
}
#menu1 .currentPage a {
  color: #0E0B16;
}


#menu2 ul {
  width: 10%;
  height: 300px;
  background-color: #BFD8D2;
  margin: 0px;
  text-align: center;
  padding: 0px;
  float: left;
}
#menu2 a {
  color: #FFFFFF;
}
#menu2 li {
  height: 15%;
  padding-top: 25px;
}
#menu2 li:hover {
  background-color: #FEDCD2;
  border-left: 5px #DCB239 solid;
}
#menu2 li a {
  font-size: 1.2em;
}
#menu2 .currentPage {
  background-color: #FEDCD2;
  border-left: 5px #DCB239 solid;
}
#menu2 section {
  background-color: #FEDCD2;
  margin-left: 10%;
  height: 300px;
}
#menu2 h1 {
  margin: 0px;
  color: #FFFFFF;
  text-align: center;
}
#menu2 p {
  padding: 30px;
}

#menu3 {
  background-color: #D9D9D9;
}
#menu3 ul {
  background-color: #4484CE;
}
#menu3 li {
  float: right;
  padding: 15px 30px;
}
#menu3 li:hover {
  background-color: #F9CF00;
}
#menu3 li:hover a {
  color: #4484CE;
}
#menu3 a {
  color: #F9CF00;
  font-size: 1.3em;
}
#menu3 .subitems {
  background-color: #F9CF00;
  width: 100%;
  padding: 0px;
  display: none;
}
#menu3 .subitems li {
  width: 100%;
  margin: 0px;
  padding: 0px;
  float: none;
  color: #4484CE;
}
#menu3 #about:hover .subitems {
  display: block;
}
```

#### Menu 1

This is a very basic menu design. It floats the list elements to the left and gives them each a simple hover property (underline) and a new background color for the link representing the page you are currently viewing.

![menu1](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/6985026ba90be845a330a399bc6b59a1/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/4-5_menu_1.PNG)

#### Menu 2

This menu design uses a vertical arrangement but still floats the overall menu object so it can sit level with your content. You can also see a tabbed format here where the page you are currently viewing directly connects to the menu item representing it. 

![menu2](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/33113a2129d524c729491baf42660eab/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/4-5_menu_2.PNG)

#### Menu 3

This third design employs hover as a way to expose secondary links. This lets you leave the top level clean and simple but gives the user the power of more specific options when they interact with your header.

![menu3](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/e082cebfa12f01a129b47d94dd0a929a/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/4-5_menu_3.PNG)

---

#### Module 4: Layout and positioning   4.5 Style studies   Footers

# Footers

The footer of your page is typically the last thing your user will see, so it's important that you provide them any essential information. Typically, you will see footers that just contain contact info, but often they can also include navigation links, search bars or other calls to action.

You will want your footer to flow with your overall page design, but to be distinct from your content.

https://codepen.io/techie4good/pen/RoLYKO


```html
<!DOCTYPE html> 
<!--It's a best practice to always declare DOCTYPE!-->
<html lang="en">
  <head>
    <title>Practice with Alignment</title>
    <meta charset="utf-8">
  </head>
  <body>
    <div id="footer1">
      <section>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
      </section>
      <footer>
        <div class="contacts">
          <a href="">email</a>
          <a href="">twitter</a>
          <a href="">instagram</a>
          <a href="">facebook</a>
        </div>
        <p>design and code by me</p>
      </footer>
    </div>

    <div id="footer2">
      <section>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
      </section>
      <footer>
        <ul class="navCat">
          <li class="topLevel">About</li>
          <li>About Us</li>
          <li>Our Story</li>
          <li>FAQ</li>
        </ul>
        <ul class="navCat">
          <li class="topLevel">Services</li>
          <li>Custom Orders</li>
          <li>Wholesale</li>
        </ul>
        <ul class="navCat">
          <li class="topLevel">Contact</li>
          <li>Customer Service</li>
          <li>Careers</li>
          <li>Community</li>
          <li>Social Media</li>
        </ul>
      </footer>
    </div>

    <div id="footer3">
      <section>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
      </section>
      <footer>
        Please <a href="#">contact us</a> if you have any questions
      </footer>
    </div>
  </body>
</html>
```

```css
div {
  font-family: Arial;
}

#footer1 {
  background-color: #F4F4F4;
  height: 150px;
  margin-bottom: 50px;
}
#footer1 section{
  height: 60%;
  color: #373737;
  width: 85%;
  margin-left: auto;
  margin-right: auto;
}
#footer1 footer {
  background-color: #C0B283;
  color: #DCD0C0;
  height: 40%;
  text-align: center;
  padding: 15px;
}
#footer1 footer a {
  color: #373737;
  padding: 5px 20px;
}
#footer1 footer a:hover {
  color: #F4F4F4;
}

#footer2 {
  background-color: #0E0B16;
  color: #E7DFDD;
  height: 350px;
  margin-bottom: 50px;
}
#footer2 section {
  width: 85%;
  margin-left: auto;
  margin-right: auto;
  padding-bottom: 30px;
}
#footer2 footer {
  width: 75%;
  margin-left: auto;
  margin-right: auto;
  color: #A239CA;
  border-top: 1px #A239CA solid;
}
#footer2 ul {
  float: left;
  width: 30%;
  list-style: none;
  padding: 0px;
}
#footer2 li {
  padding: 5px;
}
#footer2 .topLevel {
  font-size: 1.2em;
  font-variant: small-caps;
}

#footer3 {
  height: 200px;  
  background-color: #F4DECB;
}
#footer3 section {
  width: 70%;
  margin-left: auto;
  margin-right: auto;
  background-color: #94618E;
  color: #F8EEE7;
  padding: 30px;
  margin-bottom: 30px;
}
#footer3 footer {
  width: 70%;
  margin-left: auto;
  margin-right: auto;
  background-color: #49274A;
  color: #94618E;
  padding: 5px 30px;
  text-align: center;
}
#footer3 a {
  color: #94618E;
}
#footer3 a:hover {
  color: #F4DECB;
}
```

#### Footer 1

This is a basic footer that uses background color to help it stand out from the rest of the content. It contains contact links and a subtle reference to the designer of the page.

![footer1](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/9c135af0d1fef9c55f3107993e8b7e88/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/4-5_footer_1.PNG)

#### Footer 2

This footer provides navigation links. Because the footer is at the bottom of the page, you can get away with more links being exposed because limiting area isn't as important as in the top level header.

![footer2](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/9faaec50681a88db6ebed64764a8bee2/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/4-5_footer_2.PNG)

#### Footer 3

This final design flows with the overall structure of the page, but limits the content to a single simple contact link.

![footer3](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/015bf0799a0d0d1174f6f8817cf511af/asset-v1:W3Cx+CSS.0x+1T2017+type@asset+block/4-5_footer_3.PNG)

---

#### Module 4: Layout and positioning   4.6 Project 4 - My resume   When to use what?

# When to use what?