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
