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

You can put multiple names in the square brackets separated by spaces.

## 16 - grid-auto-flow dense block fitting

`grid-auto-flow: dense` can be used to fill holes in the layout by rearranging items. It's not perfect, though, and if you don't have a `grid-item` that fits in the hole, the hole will not be filled.

## 17 - CSS Grid Alignment + Centering

Grid can be useful for centering in non-grid layouts. Useful properties like `justify-content`/`align-content`, `justify-items`/`align-items` exist for grid containers, and items can justify/align themselves with `justify-self`/`align-self`.

`justify` works across the x-axis in CSS grid, and `align` works across the y-axis.

CSS-tricks complete guide to grid is a useful guide, just like it's flexbox equivalent.

The `items` and `self` properties control how the content inside each grid item is displayed between the tracks they fit inside. The `content` options control how all the items are laid out in the container.

`place-items`/`place-content` can also be used as a shorthand to set justify/align properties of items/content at the same time.

## 18 - Re-ordering Grid Items

`order` can be used to change the order of grid items on the page. You may find you need to give many items an order to get items where you want.

`order` effects selecting, and the order screen readers will read (according to wes bos, but it seems like selecting and focus happen in order of the markup. Things should only go bad if it's not okay for content to be read in markup order, I think. More testing needed)

## 19 Nesting Frid with Album Layouts

`repeat(auto-fit, minMax(min, max))` is super useful for responsive grid layouts where you don't want a strict size for grid items.

- grids can be nested, of course

- images can be weird. They're the only element that're not exactly responsive by default.

## 20 - Image Gallery

Placing things in the same grid area overlays them on top of each other by default.

This is nice, since it allows us not to have to mess with positioning CSS.

## 21 - Flexbox vs CSS Grid

In general, grid can do everything flexbox can do.

Flex items can be transitioned, while at the time of the course grid was less transition-able (save the gap property).

Grid is much more consistant across browsers.

It's easy to add more rows, if needed, when using grid for single-dimension layouts.

### Axis flipping

You can adjust `grid-template-columns` from a multi-column layout to a single column layout easily.

It is harder to flip the _order_ of all elements, like you could do in flexbox.

### Controls on the right

With grid, it's easy to separate elements that are meant to be on the left/right side of a container by setting the amount of space you want the first items to use with `grid-template-columns`, then using `grid-auto-flow: column` to tell the rest of the items to squeeze into the left side. This doesn't require an extra wrapper for the left/right elements!

### Flex on item

Flexbox makes it super easy to take a container of many items, and give a single item `flex: 1` so it will take up all the available space.

In Grid, you'd have to write out your `grid-template-columns` property, telling each item how much space they should use.

The flexbox version is also more maintainable, because if one of the other elements that aren't growing are removed/reordered, you don't have to re-write the `grid-template-columns` property.

### Perfectly Centered

About the same

### Self control

- There is a `grid-template` shorthand for `grid-template-columns`/`grid-template-rows`/`grid-template-areas`

Grid items can align and justify themselves in their grid-areas.
Flex items can just align themselves.

### Stacked Layout

Grid lines are rigid, which means you'd have to to manually place items if you wanted each row to be offset from each other. Flex is a much easier option for this with the `flex-wrap` property.

### Unknown content size

Unknown content size can be handled with `auto` when using things ike `grid-template-columns`

### Unknown number of items

You can get more predicable wrapping behavior with `grid-template-columns: repeat(auto-fit, minmax(min, max));` than with flexbox.

### Variable widths on each row

Much easier for flexbox.

Changing the amount of columns in a single row isn't possible with grid, and it'd be a pain to manually span each item.

## 21 Recreating Codepen

Grid is often helpful in web applications specifically, where different widgets need to fit somewhere in the layout. It can be easy to assemble a complex looking layout with just grid.

## 22 - Bootstrappy grid with CSS Variables

- If you want to have a very rigid grid, you'll have to set a grid items `min-width` to be `0`, or use `minmax` to give each cell in a column/row a min width of `0`.

- You can add a CSS variable to a class to determine how much it spans, and editing that variable via JS/inline styles on a specific item will make that item expand/shrink on the grid.

- You can do the same thing for determine grid size by using something like a `--cols` variable in a `repeat()` function.
