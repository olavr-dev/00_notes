# User Authentication & Working with Sessions

Many websites have certain "areas" (pages) that should only be accessible by authenticated users (logged in).

1: `User Sign Up` => 2: `User Login` => 3: `User Authentication`

## Important! - Hashing Passwords

Hashing = converting a string (e.g. the password) to a _**non-decodable**_, different string.

Using a hashing algorithm `my-plain-text-password` becomes `klatrjbw3452anwej321mbn`

_**Securely hashed values can't be transformed, reverted or decoded back into the original value.**_

A popular third-party hashing package is [**bcrypt.js**](https://www.npmjs.com/package/bcryptjs)

### Installing bcrypt.js

`npm install bcryptjs`

#### Import the library

```javascript
const bcrypt = require('bcryptjs');
```

#### Store the hashed password in the database instead of the plain text one

```javascript
router.post('/signup', async function (req, res) {
  const userData = req.body;
  const enteredEmail = userData.email;
  const confirmEmail = userData['confirm-email'];
  const enteredPassword = userData.password;

  const hashedPassword = await bcrypt.hash(enteredPassword, 12);

  const user = {
    email: enteredEmail,
    password: hashedPassword,
  };

  await db.getDb().collection('users').insertOne(user);

  res.redirect('/login');
```

## Sessions & Cookies

We need to track the user auth status. This can be done with an "entry ticket". One part of the ticket is saved on server, and one part is handed out to the visitor.

This way, the user can show their ticket and be granted access.

### Tracking user auth status with "Sessions"

1. `Client` => User sends login credentials to the server
2. `Server` => Server-side code validates credentials and hands it over to the database
3. `Database` => Creates a database document/record and store a unique **Session Id**
4. `Cookie` => A cookie (contains session id) response / request header data is sent to the client
5. `Client` => Stores the cookie locally on the users computer
6. `Client` => On next visit, the client hands the cookie over to the server and is granted access without having to log in again.

#### Sessions are stored on the Server

- Unauthenticated users can also be assigned sessions
- The data stored in a session (e.g. `isAuthenticated: true`) matters

#### Session Cookies are stored client-side

- Does not expire until the user deletes it from their browser
- Cookies can also be used for more annoying things like tracking and advertisements.
- Can be combined with sessions, but don't have to.

### Working with Sessions & Cookies

Typically, you use third-party packages for handling sessions and cookies.

### `express-session`

For sessions using Node.js, Express.js and MongoDB

`npm install express-session`

Install a compatible session store (for mongodb in this case)

`npm install connect-mongodb-session`

```javascript
// import the packages
const session = require('express-session');
const mongodbStore = require('connect-mongodb-session');

// enable the built in constructor class
const MongoDBStore = mongodbStore(session);

// set up the store
const sessionStore = new MongoDBStore({
  uri: 'mongodb://localhost:27017',
  databaseName: 'auth-demo',
  collection: 'sessions',
});

// set up the middleware
app.use(
  session({
    secret: 'super-secret',
    resave: false,
    saveUninitialized: false,
    store: sessionStore,
  })
);
```

**cookie-parser** for cookies using Node.js and Express.js

Other languages have their own packages.
