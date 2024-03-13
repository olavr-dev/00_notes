# Responsive Web Design

## Mobile First Design

This is the best way to design web sites in 2024.

## Layout

Use `flexbox` for 2 dimensional layout.

Use `grid` for 3 dimensional layout.

For example: A nav bar works best with `flexbox` and a container filled with content cards that might move based on responsive design or that you need to position individually, it's easier to use `grid`.

## Font Size Units

`px` Easy to understand, but limited user focus and not scalable. If you set `font-size` to a pixel value, it will not scale with their browser's font size scaling. Not suitable for responsive design, and bad for accessability.

`%` Relative to the parent element size. Hard to manage due to cascading nature, such as nested elements.

`em` Relative to font-size. As with `%` it is hard to manage due to it's cascading nature.

`rem` Relative to the root element font size. `1em` == `16px`. Does not cascade, and stays the same no matter how many nested elements you have. Preferred choice if applicable.

## Media Queries

`@media (min width or max-width: 1200px){ }`

**You can set as many media query breakpoints you like.**

Desktop first use `max-width` and scales downwards.

Mobile first use `min-width` and scales upwards.
