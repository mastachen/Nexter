Codepen for CSS grid:
https://codepen.io/primozt/pen/wveaRpM?editors=1100

If grid items occupy more space than we defined, new row will be automatically added to grid.

**GRID CONTAINER**
```css
grid-template

grid-template-rows: repeat(2,150px);
/* 
    - define number and height of rows
    repeat(2,150px): 2 rows with 150px height 
    1fr: occupy all remainig space
*/

grid-template-columns: repeat(3, 150px);
/* 
    - define number and width of columns
    repeat(3, 150px): 3 columns with 150px width
    repeat(3, 1fr): 3 columns that will occupy all available space
    1fr 2fr 1fr: second column will be double the size of other columns; available space is divided into 4 parts
    50% 1fr 1fr: first column will occupy 50% of container width, others will split the rest of the space
*/

grid-template-areas

grid-gap: 30px;
/*
    - define space between columns and rows
*/

grid-row-gap: 30px;
/*
    - space between rows
*/

grid-column-gap: 50px;
/*
    space between columns
*/

justify-items
align-items
justify-content
align-content

grid-auto-rows
grid-auto-columns
grid-auto-flow
```
**GRID ITEM**
```css
/*grid-area
    /*grid row*/
    grid-row-start
    grid-row-end
    /*grid column*/
    grid-column-start
    grid-column-end

justify-self
align-self

order
```
