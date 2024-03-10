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

## Images

`object-fit: fill` default img style - may get distorted to fit the container.

`object-fit: contain` retains the default aspect ratio, but may not fill the container.

`object-fit: cover` scales to fit the container without distorting it.

## CSS Position Property

`position: relative` Set this on the parent element you want to target. This defaults to the `<html>` tag of the page if not otherwise specified.

`position: absolute` Set this on the element you want to target. This will take the element out of the document flow and place it `top:0` and `left:0` on top of the relative element.

`position: fixed` Set this on the element you want to target. This makes it relative to the viewport, which means it stays in the same place, even if the page is scrolled.

`position: static` Set this ont he element you want to target. This will not be affected by `bottom` `left` `right` and `top` properties. It will always be positioned according to the normal flow of the document.
