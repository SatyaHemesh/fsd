Experiment-3:
-------------
Write a Node JS Program to read form data from query string and generate response using NodeJS

Aim: The aim of this experiment is to understand how to handle user inout via query strings in a Node.js application and generate an appropriate response

Recommended Hardware/Software Requirements:
-------------------------------------------
->Intel Based Desktop PC with minimum of 166 MHZ or faster processor with at least 64 MB RAM and 100 MB free disk space
->Nodejs, Visual Studio Code

Source Code:
------------
const http = require("http");
const url = require("url");

//create an http server

const server = http.createServer((req, res) => {
  const parsedUrl = url.parse(req.url, true);
  const query = parsedUrl.query;

  // Extract form data from query string
  const name = query.name || "Guest";
  const age  = query.age || "Unknown";
  const email = query.email || "Not provided";

  // Send response header
  res.writeHead(200, { "Content-Type": "text/html" });
 //Generate response with submitted data
  res.write('<h1>Form Data Received<h1>')
  res.write('<p>Here is the data you submitted<p>')
  res.write('<ul>
    <li><strong>Name:</strong> ${name}</li>
    <li><strong>Age:</strong> ${email}</li>
    <li><strong>Email:</strong> ${email}</li>
  ');
  res.end();
});

server.listen(3000, () => {
  console.log("Server running at http://localhost:3000");
});
