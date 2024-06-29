
# MongoDB Logical Operators

MongoDB provides several logical operators that allow you to combine multiple query conditions. These operators are used to form complex queries by combining simpler queries with logical relationships.

## List of Logical Operators

1. **$and**: Joins query clauses with a logical AND returns all documents that match the conditions of both clauses.
   ```
   { $and: [ { condition1 }, { condition2 }, ... ] }
   ```

2. **$or**: Joins query clauses with a logical OR returns all documents that match the conditions of at least one of the clauses.
   ```
   { $or: [ { condition1 }, { condition2 }, ... ] }
   ```

3. **$not**: Inverts the effect of a query expression and returns documents that do not match the condition.
   ```
   { field: { $not: { <operator>: value } } }
   ```

4. **$nor**: Joins query clauses with a logical NOR returns all documents that fail to match both conditions.
   ```
   { $nor: [ { condition1 }, { condition2 }, ... ] }
   ```

5. **$expr**: Allows the use of aggregation expressions within the query language.
   ```
   { $expr: { <expression> } }
   ```

## Examples

### $and Example
Find documents where the age is greater than 25 and the status is "A".
```
db.collection.find({ $and: [ { age: { $gt: 25 } }, { status: "A" } ] })
```

### $or Example
Find documents where the age is less than 25 or the status is "A".
```
db.collection.find({ $or: [ { age: { $lt: 25 } }, { status: "A" } ] })
```

### $not Example
Find documents where the age is not greater than 25.
```
db.collection.find({ age: { $not: { $gt: 25 } } })
```

### $nor Example
Find documents where neither the age is greater than 25 nor the status is "A".
```
db.collection.find({ $nor: [ { age: { $gt: 25 } }, { status: "A" } ] })
```

### $expr Example
Find documents where the value of field `a` is greater than the value of field `b`.
```
db.collection.find({ $expr: { $gt: ["$a", "$b"] } })
```

## Conclusion

MongoDB's logical operators are powerful tools for building complex queries by combining multiple conditions. Understanding and using these operators effectively allows for flexible and efficient querying of documents in a MongoDB collection.
