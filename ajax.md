# What is Ajax?

**A**synchronous **J**avaScript **A**nd **X**ML

The **AJAX** term is a bit dated, as we mostly use **JSON** instead of XML now.

Ajax enables sending HTTP requests via JavaScript. Not like NodeJS that is running on the back end, but using JavaScript running on the front end.

## Why send HTTP requests from within JavaScript?

### Sending HTTP requests **without** Ajax

- Enter a URL (sends a GET request to the URL)
- Click a link (sends a GET request to the URL)
- Submit a form (sends a GET or POST request to the URL)

All of the above leads to a new page being loaded.

### Sending HTTP requests **with** Ajax

- Send a HTTP request via browser-side JavaScript
- Handle response in the same script code

You have full control over the browsers behavior and can prevent loading of a new page.

>

### Lets take a look at the two built-in browser-side JavaScript features you can use

## `XMLHttpRequest`

An object built into browser-side JavaScript that contains utility methods for sending HTTP requests via JavaScript.

- Originally developed to send XML data
- A bit clunky to use. Almost no one use it from the ground up these days
- Typically used indirectly via commonly used third-party libraries like [Axios](https://axios-http.com/docs/intro)

### What is XML?

E**x**tensible **M**arkup **L**anguage

```xml
<post-comment>
    <title>This was great!</title>
    <comment-text>Thanks a lot - this was really helpful!</comment-text>
</post-comment>
```

Data format for structuring and formatting text data in a machine-readable way.

Looks a lot like HTML which is based on XML, but HTML is standardized and XML is not.

XML is too verbose with all the tags wrapping the text, and is a lot of unnecessary work.

>

#### Modern web development has moved on to use JSON (**J**ava**S**cript **O**bject **N**otation) instead of XML

```json
{
  "title": "This was great!",
  "commentText": "Thanks a lot - this was really helpful!"
}
```

This is way more condensed and a lot more human-readable. It is also just as readable by machines. It looks a lot like a JavaScript object, but all keys (property names) and values have to be between double quotes.

## `fetch()`

fetch() is a modern alternative to XMLHttpRequest

An object built into browser-side JavaScript that contains utility methods for sending HTTP requests via JavaScript.

- Uses modern JavaScript features like Promises
- Relatively straightforward to use
- Alternative to XMLHttpRequest and third-party libraries like [Axios](https://axios-http.com/docs/intro)

## More HTTP Methods

### Default browser methods

- `GET` Fetch some data
- `POST` Store some data

### Ajax / JavaScript driven Http requests

- `PUT` Replace / Update some data
- `PATCH` Update some data
- `DELETE` Delete some data
