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
- Typing both grid-column-start and grid-column-end every time is repetative. There is a shorthand property that accepts typing both values at once, seperated by a slash. For example, grid-column: 2 / 4
This will set the grid item to start on the 2nd vertical grid line and end on the 4th grid line.

**Grid Row Start**
- One thing that sets CSS grids apart from flexbox is that you can position items in two dimensions: Columns and rows. Grid-row-start works much like grid-column-start except along the vertical axis. 

**Grid Area**
If typing out both grid-column and grid-row is too much for you, there's yet another shorthand for that. grid-area accepts four values separated by slashes: grid-row-start, grid-column-start, grid-row-end, followed by grid-column-end.

One example of this would be grid-area: 1 / 1 / 3 / 6;.