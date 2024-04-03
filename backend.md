# Backend (server-side) development

Server-side code is written in a language that can be executed on a server.

Since a "server" is in the end just a regular computer, we can use basically any programming language.

Some languages are more suited for this though, and some of the more popular ones for web development are:

`Python` `PHP` `C#` `NodeJS (JavaScript)`

## NodeJS

NodeJS is JavaScript for the server-side. It is a JavaScript Runtime.

It is JavaScript as learned for frontend use, but with more features like read + write files, parse incoming requests, send responses and more.

### How to connect to a server

`const http = require('http')` The require function is built into NodeJS

`const server = http.createServer()`

`server.listen()` Listen to server at port

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
