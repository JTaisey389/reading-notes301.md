# Code 301 Reading Notes

## Read 06 Node JS

### What is node and when should I use it
- Node.js ia a JavaScript runtime built on Chrome's V8 JavaScript engine. It was designed with performance in mind and is responsible for compiling JavaScript directly to native machine code that your computer executes.

- When we say that Node is built on the V8 engine, we don't mean that Node programs are executed within the browser. The creator of Node **Ryan Dahl** took the V8 engine and enhanced it with a set of features such as, API, HTTP library, and a number of operating system related utility methods.

### Installation of Node
- Handfuls of websites suggest you go to the official Node download page and grab the Node binaries for your system. This can work but I recommend that you use a version manager instead. This is a program that allows you to install many versions of node and switch between them at will. There are advantages to this, for example it negates potential permission issues when using Node with npm.

- Lets check to see if you have Node installed on your computer by opening a terminal and typing `node -v`. You should see something like v12.14.1 displayed and this is the current version at this time. 

- Next thing is to create a hello.js and to then copy in the following code `console.log("Hello, World")`. Pop back over to your terminal and type in node  `hello.js`, if your Nods.js is configured right. 

### Node.js and Support for JavaScript
- If you take a look at this link https://node.green/. Node has excellent support for ECMAScript 2015 (ES6) and beyond. You are only targeting one runtime and this means that you can write your JavaScript using the latest and up to date syntax. This also means you should not have to worry about compatibility issues. 

- Moving on here is a second program that makes use of several modern JavaScript features, such as tagged `template literals, object destructuring` and `array.prototype.flatmap():`

Copy and paste this code into your hello.js:

`function upcase(strings, ...values) {
  return values.map(name => name[0].toUpperCase() + name.slice(1))
    .join(' ') + strings[2];
}`

`const person = {
  first: 'brendan',
  last: 'eich',
  age: 56,
  position: 'CEO of Brave Software',
};`

`const { first, last } = person;`
`const emoticon = [ ['┌', '('], ['˘', '⌣'], ['˘', ')', 'ʃ'] ];`

`console.log(`
  `upcase`${first} ${last} is the creator of JavaScript! ` + emoticon.flat().join('')`
`);`

- In your terminal save this file called index.js

### Introducing npm, the JavaScript Package Manager
- As mentioned earlier, Node comes bundled with a package manager called npm. To check which version you have installed, type `npm -v` in your terminal. NPM is a package manager for JavaScript, npm is also the worlds largest software registry. There are well over 1,000,000 packages of JavaScrip code available to download, with billions of downloads each week. 

### Table of Contents

### Link to Code 102
- [Code 102 Reading Notes](https://jtaisey389.github.io/reading-notes/)

### Link to Code 201
- [Reading Notes 201](https://jtaisey389.github.io/reading-notes201.md/)