# Code 301 Reading Notes

## Read 04 Responsive web design and Regular Expressions

**Grid Column Start**
- For example grid-column-start: 3 an item in the first vertical grid line on the left will move over three grid rows. 

**Grid Column End**
- When you use grid-column-start the element will span exactly on one column. You can expand across multiple columns by adding the grid-column-end property. 

- Using the grid-column-end we will span the grid elements to only the items that need it. The great part about grid-column-end is that you can have a negative value. If you had all of your elements in the right hand corner you can specify a negative value with grid-column-end to span the sections to the left. 

**Span**
- Instead of defining a grid item based off of the start and end positions of the grid lines. You can define it based on you desired column width using the span keyword. **Note** span only works with positive values

**Shorthand Grid Column**
- Typing both grid-column-start and grid-column-end every time is repetitive. There is a shorthand property that accepts typing both values at once, separated by a slash. For example, grid-column: 2 / 4
This will set the grid item to start on the 2nd vertical grid line and end on the 4th grid line.

**Grid Row Start**
- One thing that sets CSS grids apart from flexbox is that you can position items in two dimensions: Columns and rows. Grid-row-start works much like grid-column-start except along the vertical axis. 

**Grid Area**
- Typing out both grid-column and grid-row is repetitive. There is another shorthand for that which is grid-area which accepts four values. 

One example of this would be grid-area: 1 / 1 / 3 / 6;.

**Order**
- If you don’t place grid items with grid-area, grid-column, grid-row, etc. These are automatically placed according to their order in the source code. We can override this using the order property. Grid items have a default order of 0, this can be set to any positive or negative value, similar to z-index. 

**Grid Template Columns**
- So far the garden has been set up as a grid with five columns, each 20% of the full width and height. This was done with the rules grid-template-columns: 20% 20% 20% 20% 20%. The grid can be set up however you like. 

**Repeat**
- Calling a bunch of columns with identical widths can be tedious. There is the repeat function to help with that. 

**Fraction**
Grid also introduces a new unit, the fractional fr. Each fr unit allocates one share of the available space. For example, if two elements are set to 1fr and 3fr respectively, the space is divided into 4 equal shares; the first element occupies 1/4 and the second element 3/4 of any leftover space.

### Table of Contents

### Link to Code 102
- [Code 102 Reading Notes](https://jtaisey389.github.io/reading-notes/)

### Link to Code 201
- [Reading Notes 201](https://jtaisey389.github.io/reading-notes201.md/)