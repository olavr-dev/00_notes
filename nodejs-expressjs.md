# Backend (server-side) development

Server-side code is written in a language that can be executed on a server.

Since a "server" is in the end just a regular computer, we can use basically any programming language.

Some languages are more suited for this though, and some of the more popular ones for web development are:

`Python` `PHP` `C#` `NodeJS (JavaScript)`

## File and Folder Names for Backend Development

`app.js` This is the common file name for the main js file

`views` This is the common folder name for the html files being served dynamically and not available to the public directly.

`public` This is the common folder name for static files like stylesheets, scrips and images. These are directly available to the public. (can be accessed via the url field)

## NodeJS

NodeJS is JavaScript for the server-side. It is a JavaScript Runtime.

It is JavaScript as learned for frontend use, but with more features like read + write files, parse incoming requests, send responses and more.

### How to connect to a server using NodeJS

```javascript
const http = require('http'); // The require function is built into NodeJS

function handleRequest(request, response) {
  response.statusCode = 200;
  response.end('<h1>Hello, world!</h1>');
}

const server = http.createServer();

server.listen(3000); // Listen to server at port 3000
```

#### Example of how you would connect to a website

`amazon.com` => Send a request to Amazon's server

`amazon.com:80` Port 80 is the default port for http (unsecure)

`amazon.com:443` Port 443 is the default port for https (secure)

## Server status codes

Web servers communicate the status of a request & response via standardized status codes.

`200` **Success!** Request parsed successfully and a response could be generated and sent without any problems

`404` **Client-side error!** The requested resource / URL was not found. The expected response could not be generated.

`401` **Client-side error!** The requesting client (user) is not authorized to access the requested resource / URL (e.g. not being logged in.)

`500` **Server-side error!** The request was valid but something went wrong on the server. The expected response could not be generated.

## Easier NodeJS Development with ExpressJS

ExpressJS is a third-party NodeJS library that simplifies the creation of web servers and the handling of requests and responses.

### Installing ExpressJS with NPM

`npm init` This will initialize NPM and set up a package.json file.

`npm install express` This will install express and all dependencies.

### How to connect to a server using ExpressJS

#### _Express will set the server status code to 200 by default_

```javascript
const express = require('express');

const app = express();

// localhost:3000/currenttime
app.get('/currenttime', function (request, response) {
  response.send('<h1>' + new Date().toISOString() + '</h1>');
});

// localhost:3000/
app.get('/', function (request, response) {
  response.send('<h1>Hello, world!</h1>');
});

app.listen(3000);
```

To run the app on the local server, use `node app.js` (replace app.js with your js file)

In the terminal, to exit out of the server, click `CTRL + C`

Restart the server when you save changes to the app.

## Installing nodemon

This package will make it easier to test your code without having to stop and start the server for every change / save.

`npm install nodemon --save-dev`

`--save-dev` this marks nodemon as dev dependency used for development.

Add the following script to package.json

```json
"scripts":{
  "start": "nodemon app.js"
}
```

To run the app on the local server, use `npm start`

`"start":` is a reserved special script name. If you name the script anything else you have to start it with `npm run your-script-name`

## Template Engines

Templates are placeholders within the HTML code with different syntax.

One of the most popular Express template engine is EJS (Embedded JavaScript Templating).

Command to install the EJS package for your project:

`npm install ejs`

Enable the engine in your project. Typically the first thing after creating the app object.

`app.set('views', path.join(__dirname, 'views'))`

`app.set('view engine', 'ejs')`

Convert the html files you want to use to ejs files.

`index.html` => `index.ejs`

### Serving HTML files dynamically

Instead of creating a file path and sending back the file manually with Express

```javascript
app.get('/', function (req, res) {
  const htmlFilePath = path.join(__dirname, 'views', 'index.html');
  res.sendFile(htmlFilePath);
});
```

Using EJS you can instead use the `render()` method on the response object.

```javascript
app.get('/', function (req, res) {
  res.render('index'); //index.ejs, but omit the file extension.
});
```

This renders a template. Parsing a template file with the help of a template engine and convert it to html that will be sent back to the browser.

In the .ejs template file, specify the key using this syntax:

`<%= nameOfKey %>`

In app.js, add this key to the render method as a second parameter.

```javascript
app.get('/', function (req, res) {
  res.render('index', { nameOfKey: variableToShow });
});
```

#### Writing your own EJS logic using a for loop

In app.js

```javascript
app.get('/restaurants', function (req, res) {
  const filePath = path.join(__dirname, 'data', 'restaurants.json');

  const fileData = fs.readFileSync(filePath);
  const storedRestaurants = JSON.parse(fileData);

  res.render('restaurants', { numberOfRestaurants: storedRestaurants.length, restaurants: storedRestaurants });
});
```

In restaurants.ejs

```html
<main>
  <h1>Recommended restaurants</h1>
  <p>Find your next favorite restaurants with help of our other users!</p>
  <p>We found <%= numberOfRestaurants %> restaurants.</p>
  <ul id="restaurants-list">
    <% for (const restaurant of restaurants) { %>
    <li class="restaurant-item">
      <article>
        <h2><%= restaurant.name %></h2>
        <div class="restaurant-meta">
          <p><%= restaurant.cuisine %></p>
          <p><%= restaurant.address %></p>
        </div>
        <p><%= restaurant.description %></p>
        <div class="restaurant-actions">
          <a href="<%= restaurant.website %>">View Website</a>
        </div>
      </article>
    </li>
    <% } %>
  </ul>
</main>
```

### EJS Includes

Includes are .ejs files that contain parts of a page. Used to split large files into more manageable pieces.

You split parts of the html page into separate .ejs files. One for the `header`, one for the `main`, one for the `footer` etc.

You can then include these .ejs files where you want to render this html content.

`<%- include('includes/header') %>` Path is relative to file. File extensions are omitted.

#### NOTE

`<%= contentHere %>` This will escape any content added by the user for security purposes and output it as plain text.

`<&- contentHere %>` This will not escape any content and will output anything including html code and scripts.
