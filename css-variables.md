# CSS Variables / CSS Custom Properties

Declare a variable with `--` followed by a custom name.

E.g `--color-grey-100: rgb(235, 235, 235)` (100 is to signify a very light gray)

This should be placed in the `html` selector in the styles page.

> Example

`html {
    --color-grey-100: rgb(235, 235, 235)
}`

`body {
    background-color: var(--color-grey-100)
}`
