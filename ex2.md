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

