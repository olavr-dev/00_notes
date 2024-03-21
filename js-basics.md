# JavaScript

## What is Javascript?

Programming language that can be executed by browsers.

HTML - Defines structure and semantic.

CSS - Styles the page.

JavaScript - Change the page dynamically. (Without loading a new file)

## JavaScript Applications & Use-Cases

- Update displayed data behind the scenes, like weather data, stock prices, chat messages and more.
- Display or use a timer.
- Validate user input and show errors in more customizable ways.
- Display and manage complex overlays.
- Re-order, hide/show or remove elements on the screen, e.g. drag-and-drop list.
- Keep part of websites working even if the internet connection is lost.

## Core JavaScript Syntax & Features

Syntax is the "grammar" of a programming language. You have to adhere to certain rules.

**JavaScript code is executed top to bottom, left to right.**

### Roadmap

1. Variables & Values
2. Arrays & Objects
3. Functions
4. Working with the "DOM"
5. Control Structures

## Understanding Values

`"Hi, I'm Olav"` this text, also known as a String.

`42` This is a number

`"42"` This is a String (text)

`['Hello', 'Goodbye', 'How are you?']` This is an Array. A collection of values.

`{ title: 'Web Developer', location: 'Sandnes', salary: 750000 }` This is an Object. A collection of properties. Instead of having three let variables you group them all into an object. Note the colon instead of an equal sign for setting the value.

## Understanding Variables

Variables are data containers where you can store values.

`var age = 42` Legacy variable. Still works, but do not use. It has been replaced by `let`

`let age = 42` This variable can be set and overwritten

If you want to overwrite the value of age, you do not use the let keyword, but only the name:

`age = 44`

`const`

## Best Practices

- Use camelCase when naming variables
- Be descriptive in your variables
- Stick to either double quotes or single quotes. Both are equally fine, but do not use both randomly.
- Semicolons are optional, but it will clearly mark where a line ends. Be consistent. Always use them, or never.
- Function names should say something about what the operation does. Not what is is used for.

## Math Operations

`10` numbers without decimals are called integers

`5.5` numbers without decimals are called floating point numbers or just floats for short.

`10 / 4` returns 2.5, a float

`10 % 4` using the modulus operator, it returns 2, an integer.

`10 / 4 => 2 * 4 => Remainder: 2` how the modulus operator works

### Some Examples

`let result = (10 + 3 - 5) * 10` Stores the result in a variable

`result = 10 * 4` Overwrites the result variable (Sets it to 40)

`result++` same as result = result + 1

`result--` same as result = result - 1

`result += 5` same as result = result + 5

`result -= 5` same as result = result - 5

`result *= 5` same as result = result \* 5

`result /= 5` same as result = result / 5

## String Operations

`'Olav' + ' ' + 'Øye Rørvik'` Concatenates the strings together to show Olav Øye Rørvik

**Only the + symbol works for concatenations.**

## Manipulating the DOM

### DOM stands for Document Object Model, and that is a long-winded way to say your web page

`window` and `document`

These are build in variables and functions

Window Object `window` means everything in the browser window (including the current tab).

The Document Object `window.document` means everything on the web page.

We can use the document object to manipulate the HTML and CSS of the web page without reloading the page.

#### Since the browser parses all HTML code and saves all elements as JavaScript objects, we can use our JavaScript code to extract data from it or manipulate it

### Selecting DOM Elements

There are two main ways to select DOM elements:

#### You can "drill" into the document object

`document.body.children[2].children[0].href = 'https://google.com'`

This will select the `<body>` => 3rd child `<p>` => 1st child `<a>` and set `href=""` to `href="https://google.com"`

#### You can query elements. This is often easier as you do not have to remember the exact structure of the DOM

`document.getElementById('some-id')`

This will select the HTML element that has `id="#some-id"`

`document.querySelector('.some-class')`

This will select the first HTML element that has `class="some-class"` and return a single element.

`document.querySelectorAll('.some-class')`

This will select all HTML elements that has `class="some-class"` and return an array.

### Changing HTML element content with JavaScript

Accessing the element and adding `.textContent` will let you replace the element's content with plain text.

Accessing the element and adding `.innerHTML` will let you replace the element's content with a mix of plain text and new HTML elements.
