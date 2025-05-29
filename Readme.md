chai aur backend series to build a professional backend project with javascript

- [Model Link ](https://app.eraser.io/workspace/YtPqZ1VogxGy1jzIDkzj)

-to store images and files we will use cloudinary,aws,azure, or any other cloud storage service
-so firstly we upload the photos temporarily to the local storage or server and then we upload them to the cloud storage service
-why because say we a user lose connection to the internet while uploading the file, we can still save the file locally and then upload it later
-when we upload the file to the cloud storage service, we will get a url for that file, and we will store that url in our database

//whatever files related to node js we will put in gitignore file
//any other files that you don't want to push to the git repository, you can put them in the gitignore file

//in js we import files either using module or common js
//in common js we use require and in module we use import

//Explanation of "dev": "nodemon src/index.js"
This line is typically part of the scripts section in a project's package.json file.

It defines a shortcut to run the nodemon tool to execute the file src/index.js during development.

Example in package.json:
{
"scripts": {
"dev": "nodemon src/index.js"
}
}

//What is nodemon?
nodemon is a development utility for Node.js that automatically restarts the application when it detects changes in the source files. It improves developer productivity by removing the need to manually restart the Node.js server.

How to Use nodemon
Install nodemon as a dev dependency:

npm install nodemon --save-dev
Run the script:

npm run dev
Behavior:

The server (src/index.js) will start.

When you make changes to any file in the project, nodemon will detect it and restart the server automatically.

//Benefits of nodemon
Automatic Restart: Restarts the server on file changes.

Efficiency: No need for manual restarts during development.

Customization: Supports configuration for watching specific file types or directories.

---//When you run the command "dev": "nodemon src/index.js" using npm run dev, here's what happens with index.js:

-Start the Application:

nodemon starts the Node.js application by running the src/index.js file.

This file typically contains your server setup (e.g., Express app initialization).

Watch for Changes:

nodemon continuously monitors all files in your project directory (by default) for changes.

If you modify and save any file (e.g., index.js, routes.js, or a .env file), nodemon detects the change.

Restart the Application:

When a change is detected, nodemon stops the current application process and restarts it with the updated code.

You don't need to manually stop and restart your application.

Why Use It with index.js?
The index.js file is often the entry point for a Node.js app. It might:

Initialize an Express server.

Connect to a database.

Define API routes.

Using nodemon ensures that any changes you make to this file (or related files) are immediately reflected in the running app without manual intervention.

//Folder Structure added in Src and their usecases  
/src
/controllers
-Purpose: Contains the logic for handling requests and responses.
Usage:
-Controllers process incoming HTTP requests, perform necessary operations (e.g., call services/models), and send responses back to the client.
-Each controller corresponds to a specific module or feature (e.g., userController.js, productController.js).

/models
-Purpose: Defines data models and schemas for the application.
-Usage:
Represents the structure of data in the database.
Typically uses libraries like Mongoose (MongoDB) or Sequelize (SQL databases).

/routes-
-Purpose: Manages the routing of HTTP requests to the appropriate controller.-Usage:
Contains route definitions for API endpoints (e.g., /users, /products).
Often modularized into files for each feature (e.g., userRoutes.js, productRoutes.js).

/middlewares-
-Purpose: Contains middleware functions to handle request preprocessing.
-Usage:
Middleware is executed before controllers handle requests.
Examples include authentication, logging, input validation, and error handling.

/utils
-Purpose: Contains reusable utility functions or helper modules.
-Usage:
Functions for formatting, logging, email sending, or other generic tasks.
Typically independent of specific features.
