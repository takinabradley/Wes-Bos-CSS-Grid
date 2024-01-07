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
