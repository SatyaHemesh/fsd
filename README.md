Experiment-1:
-------------
Create an application to setup node JS environment and display "Hello World"

AIM: To Write a Program Create an application to setup node JS 
----
environment and display "Hello World"

Recommended Hardware/Software Requirements:
-------------------------------------------
->Intel Based Desktop PC with minimum of 166 MHZ or faster processor with at least 64 MB RAM and 100 MB free disk space
->Nodejs, Visual Studio Code

Source Program:
---------------
1.Install Nodejs from Nodejs.org
2.Create a new folder for your project
3.Initialize a Node.js project using npm init -y
4.Create a file named server.js
5.Write the code to display "Hello World"

//server.js
//import a http module

const http=require('http');

http.createServer((req,res)=>{

    res.writeHead(200,{'Content-Type':'text/plain'});
    res.write('Hello World');
    res.end();
    console.log("server running");

}).listen(8080);

Run the application:
--------------------
node server.js

Visit http://localhost:8080 in your browser to see "Hello World".

Sample Output:
--------------
Hello World

==================================================================
Experiment-2:
-------------
Write a Node JS program tp perform read,write and other operations on a file

Aim:
----
The aim of this experiment is to understand how to perform file operations such as reading,writing,appending,renaming and deleting files using Node.js.This helps in handling file system operations asynchronously and synchronously,which is a fundamental concept in backend development

Recommended Hardware/Software Requirements:
-------------------------------------------
->Intel Based Desktop PC with minimum of 166 MHZ or faster processor with at least 64 MB RAM and 100 MB free disk space
->Nodejs, Visual Studio Code

Source Program:
---------------
fs.readFile() => Reads the contents of a file asynchronously
fs.writeFile() => Writes data to a file asynchronously,replacing                                       the file if it already exists
fs.appendFile() => Appends the data to a file aynchronously, creating the file if it doesn't exist
fs.unlink() => Deletes a file asynchronously
fs.mkdir() => Creates a directory asynchronously
fs.rmdir() => Removes a directory asynchronously

fileoperations.js:
-------------------
//import a fs module
const fs=require('fs');

//writing a file
fs.writeFile('./sample.txt','Testing FS Module',(err)=>{

          if(err)
          {
           console.log("file not created");
          }
         console.log("File created successfully");
  })

//reading a file

fs.readFile('./sample.txt','utf8',(err,data)=>{
           if(err)
           {
            console.log("file not found");
            return;
           }
        console.log('Data in file:',data);
     
})

//Appending a file

 fs.appendFile('./sample.txt','adding extra',(err,data)=>{

          if(err)
           {
            console.log("file not updated");
            return;
           }
        console.log('Updated Data in file:',data);
           
   })

//Deleting a file

fs.unlink('./sample.txt',(err)=>{

          if(err){
           console.log("file not deleted");
          };
          console.log('file deleted');
   })

//creating a directory

fs.mkdir('./test1',(err)=>{
           if(err){
            console.log("Directory not created");
           }
           console.log("Directory created");
        });

=================================================================
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

===============================================================
