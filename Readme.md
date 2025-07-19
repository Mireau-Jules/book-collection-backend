Book Collection API (Backend)
Overview
JSON-server backend for the Book Collection App. Provides RESTful API endpoints for managing book data.

Frontend Repository: Mireau-Jules/book-collection-app

Features
REST API endpoints for books

Persistent data storage in db.json

Supports all CRUD operations

Simple setup and configuration

Installation
Clone this repository:

bash
git clone https://github.com/Mireau-Jules/book-collection-backend
cd book-collection-backend
Install dependencies:

bash
npm install
Running the Server
Start the JSON-server:

bash
npx json-server --watch db.json --port 3001
The API will be available at:

http://localhost:3001/books

API Endpoints
Method	Endpoint	Description
GET	/books	Get all books
GET	/books/:id	Get single book
POST	/books	Add new book
PUT	/books/:id	Update existing book
PATCH	/books/:id	Partially update book
DELETE	/books/:id	Delete book
Data Structure
Example book object:

json
{
  "id": 1,
  "title": "Sample Book",
  "author": "Author Name",
  "category": "Fiction",
  "cover": "http://example.com/cover.jpg"
}
Connecting to Frontend
Ensure the frontend is configured to use:

env
VITE_API_URL=http://localhost:3001
Run both servers simultaneously:

Backend: http://localhost:3001

Frontend: http://localhost:5173

Custom Routes (Optional)
Create routes.json for custom routes:

json
{
  "/api/*": "/$1"
}
Then run with:

bash
npx json-server --watch db.json --routes routes.json
Deployment Options
Render (Recommended):

Create new Web Service

Connect your repository

Set build command: npm install

Set start command: npx json-server db.json

Vercel:

Requires custom server configuration

Use server.js with Express wrapper

Troubleshooting
Common Issues:

Port conflicts: Change port with --port 3002

CORS errors: Enable CORS with --middlewares ./enable-cors.js

Data not saving: Ensure write permissions for db.json

License
MIT License