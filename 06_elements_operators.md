
# MongoDB Element Operators

MongoDB provides element operators that allow you to query documents based on the existence or type of fields within the documents. These operators are useful for checking whether fields exist, are of a specific type, or satisfy certain conditions related to arrays.

## List of Element Operators

1. **$exists**: Matches documents that have the specified field.
   ```
   { field: { $exists: <boolean> } }
   ```

2. **$type**: Matches documents where the value of a field is of the specified BSON type.
   ```
   { field: { $type: <BSON type> } }
   ```

3. **$regex**: Provides regular expression capabilities for pattern matching within strings.
   ```
   { field: { $regex: /pattern/, $options: '<options>' } }
   ```

4. **$mod**: Performs a modulo operation on the value of a field and selects documents with a specified result.
   ```
   { field: { $mod: [ divisor, remainder ] } }
   ```

5. **$size**: Matches arrays that contain a specific number of elements.
   ```
   { field: { $size: <number> } }
   ```

6. **$elemMatch**: Matches documents that contain an array field with at least one element that matches all the specified query criteria.
   ```
   { arrayField: { $elemMatch: { criteria1, criteria2, ... } } }
   ```

## Examples

### $exists Example
Find documents where the field `age` exists.
```
db.collection.find({ age: { $exists: true } })
```

### $type Example
Find documents where the field `address` is of type string.
```
db.collection.find({ address: { $type: "string" } })
```

### $regex Example
Find documents where the field `name` matches a regular expression pattern.
```
db.collection.find({ name: { $regex: /^Joh/, $options: 'i' } })
```

### $mod Example
Find documents where the field `count` modulo 10 equals 1.
```
db.collection.find({ count: { $mod: [10, 1] } })
```

### $size Example
Find documents where the array field `tags` contains exactly 3 elements.
```
db.collection.find({ tags: { $size: 3 } })
```

### $elemMatch Example
Find documents where the array field `scores` contains at least one element that is greater than 80 and less than 90.
```
db.collection.find({ scores: { $elemMatch: { $gt: 80, $lt: 90 } } })
```

## BSON Types Reference
Here are some common BSON types used with the $type operator:

- Double: "double" or 1
- String: "string" or 2
- Object: "object" or 3
- Array: "array" or 4
- Binary Data: "binData" or 5
- Undefined: "undefined" or 6
- ObjectId: "objectId" or 7
- Boolean: "bool" or 8
- Date: "date" or 9
- Null: "null" or 10
- Regular Expression: "regex" or 11
- Int32: "int" or 16
- Timestamp: "timestamp" or 17
- Int64: "long" or 18
- Decimal128: "decimal" or 19