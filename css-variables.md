# CSS Variables / CSS Custom Properties

Declare a variable with `--` followed by a custom name.

E.g `--color-grey-light: rgb(235, 235, 235)` (100 is to signify a very light gray)

This should be placed in the `html` selector in the styles page.

> Example

`html {
    --color-grey-light: rgb(235, 235, 235)
}`

`body {
    background-color: var(--color-grey-light)
}`

## More on selectors

### Differences

`html` CSS rules are applied to the html element and & inherited to nested elements inside.

`:root` The root of the document. In web development using HTML this is the same as selecting the `html` tag. There are however other uses for CSS where you cannot target a `html` tag, and thus targeting `:root` would work instead.

`*` Selects all elements of the HTML document. CSS rules are applied to everything.
