
# MongoDB Comparison Operators

MongoDB provides a range of comparison operators for querying documents in a collection. These operators allow for filtering documents based on various criteria.

## List of Comparison Operators

1. **$eq**: Matches values that are equal to a specified value.
   ```
   { field: { $eq: value } }
   ```

2. **$ne**: Matches all values that are not equal to a specified value.
   ```
   { field: { $ne: value } }
   ```

3. **$gt**: Matches values that are greater than a specified value.
   ```
   { field: { $gt: value } }
   ```

4. **$gte**: Matches values that are greater than or equal to a specified value.
   ```
   { field: { $gte: value } }
   ```

5. **$lt**: Matches values that are less than a specified value.
   ```
   { field: { $lt: value } }
   ```

6. **$lte**: Matches values that are less than or equal to a specified value.
   ```
   { field: { $lte: value } }
   ```

7. **$in**: Matches any of the values specified in an array.
   ```
   { field: { $in: [value1, value2, ...] } }
   ```

8. **$nin**: Matches none of the values specified in an array.
   ```
   { field: { $nin: [value1, value2, ...] } }
   ```

## Conclusion

MongoDB's comparison operators are essential for querying documents based on various conditions. They provide flexibility and power to filter and retrieve data efficiently from a collection.
