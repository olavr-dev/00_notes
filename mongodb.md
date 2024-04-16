# MongoDB - NoSQL Database

MongoDB uses collections (_"tables"_) and documents (_entries_).

## Setting up a MongoDB database from scratch

Using the blog course exercise from the 100 days of code bootcamp as an example.

- [ ] Make sure MongoDB is running on windows:
  - [ ] Go to Windows Services
  - [x] Start MongoDB

Start MongoDB in the terminal => `mongosh`

### Show databases

To view all databases running on the server: `show dbs`

### Creating a new database

The database will be created automatically when you start adding to it.

`use name-of-database`

### Inserting data (_document_) into the collection (_restaurants_)

_You can also use_ `insertMany()`

```js
db.authors.insertOne({ name: 'Olav Øye Rørvik', email: 'olav@test.com' });
```

### View entries in the document

`db.authors.find()` This will list all entries.

### Filtering

`db.authors.find()` Lists all documents in the collection.

`db.authors.find({ name: "Olav Øye Rørvik"})` More specific filter

#### 1 is include - 0 is exclude from filtering

`db.authors.find({}, {name: 1})` Filters for name and id only

`db.authors.find({}, {name: 1, _id: 0})` Filters for name only

### Updating documents

`db.authors.updateOne({ _id: ObjectID("661cc797386772fe5816c9b5") }, { $set: { "name": "Olav Ø Rørvik" } })`

### Deleting documents ===

`db.authors.deleteOne({ _id: ObjectID("661cc797386772fe5816c9b5") })`

#### Deleting all documents

`db.authors.deleteMany({})` Deletes all entries.

## Connecting a NodeJS app to MongoDB

_*data/database.js*_

```javascript
const mongodb = require('mongodb');

const MongoClient = mongodb.MongoClient;

// Database variable created outside of the connect function
// This makes it usable anywhere in this file
let database;

async function connect() {
  const client = await MongoClient.connect('mongodb://localhost:27017');
  database = client.db('blog');
}

function getDb() {
  if (!database) {
    throw { message: 'Database connection not established!' };
  }
  return database;
}

// Make connect() and getDb() functions available to the rest of the project
module.exports = {
  connectToDatabase: connect,
  getDb: getDb,
};
```

**_Note: Using NodeJS 18 and higher may fail using localhost. Use IP instead:_**

```javascript
const client = await MongoClient.connect('mongodb://127.0.0.1:27017');
```

_*app.js*_

```javascript
// Import the database (Start of file)
const db = require('./data/database');
```

```javascript
// Only listen to port 3000 if connected to the database. (End of file)
db.connectToDatabase().then(function () {
  app.listen(3000);
});
```
