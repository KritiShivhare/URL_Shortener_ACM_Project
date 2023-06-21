# URL_Shortener_ACM_Project
>## Open Projects 2023
## Abstract
The URL shortener web project is a Node.js application using Express and MongoDB. It shortens long URLs, stores them in a database, and provides shortened URLs that redirect to the original ones. Users can search for URLs based on notes and create/update short URLs. The project has a clean interface, utilizes dotenv for environment variables, and enhances the user experience with static assets. It simplifies URL sharing and management.

## Tech Stack
- Node.js
- Express
- MongoDB
- EJS
- Render.com
- GitHub
  
## Getting started
### Prerequisites 
- Node.js installed on your machine.
- MongoDB Atlas account (or a local MongoDB instance) for database storage.
- Basic knowledge of Express.js and Mongoose.


### Steps 

**1. Clone the repository:**

- Clone the project repository or download the project as a zip file and extract it on your local machine.

**2. Install dependencies:**

- Open the command prompt and navigate to project’s root directory.
- Run the following command to install the required depecndecies:
 `npm install`
- Dependencies:
`dotenv: ^16.3.1`
`ejs: ^3.1.9`
`express: ^4.18.2`
`mongoose: ^5.13.17`
`shortid: ^2.2.15`
`nodemon: ^2.0.22`

**3. Set up MongoDB Database:**
- Create a MongoDB Atlas account or use an existing one.
- Log in to your MongoDB Atlas account and create a new project.
- Within the project, create a new cluster or use an existing one.
- In the cluster, navigate to the "Database Access" section and create a new database user with appropriate privileges. Take note of the username and password for this user.
- Next, navigate to the "Network Access" section and click on the "Add IP Address" button to allow access from your current IP address. Optionally, you can configure more secure network access settings based on your requirements.
- Next, navigate to the "Database Clusters" tab and click on the "Connect" button for your cluster.
- Choose "Connect your application" and select the driver and version (e.g., Node.js and the latest version).
- Copy the connection string provided.

**4. Set Up Search Index:**
- Open the MongoDB Atlas dashboard and navigate to your cluster.
- Click on the "Collections" tab and select the database associated with your connection string.
- Create a new collection named 'shorturls' by clicking the "Create Collection" button.
- In the created 'shorturls' collection, click on the "Search" tab.
- Create a new search index and save it. Keep note of the index name.
- In the project's root directory, create a new file named ‘.env’.
- Inside the ‘.env’ file, add the following variables:

  `URL=<mongodb-connection-string>`
  
  `SearchIndex=<search-index-name>`
  
**5. Start the application:**

   `npm run devStart`
 - Open your web browser and visit http://localhost:5000 to access the URL shortener application.

## Usage

- Enter a long URL in the input field and click the "Drop" button to generate a short URL.
- You can optionally add some notes to the URL before shortening it.
- The shortened URLs will be displayed on the main page along with their corresponding full URLs and notes.
- To search for URLs based on notes, enter a search query in the search bar and click the "Search" button.
- You can search the url through your long url, short url or notes. Matching URLs will be displayed.
- To copy a URL, click the “Copy” icon on the shortened URL that you want to copy.
- To delete a URL, click the "Delete" button next to the URL you want to remove.

## Implementation

The URL shortener application follows the following internal working:

### Importing dependencies and setting up the Express application:
- The express module is used to create the Express application.
- The mongoose module is used to connect to the MongoDB database.
- The ShortUrl model is imported from the shortUrl.js file.
- The dotenv module is used to load environment variables from a .env file.
- The Express application is created and configured.

### Connecting to the MongoDB database: 
- The mongoose.connect() method is used to establish a connection to the MongoDB database.
- The MongoDB connection string is read from the process.env.URL environment variable.

### Configuring the application:
- The view engine is set to ejs, which allows rendering dynamic HTML templates.
- URL-encoded data is parsed using express.urlencoded() middleware.

### Handling routes:
- The root route ('/') fetches all the shortened URLs from the database using ShortUrl.find() and renders the index template with the fetched data.
- The **'/shortUrls'** route handles the creation of short URLs. It checks if a given full URL already exists in the database using ShortUrl. findOne(). If it doesn't exist, a new document is created using ShortUrl.create(). If it already exists, display the URL at the top,
- The **'/search'** route handles the search functionality. It uses full text mongo Atlas search for URLs. 
- The **'/deleteUrl'** route handles the deletion of URLs. It deletes the document with a specific short URL using ShortUrl.deleteOne().
- The **'/shortUrl'** route handles the redirection of a short URL to its corresponding full URL. It finds the document with the given short URL using ShortUrl.findOne() and redirects the user to the full URL.

### Hosting the website:
  Deployed the project on render.com.
  Here's the link:

https://url-shortener-acm-project-kritishivhare.onrender.com/

 ## Key take-aways:
- Building a URL shortener using Express.js and MongoDB.
- Storing shortened URLs in a MongoDB database.
- Implementing routes for creating, searching, and deleting URLs.
- Using MongoDB's text search capabilities for searching URLs based on notes.
-	Using ATLAS search for full text search in database.
-	Managing environment variables with dotenv.
-	Handling form submissions and parsing form data.
-	Rendering dynamic views with EJS templates.
-	Gaining practical experience in web development, database integration, and error handling.

  ## Refrences ##
  - https://www.youtube.com/watch?v=SLpUKAGnm-g&t=1098s

  









  





