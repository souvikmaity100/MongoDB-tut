
# MongoDB Cursor Methods in Mongosh

In MongoDB, a cursor is an object that allows you to iterate over the results of a query. When you perform a query using `find()`, it returns a cursor. The `mongosh` shell provides various methods to work with cursors.

## Common Cursor Methods

### 1. `forEach()`
Iterates over each document in the cursor and applies a function to each document.
```javascript
db.collection.find().forEach(doc => printjson(doc))
```

### 2. `map()`
Applies a function to each document and returns an array of the results.
```javascript
let result = db.collection.find().map(doc => doc.fieldName)

printjson(result)
```

### 3. `toArray()`
Returns all documents in the cursor as an array.
```javascript
let docs = db.collection.find().toArray()
```

### 4. `hasNext()`
Returns `true` if the cursor has more documents.
```javascript
let cursor = db.collection.find()
while (cursor.hasNext()) {
  printjson(cursor.next())
}
```

### 5. `next()`
Returns the next document in the cursor.
```javascript
let doc = db.collection.find().next()
printjson(doc)
```

### 6. `count()`
Returns the count of documents in the cursor.
```javascript
let count = db.collection.find().count()
```

### 7. `limit()`
Limits the number of documents returned by the cursor.
```javascript
let limitedDocs = db.collection.find().limit(5).toArray()
```

### 8. `skip()`
Skips a specified number of documents in the cursor.
```javascript
let skippedDocs = db.collection.find().skip(10).toArray()
```

### 9. `sort()`
Sorts the documents in the cursor by the specified fields.
```javascript
let sortedDocs = db.collection.find().sort({ fieldName: 1 }).toArray() // 1 for ascending, -1 for descending
```

### 10. `projection()`
Specifies the fields to include or exclude in the returned documents.
```javascript
let docs = db.collection.find({}, { projection: { fieldName: 1 } }).toArray() // 1 to include, 0 to exclude
```

## Example Usage

### Find all documents and print each
```javascript
db.collection.find().forEach(doc => printjson(doc))
```

### Find documents with a limit and sort
```javascript
let docs = db.collection.find().sort({ age: -1 }).limit(5).toArray()
printjson(docs)
```

### Check if there are more documents and print the next one
```javascript
let cursor = db.collection.find()
if (cursor.hasNext()) {
  let doc = cursor.next()
  printjson(doc)
}
```

## Conclusion

MongoDB cursor methods in `mongosh` provide powerful ways to handle and manipulate query results. These methods allow for efficient iteration, transformation, and retrieval of data from collections.
