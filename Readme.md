# Activity

## Mock API Data Manipulation

Objective: Practice creating and handling HTTP requests (GET, POST, PUT, DELETE) with mock data, retrieving an item by its specific id, and using dotenv and nodemon for server configuration and auto-reloading.

## Instructions:

Instructions:
Setup Project Folder:

1. Create a folder named using your surname (e.g., `Dela_Cruz_Activity`).
   Inside this folder, initialize a new Node.js project:

```bash
npm init -y
```

- if your encountering error with `npm`:

```bash
Set-ExecutionPolicy RemoteSigned -Scope Process
```

2. Install Dependencies:

```bash
npm i express nodemon dotenv
```

3. Configure Scripts in package.json:

Update the `package.json` file to use `nodemon` for starting the server in development mode:

```bash
 "dev": "nodemon server.js"
```

4. Create Project Files:

- Create an `.env` file in the project folder to store environment variables, such as the server port:

```bash
PORT=3000
```

- Add .gitignore:

  Create a `.gitignore` file in your project folder and add the following lines to ensure that `.env` and `node_modules` are not tracked by `Git`:

```Bash
node_modules/
.env
```

5. Implement the API Endpoints:

- GET `/items`: Fetch and display all items in mockData.
- GET `/items/:id`: Retrieve a specific item by `id` from mockData. If the item doesn’t exist, return a `404` status and an error message.
- POST `/items`: Add a new item to `mockData` (send the item’s details in the request body).
- PUT `/items/:id`: Update an existing item in `mockData` based on the given `id`.
- DELETE `/items/:id`: Remove an item from `mockData` by `id`.

6. Run the Server:

In your main server file (e.g., server.js), load environment variables from `.env` using dotenv:

```javascript
const express = require("express");
const app = express();
require("dotenv").config();

app.use(express.json());

app.listen(process.env.PORT, () => {
  console.log(`Server is running on port ${process.env.PORT}`);
});
```

- To start the server with `nodemon`, use the following command:

```bash
npm run dev
```

- local enviroment

```bash
http://localhost:3000
```

7. Example Mock Data:

Set up mockData as an array of objects:

```javascipt
const mockData = [
  { id: 1, name: "Product A", price: 10 },
  { id: 2, name: "Product B", price: 20 },
  { id: 3, name: "Product C", price: 30 },
];
```

## Bonus Challenge:

Implement `error handling` for cases where an item with a specific `id` is not found.
Test all endpoints using `Postman`.

## Deliverables:

- Project folder named with your `surname`.
- .`gitignore` file including .`env` and `node_modules`.
- .`env` file with the `PORT` variable.
- `package.json` with the `"dev": "nodemon index.js"` script.
