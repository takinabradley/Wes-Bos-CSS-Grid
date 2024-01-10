# CSS Grid Video Course

Hey! These are the starter files and finished solutions for Wes Bos's video course. Grab the full course over at [CSSGrid.io](https://CSSGrid.io).

## 03 CSS Grid Fundementals:

- `grid-template-columns` accepts multiple width values, and creates columns of those widths.
- `grid-tempalte-rows` accepts multiple height values, and creates rows of those heights.
- `gap` or `grid-gap` adds gaps between columns and rows (or in-between grid tracks).
- `auto` value automatically layouts columns between the ones you set.
- `repeat(times, value)` is a useful CSS function for grid layouts

## 04 CSS Grid Dev Tools

- Firefox dev tools are pretty great for Grid. Use the Layout tab!

- You'll always have one more track than you'll have columns/rows

- devtools displays explicit tracks, implicit tracks, grid edge, and gaps differently.

## 05 CSS Grid Implicit vs Explicit Tracks

- If you create tracks, they'll be marked as such (explict)

- If you didn't, and there is no room for elements that are supposed to fit in the grid, the browser will create implicit tracks.

- `grid-auto-rows`/`grid-auto-columns` allows you to define how implicit rows and columns should be sized.

## 06 grid-auto-flow explained

- `grid-auto-flow` determines if by default CSS Grid tacks new elements onto columns or onto rows

## 07 Sizing tracks

- Percentages overflow with gaps larger than 0. `fr` units solve this
- `fr` units will take up the space left when you use other units
- The default width of block elements you might use as a grid is 100%, the default height depends on content. That's why `fr` units on height don't by default try to take up the height of the viewport.
- `auto` with an `fr` unit will fit to the size of the content, and allow `fr` units to take up the rest of the space. It will effect other elements in the grid.

## 08 - CSS Grid repeat function

- The repear function will repear multiple values passed into it

## 09 - Sizing grid items

- setting a width on a grid-item will effect the layout of the grid Similarly, if content on a grid-item is too long, it will do the same thing

- The `grid-column` option for grid-items can help us here. For example, `grid-column: span 2` tells an item to span two columns without effecting the rest of the grid layout.

- Telling an item to span more than there are available columns left will cause it to flow to the next line, and create dead space in the layout. By default, more implict rows will be created. Telling an item to span more than there are template columns will make new implicit columns

- Using the `dense` keyword in `grid-auto-flow` will cause elements in front of a spanning element to fill in the dead space.

## 10 Placing Grid Items

- `grid-column` is shorthand for `grid-column-start` and `grid-column-end`.

- `grid-column-start` tells an item what track it should start at
- `grid-column-end` tells an item what track it should end at
- `grid-column`/`grid-row` can also take `start / end` value syntax
- `span` value just says to start were you would normally be, and span from there for each of these.
- `-1` can be used as a value to select the end, if you don't know how many tracks you might have. Higher negative numbers will select from the end. This may behave unexpected for rows if you don't have explicit rows
- (same for `grid-row-start`/`grid-row-end`/`grid-row`)

## 11 Spanning and Placing Cardio

## 12 auto-fit and auto-fill

- The `auto-fit` keyword for the `repeat()` function tells CSS Grid to automatically create rows/columns until it doesn't need to make any more (ends the grid at the end of the content).
  (It seems to squeeze content down and remove unused cells in order to fit it)
- The `auto-fill` keyword for the `repeat()` function tells CSS Grid to do the same, but to fill the additional space with rows/columns of a similar size.

- auto-fill allows you to place items past the normal auto-fit of a grid, but still keep the ability to place items past it easily with values like `-1`.

## 13 Using minmax() for responsive grids

- `minmax` with auto-fill/auto-fit will create tracks matching the maximum value

- `minmax` is useful with `fr` units, as it allows the items to stretch/shrink a bit based on the min/max size as the window resizes.

- `fit-content` can be used sometimes to fit the content to a maximum width, with the mimimum being the width of the content (?)

## 14 - Grid Template Areas

### Areas

- `grid-template-areas` allows you to name cells/spans of cells, and then place individual grid-items in those named cells with `grid-area: <name>`

- `grid-template-areas` are easily redefined via media queries

### Area line names

When you use areas, you get area line names for free like `<area-name>-start` and `<area-name>-end`

## 15 - Naming Lines in CSS Grid

You can name lines using square brackets `[]` in `grid-template-columns`/`grid-template-rows`. Then you can use these names in `grid-column`/`grid-row`.

Ex: `grid-template-columns: [left] 1fr [right]`

YOu can put multiple names in the square brackets separated by spaces.
