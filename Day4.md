# Event Loop, Callback, Promises, Closures , Async & Await.

>### What is Event Loop
<p align="justify">
Event Loop is a mechanism that allows a program to handle multiple events or tasks concurrently. It is a centralized control structure that manages the execution of tasks, ensuring that each task is executed in a sequential manner, while allowing other tasks to be executed concurrently.
</p>

__Sample Code__
```
console.log("First Message");

setTimeout(() => {
    console.log("Second Message");
    }, 1000);

console.log("Third Message");
```
__Sample Output__
```
First Message
Third Message
Second Message
```
In the above code ("Second Message") message wil prints after the completion of all the code execution and later it will take one second time to print this message because of the event loop mechanism. 

>### What is a Callback?
<p align="justify">
A callback is a function that can be passed as an argument to the another function, which is can be executed later time, usually after the completion of an asynchronous operation.
</p>

__Sample Code__
```
function greet(Name, callback) {
    console.log("Hello " + Name + "!");
    callback(); // Call me back when done
}

let Name="Jhon";
greet(Name, function() {
    console.log("How are you?");
});
```
__Sample Output__
```
Hello Jhon!
How are you?
```
<p align="justify">
In the above code, the callback function is called after the completion of the greet function. The callback function is passed as an argument to the greet function, which is executed later time.
</p>

>### What is a Promise?
<p align="justify">
A Promise is a result object that is used to handle asynchronous operations. It represents a value that may not be available yet, but will be resolved at some point in the future.
</p>

__Sample Code__
```
const cleanRoom = new Promise((resolve, reject) => {
    let isClean = true;

    if (isClean) {
        resolve("Room is clean!");
    } else {
        reject("Room is still messy!");
    }
});

cleanRoom
    .then(message => console.log(message)) // "Room is clean!"
    .catch(error => console.log(error));  // If rejected
```

__Sample Output__
```
Room is clean!  
```
<p align="justify">
In the above code, a Promise is created with a resolve and reject function. The resolve function is called when the room is clean, and the reject function is called when the room is still messy.
</p>

>### What is Closures ?
<p align="justify">
A closure is a function that can remembers and also allow to access its own scope, as well as the scope of its outer functions, even when the outer functions has returned.
</p>

__Sample Code__
```
function Wallet(Money) {
    return function() {
        console.log("I have enough " + Money+" in my wallet.");
    };
}

const Money = Wallet("money");
Money(); // "I have enough money in my wallet"
```

__Sample Output__
```
I have enough money in my wallet.
```
<p align="justify">
In the above code, the Wallet function returns a new function that has access to the Money variable, even after the Wallet function has returned. This is an example of a closure.
</p>

>### What is async and await ?
<p align="justify">
In JavaScript async and await concepts are used to handle asynchronous code in a synchronous way. They are used to write asynchronous code that looks and feels like synchronous code.
</p>

__Sample Code__
```
async function getIceCream() {
    let promise = new Promise((resolve) => {
        setTimeout(() => resolve("Here's your ice cream!"), 2000);
    });

    let result = await promise; // Wait for the promise
    console.log(result); // "Here's your ice cream!"
}

getIceCream();
```

__Sample Output__
```
Here's your ice cream!
```
<p align="justify">
In the above code, the getIceCream function is marked as async, and it uses the await keyword to wait for the promise to resolve before logging the result. This makes the code look and feel like synchronous code.
</p>

