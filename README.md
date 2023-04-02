# Getting Started with Create React App

This is a Note keeping web application designed in MERN stack.

## Available Scripts

In the project, you can run the client using below command:

### `npm run client`
This will run the client on port 3003 as mapped in package.json, can be changed from there.
The URL: "http://localhost:3003"

User will firstly redirect to the authentication page having URL: "http://localhost:3003/auth"
After successful login it will redirect the user to the dashboard which has all features (create note, update note, delete note)
implemented.
In client side app state management is implemented using react-redux, all the relevant data gets stored in redux-store 
(browser local storage) for session management. So that once the user gets logged-in it could redirect to dashboard always 
even on hitting "http://localhost:3003/auth". The user data gets stored in local storage until it gets logout or the session
gets expired. Routing is implemented using react-router-dom.
All the api calls are getting triggered from /api directory having routes of Notes & Auth (notes.js, auth.js). All the request/response are getting intercepted inside /api/index.js to check for passing auth-token & seeing if the response says that session-is-expired/unauthorized-access
In the project, you can run the server using below command:

### `npm run server`
The server run command is also written in the package.json below client run command. The server is running using 
nodemon so that incase of any changes it gets to restart again itself.
By default I have mapped the PORT for server in .env. Anyone can change it based on requirements
The server has the implemented controllers for Users, Notes & session. All the routes and the their respective
controllers are working fine with the base_url e.g ("http://localhost:3005") mapped on client side. When server is running
on port 3005.
Session management is implemented also Unauthorized access is getting checked using jwt tokens against each login.
Each request comes with an authentication token which gets verified before going on.


# Deployment [CLIENT]
### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.
I placed this build folder on netlify and the it got deployed against this
URL: "https://notetakingapplication2.netlify.app/auth"

# Deployment [SERVER]

For deploying the server, I push the server folders only on a separate git repository including the package.json file,
had put a command "start": "node server.js" inside scripts object in package.json. 
I deployed the backend on render.com, passed the build command "npm install" & run command "npm start"
