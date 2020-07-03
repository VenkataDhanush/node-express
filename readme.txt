express intro
1.create node-express
2.create public sub folder -- add html files
3.open cmd - npm init
4.{
  "name": "node-express",
  "version": "1.0.0",
  "description": "Node Express Examples",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "node index"
  },
  "author": "dhanush",
  "license": "ISC",
  "dependencies": {
    "express": "^4.16.3"
  }
}
5.npm install express@4.16.3 --save
6.create index.js

const express = require('express');
const http = require('http');

const hostname='localhost';
const port = 3000;

const app = express();

app.use((req, res, next) => {
    console.log(req.headers);
    res.statusCode=200;
    res.setHeader('Content-Type', 'text/html')
    res.end('<html><body><h1>This is an Express Server</h1></body></html>')

})

const server = http.createServer(app);

server.listen(port, hostname, () => {
  console.log(`Server running at http://${hostname}:${port}/`);
});

7.