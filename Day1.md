# Introduction to Node.js

>### What is Node.js
<p align="justify">Node.js is a runtime environment that which allows developers to run JavaScript code out side of a web browser. It's fast and , light weight and , really good at handling many tasks at the same time. This makes it perfect building things like chat apps, online games, or any other tools that we need to work in our real time.</p>  

>### Installation of Node.js
Visit the [Official Node.js](https://nodejs.org/en/download/package-manager) Webpage and select the file as per your system type & install it. After that finish the setup and next check it whether it is installed successfully or not by chrecking its version in terminal or powershell.

>### What is Server ?
<p align="justify">A server that which stores the information and shares it with other devices when it get request. It is always ready to give the responses for the requests from other computers, Phone or any other devices.</p>

#### Example:  
<p align="justify">In your browser you are requesting that youtube then the youtube server tooks that request and that youtube server responses to you as opening youtube in your browser.</p>

>### First Node.js Program
Here the sample node.js program to run the node.js program file we need to run this command __node filename.js__ 

index.js
```
function hello(){
    console.log("Hello, World!");
}
hello();
```
>### Node.js REPL
The Node.js REPL stands for Read-Eval-Print Loop, and it’s like a playground where you can quickly try out JavaScript code in real-time.
To start the REPL, simply type `node` in your terminal or command prompt and press Enter.
 1. `Read`  : It reads the code you type.
 2. `Eval`  : It evaluates (runs) your code.
 3. `Print` : It prints the result.
 4. `Loop`  : It does this again and again until you quit.

>### What is package.json file
The `package.json` file is a JSON file that contains the complete information about the project like what are the packages are used in project and all those details such as:

1. __Basic Information :__
   - The __name__ and __version__ of the Project.
   - The __description__ of the Project.
2. __Dependencies :__
   - All the list of __libraries__ or __packages__ which is used in the project
3. __Scripts :__
   - In this the commands we can define that which we used to start the project, run tests, or building it.
   - Example: `"start" : "node index.js"` which is we can directly run the command `npm start` to run the project.
4. __Others :__
   - It can also inculdes our project's license, author name, and other data.
