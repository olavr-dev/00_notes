# MongoDB - NoSQL Database

MongoDB uses collections (tables) and documents (entries).

## Starting MongoDB

- Windows Services > Start MongoDB
- Terminal: `mongosh`

### Show databases

`show dbs`

### Setting up a server

`use name-of-server` server will be created automatically.

### Inserting data (document) into the collection (restaurants)

`db.restaurants.insertOne({ name: "Jonas B Jærhagen", address: { street: "Jærveien", streetNumber: "1902" } })`

#### Another Example

`db.restaurants.insertOne({ name: "McDonalds Mariero", address: { street: "Hetlandsgata", streetNumber: "13", postalCode: 4006, city: "Stavanger", country: "Norway" }, type: { typeId: ObjectId("661a4d28139820189b16c9ba"), name: "American" } })`

```yaml
{
  _id: ObjectId('661a4fe8139820189b16c9be'),
  name: 'McDonalds Mariero',
  address: { street: 'Hetlandsgata', streetNumber: '13', postalCode: 4006, city: 'Stavanger', country: 'Norway' },
  type: { typeId: ObjectId('661a4d28139820189b16c9ba'), name: 'American' },
}
```

### Filtering

`db.restaurants.find()` Lists all documents in the collection.

`db.restaurants.find({ name: "Jonas B Jærhagen"})` More specific filter

#### 1 is include - 0 is exclude from filtering

`db.restaurants.find({}, {name: 1})` Filters for name and id only

`db.restaurants.find({}, {name: 1, _id: 0})` Filters for name only ===

### Updating documents

`db.restaurants.updateOne({ _id: ObjectID("66197c47139820189b16c9b5") }, { $set: { "address.street": "Some Street" } })`

### Deleting documents

`db.restaurants.deleteOne({ _id: ObjectID("66197c47139820189b16c9b5") })`

#### Deleting all documents

`db.restaurants.deleteMany({})`
