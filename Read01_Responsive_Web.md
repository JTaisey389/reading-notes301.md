# Code 301 Reading Notes

## Read 01 Responsive web design and floats

### Responsive Web Design
- Responsive web design is the practice of build a website to work on every device and every screen size. It is focus around providing an intuitive and gratifying experience for all users. Responsive web design was largely developed by Ethan Marcotte. 

### Responsive vs. Adaptive vs. Mobile
- The term responsive is not that new, but you are probably wondering what exactly is the difference between all of them. Responsive and adaptive are closely related, and often transposed as one and the same. 

**Responsive** It generally means to react quickly and positively to any change.

**Adaptive** It means to be easily modified for a new purpose or situation, such as change. 

**Mobile** Generally means to build a separate website commonly on a new domain solely for mobile users. Most mobile websites can be very light.

### Flexible Layouts
- Responsive web design is broken down into three main components, including **flexible** layouts, **media queries**, and **flexible media**.

**Flexible Layout** The practice of building the layout of a website with a flexible grid, capable of dynamic resizing. These are used to declare common grid property values such as *width*, *margin*, *padding*.

### Flexible Grid
- Let's see how this works! 

HTML:
`<div class="container">`
  `<section>...</section>`
  `<aside>...</aside>`
`</div>`

CSS
.container {
  width: 538px;
}
section,
aside {
  margin: 10px;
}
section {
  float: left;
  width: 340px;
}
aside {
  float: right;
  width: 158px;
}

### Media Queries
- Media Queries were built as an extension to media types commonly found when targeting and including styles. When initializing media queries there are a couple of different ways to use it. Using the @media rule instead of an existing style sheet. Additionally importing a new style sheet using the @import rule, or by linking to a separate style sheet from within the HTML. 

HTML
`<!-- Separate CSS File -->`
`<link href="styles.css" rel="stylesheet" media="all and (max-width: 1024px)">`

CSS
/* @media Rule */
@media all and (max-width: 1024px) {...}

/* @import Rule */
@import url(styles.css) all and (max-width: 1024px) {...}

### Logical Operators in Media Queries
- Logical operators in media queries help build powerful expressions. There are three operators to use within media queries. 

**And**

**Not**

**Only**

Examples
  - @media all and (min-width: 800px) and (max-width: 1024px) {...}
  - @media not screen and (color) {...}
  - @media only screen and (orientation: portrait) {...}

### Height & Width Media Features
- One of the most common media features revolves around determining a height or width for a device or browser viewport. 

Example
  - @media all and (min-width: 320px) and (max-width: 780px) {...}

### Orientation Media Feature
- Orientation media feature determines if a device is in the landscape or portrait orientation. 

Example
  - @media all and (orientation: landscape) {...}

### Aspect Ratio Media Features
- The aspect ratio and device aspect ratio features specifies the width/height pixel ratio of the targeted rendering area or output device.

Example
  - @media all and (min-device-aspect-ratio: 16/9) {...}

In addition to aspect ratio there is the option of pixel ratio feature. 

Example
  - @media only screen and (-webkit-min-device-pixel-ratio: 1.3), only screen and (min-device-pixel-ratio: 1.3) {...}

### Resolution Media Feature
- The resolution media feature specifies the resolution of the output device in pixel density, also known as dots per inch or DPI.

**Pixel Density** Dots per inch or DPI.

Example
  - @media print and (min-resolution: 300dpi) {...}

### Other Media Features
- The other media features include identifying available output colors with the sue of the color, color-index, and monochrome features. Identifying bitmap devices with the grid feature, and identifying the scanning process of a television with the scan feature. These are less common but equally as helpful.

## Mobile First
- A popular technique with using media queries is called mobile first. The mobile first approach includes using styles targeted at smaller viewports. Mobile first approach advocates designing within the constraints of a mobile user in mind. Before too long, the majority of internet consumption will be done on a mobile device.

Examples
  - /* Default styles first then media queries */
  - @media screen and (min-width: 400px)  {...}
  - @media screen and (min-width: 600px)  {...} 
  - @media screen and (min-width: 1000px) {...}
  - @media screen and (min-width: 1400px) {...}

Additionally, downloading unnecessary media assets can be stopped by using media queries. 

Example
  - /* Default media */
body {
  background: #ddd;
}
/* Media for larger devices */
@media screen and (min-width: 800px) {
  body {
    background-image: url("bg.png") 50% 50% no-repeat;
  }
}

### Viewport Scale
- To control how a website is scaled on a mobile device, we use the viewport scale in conjunction with min, max, initial and user scalable properties.

Examples
  - `<meta name="viewport" content="initial-scale=2">`
  - `<meta name="viewport" content="minimum-scale=0">`
  - `<meta name="viewport" content="user-scalable=yes">`


### Viewport Resolution
- Allowing the browser to decide how to scale a website based off of any viewport scales values usually does the trick. 

Example 
  - `<meta name="viewport" content="target-densitydpi=device-dpi">`

### Combining Viewport Values
- The viewport meta tag will accept individual values as well as multiple values, allowing multiple viewport properties to be set at once. 

Example 
  - `<meta name="viewport" content="width=device-width, initial-scale=1">`
  
### CSS Viewport
- Since the viewport meta tag revolves heavily around setting the styles of how a website should be rendered it has been recommended to move the viewport from HTM to CSS.

Example
  - @viewport {
  width: device-width;
  zoom: 1;
}

### Flexible Media
- The final important aspect to responsive web design involves flexible media. As viewports begin to change size media doesn't always follow suit. 

Example
  - img, video, canvas {
  max-width: 100%;
}

Float: A float property allows you to take an element in normal flow and place it as far to the left or right of the containing element as possible.

`blockqoute {`
 `float: right;`
 `width: 275px;`
 `font-size: 130%;`
 `font-style: italic;`
 `font-family: Georiga, Times, Serif; `
 `margin: 0px 0px 10 px 10px;`
 `padding: 10px;`
 `border-top: 1px solid #66ff44;`
 `border-bottom: 1px solid #665544;}`

Using float to place elements side-by-side. A lot of layouts place boxes next to each other. A floating element is commonly used to achieve this. 

Example:

`body {`
 `width: 750px;`
 `font-family: Arial, Verdana, sans-serif;`
 `color: #665544;}`
`p {
 `width: 230px;`
 `float: left;`
 `margin: 5px;`
 `padding: 5px`
 `background-color: #efefef;}`

The clear property allows you to say that no element within the same containing element should touch the left or right-hand sides of a box.

`body {`
 `width: 750px;`
 `font-family: Arial, Verdana, sans-serif;`
 `color: #665544;}`
`p {
 `width: 230px;`
 `float: left;`
 `margin: 5px;`
 `padding: 5px`
 `background-color: #efefef;}`
 `.clear {`
 `clear: left;}`
 
Types of clearing floats: Left, Right, Both, and none

### Table of Contents


### Link to Code 102
- [Code 102 Reading Notes](https://jtaisey389.github.io/reading-notes/)

### Link to Code 201
- [Reading Notes 201](https://jtaisey389.github.io/reading-notes201.md/)
