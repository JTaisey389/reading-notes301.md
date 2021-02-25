# Code 301 Reading Notes

## Read 09 Functional Programing With JavaScript

- After learning and working with object-oriented programing, I took a step back to look at system complexity. What i found from research is functional programing concepts like immutability and pure function. In this reading I will tell you more about functional programming, and some important concepts with a lot of code examples.

### Functional Programing
- Functional programing is a paradigm - a style of building the structure and the elements of computer progams. It treats computation as the evaluation of mathematical function and avoides chaning-state and mutable data.

### Pure Functions

 - The fundamental concept we learn when we want to understand function programming is **Pure Functions**. What i mean is that a function returns the same reslut if given the same arguments and this is also known as deterministric. 

 - Lets imagine we want to implement a function that calculates the area of a circle. An impure function would receive *radius* as a parameter, and then calculate *radius * radius * PI*.

 - Example: 

`let PI = 3.14;`
`const calculateArea = (radius) => radius * radius * PI;`
`calculateArea(10); // returns 314.0`

- This is an impure function because it uses a global object that was not passed as a parameter to the function. Lets fix this in the next example.

`let PI = 3.14;`
`const calculateArea = (radius, pi) => radius * radius * pi;`
`calculateArea(10, PI); // returns 314.0`

### Reading Files
- Our function can read external files, if that is the case it is not a pure function - the file's content can change.

- Example: 
`const charactersCounter = (text) => `Character count:` 
`${text.length}`;`
`function analyzeFile(filename) {
  let fileContent = open(filename);
  return charactersCounter(fileContent);
`}`

### Random Number Generation
- A function that relies on a random number generator cannot be pure

- Example: 
`function yearEndEvaluation() {
  if (Math.random() > 0.5) {
    return "You get a raise!";
  } else {
    return "Better luck next year!";
  }`
`}`

- This does not cause any observable side effects. Side effects may include modifying a global object or a parameter passed by reference. 

- Example: 

`let counter = 1;`
`function increaseCounter(value) {
  counter = value + 1;`
`}`
`increaseCounter(counter);`
`console.log(counter); // 2`

- Here we have the *counter* value which is impure and the function receives a value that assigns the counter with the value increased by 1. Let's improve that last function and refactor the code.

`let counter = 1;`
`const increaseCounter = (value) => value + 1;`

`increaseCounter(counter); // 2`
`console.log(counter); // 1`

### Pure Function Benefits
- The code's definetly easier to test and we don't need to mock anything. So lets test another way to refactor a code. 

- Example:

`let list = [1, 2, 3, 4, 5];`

`const incrementNumbers = (list) => list.map(number => number + 1);`

- Lets refractor that code from above!

`incrementNumbers(list); // [2, 3, 4, 5, 6]`

### immutability
- When data is immutable, the state cannot change after it has been created. If you want to change an immutable object, you cannot. You have to create a new object with the new value. 

- Example: 
`var values = [1, 2, 3, 4, 5];`
`var sumOfValues = 0;`

`for (var i = 0; i < values.length; i++) {`
  `sumOfValues += values[i];`
`}`

`sumOfValues // 15`

- So for each iteration we change the *i* and the *sumOfValue* state. How do we handle mutability in iteration? Recursion!

`let list = [1, 2, 3, 4, 5];
`let accumulator = 0;

`function sum(list, accumulator) {`
  `if (list.length == 0) {`
    `return accumulator;`
  `}`

  `return sum(list.slice(1), accumulator + list[0]);`
`}`

`sum(list, accumulator); // 15`
`list; // [1, 2, 3, 4, 5]`
`accumulator; // 0`

- Lets OOP 

`class UrlSlugify`
  `attr_reader :text`
  `def initialize(text)`
    `@text = text`
  `end`

  `def slugify!`
    `text.downcase!`
    `text.strip!`
    `text.gsub!(' ', '-')`
  `end`
`end`

`UrlSlugify.new(' I will be a url slug   ').slugify! # "i-will-be-a-url-slug"`

- We are mutating the input state in this process. We can handle this mutation by function compostion or function chaining. 

`const string = " I will be a url slug   ";`
`const slugify = string =>`
  `string`
    `.toLowerCase()`
    `.trim()`
    `.split(" ")`
    `.join("-");`

`slugify(string); // i-will-be-a-url-slug`
`view raw`

### Referential Transperency
- Lets create a *square function*.

`const square = (n) => n * n;`

- This is a pure function and will always have the same output, given the same input.

`square(2); // 4`
`square(2); // 4`
`square(2); // 4`
`//`

### Table of Contents

### Link to Code 102
- [Code 102 Reading Notes](https://jtaisey389.github.io/reading-notes/)

### Link to Code 201
- [Reading Notes 201](https://jtaisey389.github.io/reading-notes201.md/)