# Code 301 Reading Notes

## Mustache and Flexbox
- Javascript templating is a fast and efficient technique to render client-side view templates with Javascript but using a JSON data source. 

### Mustache
- Mustache is a logic-less template syntax. It can be used for HTML, config files, source code and so on. It expands tags in a template using values provided in **hash** or **object**.

- It is referred to as "logic-less" because there are no if statements, else clauses, or for loops. There are only tags. Some tags are replaced with a value, some nothing ,and other a series of values. 

- Mustache.js is an implementation of the mustache template system in JavaScript. It is considered the base for JavaScript templating. 

Example: 
Mustace.render("Hello, {{name}}", { name: "Sherlynn"});
// returns: Hello, Sherlynn

In the above, the two braces around the {{name}}. This is Mustache syntax to show that it is a placeholder. 

### ***Mustache-Express***
- If you intend you use mustache with Node and Express, you can use mustache-express. To install mustache express you have two ways to do so. 

Examples: $ yarn add mustache-express

or with NPM:

$ npm install mustache --save

### How to configure Mustache Express
var mustacheExpress = require('mustache-express');

app.enging('html', mustaceExpress());

app.set('view engine', 'html');
app.set('views, _dirname + '/src/views');

https://miro.medium.com/max/2400/1*FRcL9NQHI7Cvi2ELLmzJGQ.png

Next in the router configuration, use res.redner(TEMPLATE_NAME, JSSON_DATA).Example:

**res.render('hello', {"name": Sherlyn})**

The first parameter hello refers to the hello.thm file. The second parameter would be the JSON data itself. We can also pass in a variable representing the data, for example.

var nameObject = {"name": "Sherlynn"}
res.render('hello', nameObject)

This is a simple example, but it should help you to understand the basic concept behind templating. 

### Flex Hints and Tricks
**Justifying Content:**
  - flex-start: Items align to the left side of the container.

  - flex-end: Items align to the right side of the container.

  - center: Items align at the center of the container.

  - space-between: Items display with equal spacing between them.

  - space-around: Items display with equal spacing around them.

**Align Items**
  - flex-start: Items align to the top of the container.
  
  - flex-end: Items align to the bottom of the container.
  
  - center: Items align at the vertical center of the container.
  
  - baseline: Items display at the baseline of the container.
  
  - stretch: Items are stretched to fit the container.

**Flex Direction**
  - row: Items are placed the same as the text direction.
  
  - row-reverse: Items are placed opposite to the text direction.
  
  - column: Items are placed top to bottom.
  
  - column-reverse: Items are placed bottom to top.

**Order**
- Sometimes reversing the row is not enough. We need to use the Order property to individual items. By default items have a value of 0, but we can set to a positive or negative interger. 

**Align Self**
- This property accepts the same values as align-items and it is a value for a **specific** item.

**Flex Wrap**
  - nowrap: Every item is fit to a single line.
  
  - wrap: Items wrap around to additional lines.

  - wrap-reverse: Items wrap around to additional lines in reverse.

***Flex Flow**
- The two properties of flex-direction and flex-wrap are often used together and the shorthand property is flex-flow.

**Align Content**
  - flex-start: Lines are packed at the top of the container.
  - flex-end: Lines are packed at the bottom of the container.
  - center: Lines are packed at the vertical center of the container.
  - space-between: Lines display with equal spacing between them.
  - space-around: Lines display with equal spacing around them.
  - stretch: Lines are stretched to fit the container.

### Table of Contents

### Link to Code 102
- [Code 102 Reading Notes](https://jtaisey389.github.io/reading-notes/)

### Link to Code 201
- [Reading Notes 201](https://jtaisey389.github.io/reading-notes201.md/)