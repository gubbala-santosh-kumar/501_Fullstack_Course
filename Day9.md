>### Sequelizing mode and manipulating data
In this section, we will discuss how to manipulate data in sequelizing mode.

To define the model we need to use the below things to represent the what type of the data.

- `DataTypes.STRING` for VARCHAR(250)
- `DataTypes.INTEGER` for Integer
- `DataTypes.DECIMAL` for DECIMAL(10,2)
- `DataTypes.DATE` for DATE
- `DataTypes.TIME` for TIME
- `DataTypes.BOOLEAN` for Boolean
- `DataTypes.DATE` for Date with timestamp
- `DataTypes.DATEONLY` for Date without timestamp
Like this there are many types are there 

#### Creating the Sequelize model

Sample __TodoModel.js__
```
const { DataTypes } = require("sequelize");
const { sequelize } = require("./connectDB.js");

const Todo = sequelize.define(
  "Todo",
  {
    title: {
      type: DataTypes.STRING,
      allowNull: false,
    },
    dueDate: {
      type: DataTypes.DATEONLY,
    },
    complete: {
      type: DataTypes.BOOLEAN,
    },
  },
  {
    tableName: "todos", 
  }
);

module.exports = Todo;

Todo.sync();
```

__Manipulating Data__

**Insert.js**
```
const Todo = require("./TodoModel.js");

async function insertTodo() {
  try {
    const todo = await Todo.create({
      title: "Complete the project documentation",
      dueDate: "2025-01-15",
      complete: false,
    });
    console.log("Todo inserted:", todo.toJSON());
  } catch (error) {
    console.error("Error inserting todo:", error);
  }
}

module.exports = insertTodo;

```

**Select.js**
```
const Todo = require("./TodoModel.js");

async function selectTodos() {
  try {
    const todos = await Todo.findAll();
    console.log("All Todos:", todos.map((todo) => todo.toJSON()));
  } catch (error) {
    console.error("Error selecting todos:", error);
  }
}

async function selectTodoById(id) {
  try {
    const todo = await Todo.findByPk(id);
    if (todo) {
      console.log("Todo found:", todo.toJSON());
    } else {
      console.log("Todo not found.");
    }
  } catch (error) {
    console.error("Error selecting todo by ID:", error);
  }
}

module.exports = { selectTodos, selectTodoById };

```

**Update.js**
```
const Todo = require("./TodoModel.js");

async function updateTodo(id, updates) {
  try {
    const todo = await Todo.findByPk(id);
    if (todo) {
      await todo.update(updates);
      console.log("Todo updated:", todo.toJSON());
    } else {
      console.log("Todo not found for updating.");
    }
  } catch (error) {
    console.error("Error updating todo:", error);
  }
}

module.exports = updateTodo;
```
**Delete.js**
```
const Todo = require("./TodoModel.js");

async function deleteTodo(id) {
  try {
    const todo = await Todo.findByPk(id);
    if (todo) {
      await todo.destroy();
      console.log("Todo deleted successfully.");
    } else {
      console.log("Todo not found for deletion.");
    }
  } catch (error) {
    console.error("Error deleting todo:", error);
  }
}

module.exports = deleteTodo;
```

**Example usage of all the operations are**

__Insert Data__
```
const insertTodo = require("./Insert");

const newTodo = {
  title: "Prepare for the meeting",
  dueDate: "2025-01-20",
  complete: false,
};

insertTodo(newTodo);
```

__Select Data__
```
const { selectTodos, selectTodoById } = require("./Select");
selectTodos();
selectTodoById(1);
```
__Update Data__
```
const updateTodo = require("./Update");
updateTodo(1, { complete: true });
```

__Delete Data__

```
const deleteTodo = require("./Delete");
deleteTodo(1);
```

All these sample example codes for that to manipulating the data.

