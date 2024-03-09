# HTML & CSS Layouts and Positioning

## Page Structure

This is how you would want your `<body>` section to look like. Semantic tags are important for making it clear what type of content you are providing, and will also give better Google ranking.

Header `<header>`

Navigation Bar `<nav>`

Main Content `main` will also contain various `<article>` `<section>` `<div>`

Sidebar `<aside>` often placed inside `main`

Footer `<footer>`

You can take a section "out" of the document flow by setting its position to absolute or fixed. This will overlay the section on top of the page.

## Flexbox

Use `display: flex` on the parent container

Default mode is `flex-direction: row` so the children will be displayed beside each other.

`flex-direction: column` will display them underneath each other.

`flex-wrap: nowrap` is the default. Change to `flex-wrap: wrap` to make the flex move underneath each other when the screen size gets too small to show them side by side.
