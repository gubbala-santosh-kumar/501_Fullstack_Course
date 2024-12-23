# NPM ( Node Package Manager )
>### Why there is need for a Library Ecosystem ?
<p align="justify">A library Ecosystem useful for the developers to reuse pre-built, well tested components saving the time and ensuring the consistency accross the projects. It fosters collaboration, innovation, and scalability while improving the product quality and softare quality</p>

>### What is NPM ?
<p align="justify"><a href="https://www.npmjs.com/">NPM</a> is a package manager for JavaScript programming language. It is the default package manager for the JavaScript runtime environment Node.js. It is used to install, update, and manage dependencies in a Node.js project. It is a command line tool to install the packages which is required to our project. This NPM is automaticall installed when we install the Node.js to check the version of the both node.js and npm we simply use this commands
</p>

- `node --version` We can get the Version of Node.js

- `npm --version` We can get the Version of NPM.

>### What is NPM Scripts ?
<p align="justify">NPM scripts are a way to run scripts in your project using npm. 
They are defined in the `package.json` file and can be run using the `npm run script-name` command. They are useful for automating tasks such as building, testing, and deploying
your project. They can also be used to run custom scripts that are specific to your project.</p>

Example : `"start":"node index.js"` Which is used to run that app using the simple command called `npm start`.

>### Built-in fs Module
<p align="justify">The `fs` module is a built-in Node.js module that provides an interface to the file system. It allows you to read and write files, as well as perform other operations on the files we can use this file system module to do all these operations on the file by using both synchronous and asynchronous files.</p>

Node.js fs modules used for some common tasks like:
- Create files
- Read files
- Update files
- Delete files
- Rename files

>### Stream in Node.js
<p align="justify">
A stream in Node.js is a way to handle large amounts of data in
chunks, rather than loading the entire data into memory at once. This is useful for handling large files
or network requests. 

__There are two types of streams in Node.js:__
- readable and writable streams. Read
able streams are used to read data from a source.
- writable streams are used to write data to
a destination.
</p>

```
const stream = require('stream');
```
We need to make sure  write the above thing in our code that to use the streams in our code.

>### Accepting Input form CLI
<p align="justify">
Node.js which is also provides the readline module whihc is allow the user to get input from a readable stream such as the `process.stdin` stream, which during the execution of a Node.js program this asks the input in the terminal input. This wil takes the input in one line only.
</p>

#### Example Code
```
const readline = require('node:readline');

const rl = readline.createInterface({
  input: process.stdin,
  output: process.stdout,
});

rl.question(`What's your name?\n`, name => {
  console.log(`Hi ${name}!`);
  rl.close();
});
```
After run this it will take the input from the user then after it will gives the output as like below

__Sample Output__
```
What is your name?
Santosh Kumar       <-----("You need to enter this.")
Hi Santosh Kumar!
```
#### Using the Minimist to accept CLI input 
<p align="justify">The minimist module will analyze arguments we pass the command line. It provides the argument list into an array for the simple use. In this array we can use the index names aswell as the numbers to access the values.</p>

__Sample Code__
```
var argv = require('minimist')(process.argv.slice(2))
console.log(argv)
```
__Sample Output__
```
{ _: [] }
```