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
