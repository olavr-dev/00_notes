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
