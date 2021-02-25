# Code 301 Reading Notes

## Read 10 The Call Stack

- A call stack is a mechnisim for n interpreter to keep track of it's place in a scritp that calls multiple functions. When the script calls a function the interpreter adds it to the call stack and then carries out the function.

- Example: 

`function greeting() {
   // [1] Some code here
   sayHi();
   // [2] Some code here
`}
`function sayHi() {
   return "Hi!";
}`

`// Invoke the `greeting` function`
`greeting();`

`// [3] Some code here`

- Here is how the code would execute
  1. Ignore all the functions till it reaches `greeting()`
  2. Adds the `greeting()` to the call stack
  3. Executes all lines of code
  4. Moves to the `sayHi()` function invocation
  5. Add `sayHi()` to the call stack
  6. Exacute all lines of code within `sayHi()` 
  7. Return execution to the line that invoked `sayHi()` and continue to the `greeting()` function
  8. Delete the `sayHi()` function 
  9. When everything incide the `greeting()` function has been executed, return to its ivoking line to execute the remaining JS code. 
  10. Delete the `greeting()` function from the call stack

### The Call Stack and why it is necessary

- The call stack is primarly used for function invocation. The call stack is single, function execution is done one at a time from top to bottom. The call stack is vital to Asynchronous programing.

- Asynchronous JavaScript, we have a callback function, an event loop, and a task que. The callback function is acted upon by the call stack during the execution after the call back has been pushed back by the event loop. 

- At the basic level a call stack is a data structure that uses the Last In, First Out (LIFO) principle to temporarily store and manage function invocation. 

- Example:

`function firstFunction(){
  throw new Error('Stack Trace Error');
}`

`function secondFunction(){
  firstFunction();
}`

`function thirdFunction(){
  secondFunction();
}`

`thirdFunction();`

- You will notice that the arrangement begins with the firstFunction() (which is the last function that got into the stack, and is popped out to throw the error), followed by the secondFunction(), and then the thirdFunction() (which is the first function that gets pushed into the stack when the code is executed).

### Understanding Errors
- If Javascript generates and error, then it throws and exception. 

Here are a variety of errors and what they mean.
    - Name: Type of error
    - Message: Description
    - fileNumber: Name of the Javascript
    - lineNumber: Line number of the error
  
Descriptions:
    - Error Generic Error -the other errors are all based upon this error
    - SyntaxError: Syntax has not been followed
    - Reference Error: Tried to reference a variable that is not declared/within scope.
    - TypeError: An unexpected data type that cannot be coerced
    - RangeError: Numbers not in an acceptable range
    - URI Error: encodeURI(), decodeURI(), and similar methods used incorrectly
    -EvalError: eval()function used incorrectly

### A Debugging Workflow
- Debugging is about deduction: Eliminating potential causes of an error. 

1. Where is the problem
2. What exactly is the problem

- A great way to review your code live is to use the DEV tools inside of the Javascript console

- Within your javascript code you can insert lines to inspect your code within the console. THere are a few different methods that be utilized to see where the errors in your code is taking place.

1. Console.info ()
2. Console.warn ()
3. Console.error ()

### Writing Tabular Data
- In browsers that support it, the console.table() method lets you output a table showing: objects, arrays that contain other objects or arrays

- You can also use the console.assert() method, you can test if a condition is met. 

### Handling Exceptions
- If you know your code might fail, use try, catch and finally.

1. Try - Will try to execute the code
2. Catch - If there is an exception, run this code
3. Finally - This always gets executed

### Throwing Errors
- If you know something might cause a problem for your script, you can generate your own errors before the interpreter creates them. 

### Table of Contents

### Link to Code 102
- [Code 102 Reading Notes](https://jtaisey389.github.io/reading-notes/)

### Link to Code 201
- [Reading Notes 201](https://jtaisey389.github.io/reading-notes201.md/)
