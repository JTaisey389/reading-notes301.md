# Code 301 Reading Notes

## Read 02 jQuery, Events, and The DOM

### JQuery Chapter 7
- jQuery offers a simple way to achieve a variety of common JavaScript tasks quickly and consistently, across all major browsers and without any fallback code needed.

- With jQuery we can:
  
  1. Select Elements
  2. Perform Tasks
  3. Handle Events

  ### What is jQuery?
  - jQuery is a JavaScript file that you include with your web pages. This allows you to find elements using CSS-style selectors and then do something with the elements. 

  - A function called jquery() lets you find one or more elements in the page. **$** is often used as a shorthand to save typing out jQuery().

  Example: $('li.hot') 
  // **This is the whole function which creates the object**
  // **The 'li.hot' is the selector**

- Now we want to do something with the the elements using jquery methods.

Example: $('li.hot').addClass('favorite');
- Lets break that down.
  - As before this is the jquery object **$('li.hot')**
  - The **.** is the member operator which is part of the **method**
  - Next we add to the method **addClass**
  - Lastly we pass in the parameter(s) **('favorite');**
  - The whole section after the member operator is the **method**
  - **.addClass('favorite');**

### A basic jQuery example
1. $(':header').addClass('headline');
2. $('li:lt(3)').hide().fadeIn(1500);
3. $('li').on('click', function() {
  $(this).remove();
});

1. The first line selects all of the `<h1> - <h6>` headings and add a value of headline to their class attributes
2. Second line selects the first three list items and does two things: Elements are hidden to allow the next step. Next the elements fade into view
3. The last three lines set an event listener on each of the `<li>` elements. 

Reminder of color used to cover the priority of each item list:
- Hot: Red
- Orange: Normal
- Cool: Mint
- Complete: Gray

### A matched set/jQuery Selection
- When you select one or more elements, a jQuery object is returned. This is known as a **matched** set.

- Single element selector: 
$('ul') - This selects the un-ordered list

- Multiple elements selector:
$('li') - This selects items within a list

- Some jQuery methods both retrieve information from, and update the contents of elements. We **get information** and then we **set information**.

### JQuery objects store references to elements
- When you create a selection with jQuery, it stores a reference to the corresponding nodes within the DOM tree. 

Example: 
**<>** Nodes take in the DOM and take up a tile
**var** Variables take of a tile
**$** Complex JavaScript objects may take up several tiles 

### **Looping**
- In plain JavaScript, if you wanted to do the same thing to several elements, you write code to loops through all of the elements. With jQuery when a selector returns multiple elements, you can update all of them using a simplified method.

Example:
$('li em').addClass('seasonal');
$('li.hot').addclass('favorite');

Example: $('li.hot').addClass('favorite');
- Lets break that down.
  - As before this is the jquery object **$('li.hot')**
  - The **.** is the member operator which is part of the **method**
  - Next we add to the method **addClass**
  - Lastly we pass in the parameter(s) **('favorite');**
  - The whole section after the member operator is the **method**
  - **.addClass('favorite');**

### **Chaining**
- If you want to use more than one jQuery method on the same selection of elements. In the statement below we **chain** the elements together.

Example: $('li'[id!="one]').hide().delay(500).fadeIn(1400);

### Checking a page is ready to work with
- jQuery's **.ready()** method checks that the page is ready for your code to work with.

Example: $(document).ready(function() {
  <!-- script goes here -->
});

**$(document)** creates a jQuery object representing the page
**.ready(function()** When the page is ready, the function inside the parentheses of the .ready() method is run. 

Shorthand Example: $(function() {
  <!-- script goes here -->
});

**$(function() {** this is a shortcut for ready event method

### Getting Element Content
- The **.html** and **.text()** methods both retrieve an update the content of elements.

Examples: 
var &listHTML = $('ul').htm;();
$('ul').append($listHTML);

var $listText = $('ul').text();
$('ul').append(`'<p>'` + $listText + `'</p>'`);

var $listItemHTML = $('li').html();
$('li').append(`'<i>'` + $listItemHTML + `'</i>'`);

var $listItemText = $('li').text();
$('li').append(`'<i>` + $listItemText + `'</i>'`);

### Updating Elements
- Here are four methods that update the content of all elements in a jQuery selection

**.html()**

**.text()**

**.replaceWith()**

**.remove()**

### Table of Contents

### Link to Code 102
- [Code 102 Reading Notes](https://jtaisey389.github.io/reading-notes/)

### Link to Code 201
- [Reading Notes 201](https://jtaisey389.github.io/reading-notes201.md/)