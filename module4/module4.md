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