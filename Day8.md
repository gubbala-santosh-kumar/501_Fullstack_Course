### What is Sequelize ?
<p align="justify">
Sequelize is a Node.js library that helps us to interact with the databases in an easier and more organized way. Instead of writing the complex SQL queries, we can use the JavaScript code to manage our database.
</p>

### What is Sequelize ORM ?
<p align="justify">
Sequelize ORM stands for Object Relational Mapping. It is a library that helps us to interact with the database using JavaScript objects. It provides a simple and easy way to interact with the database.
</p>

### Connect to Database

Before writing the code we need to install the sequelize, pg pg-hstore packages. 

Command : `npm install sequelize pg pg-hstore`.

__connectDB.js__
```
const Sequelize = require("sequelize");
const database = "todo_db";
const username = "postgres";
const sequelize = new Sequelize(
    database,
    username,
    password,
    {
        host: "localhost",
        dialect: "postgres", 
    }
);

sequelize
    .authenticate()
    .then(()=>{
        console.log("Connection has been established successfully.");
    })
    .catch((error)=>{
        console.log("Unable to connect to the database : ",error);
    });