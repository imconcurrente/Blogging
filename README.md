# Blogging

### Brief Overview:
Blogging is a web-based blogging platform that allows users to create, edit, and manage blog posts seamlessly. It features a simple and intuitive user interface, robust backend API, and efficient handling of CRUD (Create, Read, Update, Delete) operations. The project is built using modern technologies like Express.js, EJS templating, and Axios for HTTP requests, providing a solid foundation for further development and enhancements.


## Features

- Create, Read, Update, and Delete blog posts
- RESTful API for backend operations
- EJS templating for dynamic frontend rendering
- Axios for efficient HTTP communication between frontend and backend
- Clean, responsive UI with basic CSS styling


### Implementation Details:

#### 1. **Backend API (Port 4000):**
   - **Technologies:** Node.js, Express.js, Body-Parser
   - **Functionality:** Provides RESTful API endpoints for managing blog posts.
   - **Endpoints:**
     - `GET /blogPosts`: Fetches all blog posts.
     - `GET /blogPosts/:id`: Fetches a specific blog post by ID.
     - `POST /blogPosts`: Creates a new blog post.
     - `PATCH /blogPosts/:id`: Updates a specific blog post by ID.
     - `DELETE /blogPosts/:id`: Deletes a specific blog post by ID.
   - **Data Storage:** Uses an in-memory array (`blogPosts`) for storing blog data.
   
   **Sample Code:**
   ```javascript
   import express from 'express';
   import bodyParser from 'body-parser';

   const app = express();
   const port = 4000;

   app.use(bodyParser.urlencoded({ extended: true }));
   app.use(bodyParser.json());

   let blogPosts = [
       { id: 1, title: "The Rise of Decentralized Finance", content: "DeFi content...", author: "Alex Thompson", date: new Date() },
       { id: 2, title: "The Impact of AI on Businesses", content: "AI content...", author: "Mia Williams", date: new Date() },
       { id: 3, title: "Sustainable Living Tips", content: "Sustainability content...", author: "Samuel Green", date: new Date() }
   ];

   // Endpoint handlers here...

   app.listen(port, () => {
       console.log(`API server is running on port ${port}`)
   });
   ```

#### 2. **Frontend Web Server (Port 3000):**
   - **Technologies:** Express.js, EJS (Embedded JavaScript templating), Axios
   - **Functionality:** Renders web pages and interacts with the backend API.
   - **Pages:**
     - **Home Page (`/`):** Lists all blog posts with options to view, edit, or delete each post.
     - **New Post Page (`/new`):** Form for creating a new blog post.
     - **Edit Post Page (`/edit/:id`):** Form for editing an existing blog post.

   **Sample Code:**
   ```javascript
   import express from 'express';
   import axios from 'axios';
   import bodyParser from 'body-parser';
   import ejs from 'ejs';

   const app = express();
   const port = 3000;
   const APIurl = 'http://localhost:4000/blogPosts';

   app.set('view engine', 'ejs');
   app.use(express.static('public'));
   app.use(bodyParser.urlencoded({ extended: true }));
   app.use(bodyParser.json());

   // Route handlers here...

   app.listen(port, () => {
       console.log(`Backend server is running on port ${port}`)
   });
   ```

### Running the Project:
1. **Setup:**
   - Initialize the project and install dependencies:
     ```bash
     npm init
     npm install express ejs body-parser axios
     ```

2. **Starting the Servers:**
   - Start the API server (Port 4000):
     ```bash
     node apiServer.js
     ```
   - Start the web server (Port 3000):
     ```bash
     node webServer.js
     ```

3. **Accessing the Application:**
   - Open a web browser and navigate to `http://localhost:3000` to interact with blogger.
  

Blogger is a lightweight and modular blogging platform designed for simplicity and extensibility. It demonstrates a full-stack JavaScript application using Express.js, EJS, and Axios, showcasing key concepts like RESTful APIs, server-side rendering, and client-server interaction. Whether you're learning backend development, templating with EJS, or integrating frontend and backend logic, Blogger provides a clear and practical foundation for building more advanced web applications.
