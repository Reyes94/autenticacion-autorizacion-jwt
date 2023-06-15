# Desafio Latam: User Authentication and Authorization with JSON Web Token (JWT)

Soft Jobs has initiated the development of a platform that seeks to support the junior developer community. For this purpose, it seeks to create a server for
authentication and authorization of users using JWT.

The server provides the following routes:

- `POST: api/usuarios` : Allows registration of new users 
- `POST: api/login` :  Receives a user's credentials and returns a token generated with JWT. The email address of the registered user is included in the token payload.
- `GET: api/usuarios` : Returns a user's data in case that it is authenticated

<br>


Environment variables
-------
Connects node.js to the PostgreSQL server. To specify which database to connect to, create an `.env` file with the following structure, also available in the `.env.example` file.

To create the database follow the instruction of the `query.sql ` file.

```
.env

PGUSER=postgres 
PGHOST=localhost
PGPASSWORD=
PGDATABASE=softjobs
PGPORT=5432
JWTPASSWORD=
```

<br>

Client Application
-------
The client application that consumes the routes is located in the client folder and its a React application. To use it, inside the client directory, run in the terminal `npm run dev` after the backend is up:

- POST:  Register new user, fill in the fields email address, password, role and language and then click on the button "Register".
- POST: To log in, in the tab of the same name, fill in the email and password fields and then click on the "Login" button.
- GET: After logging in, you will be automatically redirected to the "My Profile" tab, and you will be able to see the user's data.


<br>

Using [Thunder Client for VS Code](https://www.thunderclient.com/) or [Postman](https://www.postman.com/) as a client application
-------
<br>

To register an user:
```html
METHOD: POST 
ENDPOINT: localhost:3000/api/usuarios/
```

Rol:
- Full Stack Developer
- Frontend Developer
- Backend Developer

Lenguage:
- JavaScript
- Phyton
- Ruby

```json
BODY JSON

{
    "email": "",
    "password": "",
    "rol": "",
    "lenguage": ""
}
```
<br>

To login:

```html
METHOD: POST
ENDPOINT: localhost:3000/api/login/
```
```json
BODY JSON

{
    "email": "",
    "password": ""
}
```
<br>

To get user data:

```
METHOD: GET
ENDPOINT: localhost:3000/api/usuarios
AUTHORIZATION: Type Bearer Token
```
<br>


Database
-------
- [PostgreSQL](https://www.postgresql.org/)


Backend
-------

- [Node.js](https://nodejs.dev/)


Dependencies
-------
CLIENT:

- This proyect is a [react application](https://react.dev/) 
- [Axios](https://axios-http.com/) : A promise-based HTTP Client for node.js and the browser 
- To install dependencies run: `npm install` inside the `client` folder
- To run de app: `npm start`

SERVER:

- Framework [Express](https://expressjs.com/es/)
- [CORS](https://expressjs.com/en/resources/middleware/cors.html) : For providing a Connect/Express middleware that can be used to enable CORS with various options 
- [node-postgres: pg](https://node-postgres.com/) : Collection of node.js modules to interact with PostgreSQL database 
- Environment variables [dotenv](https://www.npmjs.com/package/dotenv)
- [JSON Web Token (JWT)](https://jwt.io/) is an open standard (RFC 7519) that defines a compact and self-contained way for securely transmitting information between parties as a JSON object
- [bcrypt.js](https://www.npmjs.com/package/bcryptjs): To hash and salt passwords securely
- To install dependencies run: `npm install` inside the `server` folder
- devDependencies [Nodemon](https://www.npmjs.com/package/nodemon) for run server and automatically restarting the node application when file changes, in the terminal run: `npm run dev`

<br>

**Important: Run first the backend and then run the client application**


