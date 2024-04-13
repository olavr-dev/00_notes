# MongoDB - NoSQL Database

## Starting MongoDB

- Windows Services > Start MongoDB
- Terminal: `mongosh`

### Show databases

`show dbs`

### Setting up a server

`use name-of-server` server will be created automatically.

### Inserting data (document) into the collection (restaurants)

`db.restaurants.insertOne({ name: "Jonas B Jærhagen", address: { street: "Jærveien", streetNumber: "1902"}}) })`

### Filtering

`db.restaurants.find()` Lists all documents in the collection.

`db.restaurants.find({ name: "Jonas B Jærhagen"})` More specific filter

#### 1 is include - 0 is exclude from filtering

`db.restaurants.find({}, {name: 1})` Filters for name and id only

`db.restaurants.find({}, {name: 1, _id: 0})` Filters for name only
