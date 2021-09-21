Codepen for CSS grid:
https://codepen.io/primozt/pen/wveaRpM?editors=1100

If grid items occupy more space than we defined, new row will be automatically added to grid.

**GRID CONTAINER**
```css
/*
	- css ads implicit grid if we didn't define rows/columns
*/

grid-template-rows: repeat(2,150px);
/* 
    - define number and height of rows
    repeat(2,150px): 2 rows with 150px height 
    1fr: occupy all remaining space
		[header-start] 100px [header-end box-start] 200px [box-end main-start] 400px [main-end footer-start] 100px [footer-end]: define names for stat and end of rows
*/

grid-template-columns: repeat(3, 150px);
/* 
    - define number and width of columns
    repeat(3, 150px): 3 columns with 150px width
    repeat(3, 1fr): 3 columns that will occupy all available space
    1fr 2fr 1fr: second column will be double the size of other columns; available space is divided into 4 parts
    50% 1fr 1fr: first column will occupy 50% of container width, others will split the rest of the space
		repeat(3, [col-start] 1fr [col-end]) 200px [grid-end]: define names for start and end of columns
			.header {
				grid-column: col-start 1 / grid-end;
			}

			.sidebar {
				grid-column: col-end 3 / grid-end;
				grid-row: box-start / main-end;
			}

			.main-content {
				grid-column: col-start 1 / col-end 3;
			}

			.footer {
				grid-column: col-start 1 / grid-end;
			}
		max-content: exact size to accomodate content, tries not to make line breaks
		min-content: minimum size to avoid overflows
		minmax: define minimum and maximum size
		repeat(auto-fill, 100px):	auto-fill: grid will automatically create as many tracks as will fit into container
		repeat(auto-fit, 100px): grid will automatically create tracks, but colapses those which are empty (sets width to 0)
*/

grid-template: 150px / auto auto auto;
/*
	- define template for rows and columns, better to use separate definition
	150px / auto auto auto: make a three columns grid layout where the first row is 150px high
*/

grid-template-areas: "head head head head"
                     "box-1 box-2 box-3 side"
                     "main main main side"
                     "foot foot foot foot";
/*
	- define grid areas (use . for empty cells), then define cells for items
		.header {
		  grid-area: head;
		}

		.sidebar {
		  grid-area: side;
		}

		.main-content {
		  grid-area: main;
		}

		.footer {
		  grid-area: foot;
		}
*/

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
    - space between columns
*/

justify-items: center;
/* 
	- define alignment across row axis
	stretch: default value, stretches items across cells
	center: align item horizontally - across row axis
	start: aligns to the left
	end: aligns to the right
*/


align-items: center; 
/* 
    - define alignment across column axis 
    stretch: default value, items automatically stretch 
    center: aligns across coumns axis to the center
    end: align to the bottom of cell 
    start: aligns to the top of cell
*/

justify-content: center;
/* 
	- align grid tracks horizontally - across row axis
	center: aligns grid to center of the container (horizontally)
	start: aligns to left side
	end: aligns to right side
	space-between: divides all empty space between two columns
	space-around: equals space on both sides of the columns
	space-evenly: equal space between columns
*/

align-content: center;
/*
    - align grid tracks vertically - across column axis
    center: align tracks to center of container (vertically)
    start: aligns to top
    end: aligns to bottom
    space-between: divides all empty space between rows so it occupies entire height of container
    space-around: equals space on both sides of the rows
    space-evenly: equal space between rows
*/

grid-auto-rows: 80px; 
/*
	- implicit tracks have 80px height
*/

grid-auto-columns: .5fr; 
/*
	- implicit columns have .5fr width
*/

grid-auto-flow: row;
/*
	- this property tells css how to add implicit grid (columns or rows; default is rows)
	row dense: dense means we want no holes in grid, all holes of grid are filled
*/
```
**GRID ITEM**
```css
grid-area: 2 / 1 / span 2 / span 3;
/*
	- shortened definition for item row and column, better to use separated definition for row and column
	2 / 1 / span 2 / span 3: start on row 2 column 1, and span 2 rows and 3 columns
*/

grid-row-start: 2;
/*
	- number of row line in which you want item to start
*/

grid-row-end: 3;
/*
	- number of row line in which you want item to end; it works without this property, but it is cleaner this way
*/

grid row: 2 / 3;
/*
	- shortened definition for grid-row-start and grid-row-end
*/

grid-column-start: 2;
/*
	- number of column in which you want item to start
*/

grid-column-end: 3;
/*
	- number of column in which you want item to end; it works without this property, but it is cleaner this way
*/

grid column: 2 / 3;
/*
	- shortened definiton for grid-column-start and grid-column-end
	1 / -1: span till the end
	1 / span 2: span across 2 cells
*/

z-index: 10; 
/*
	- if you want grid elements to overlay each other, you can use z-index property
*/

justify-self: start; 
/*
	- overrides justify-items property set on container
*/

align-self: start;
/* 
	- overrides align items propery set on container
*/

order
```
