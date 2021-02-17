# Code 301 Reading Notes

## Mustache and Flexbox
- Javascript templating is a fast and effeciant techique to render client-side veiw templates with Javascript but using a JSON data source. 

### Mustache
- Mustache is a logic-less template suntax. It can be used for HTML, config files, source code and so on. It expands tags in a template using values provided in **hash** or **object**.

- It is refered to as "logic-less" because there are no if statements, else clauses, or for loops. There are only tags. Some tags are replaced with a value, some nothing ,and other a series of values. 

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

Next in the router congiguration, use res.redner(TEMPLATE_NAME, JSSON_DATA).Example:

**res.render('hello', {"name": Sherlyn})**

The first parameter hello refers to the hello.thm file. The second parameter would be the JSON data itself. We can also pass in a variable representing the data, for example.

var nameObject = {"name": "Sherlynn"}
res.render('hello', nameObject)

This is a simple example, but it should help you to understand the vasic concept behind templating. 
### Table of Contents

### Link to Code 102
- [Code 102 Reading Notes](https://jtaisey389.github.io/reading-notes/)

### Link to Code 201
- [Reading Notes 201](https://jtaisey389.github.io/reading-notes201.md/)