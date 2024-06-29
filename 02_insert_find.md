# CRUD Operation

## Insert Operation

```
db.<collection-name>.insertOne({
    field1: value1,
    field2: value2,
    ...
});
```

```
db.<collection-name>.insertMany([
    { field1: value1, field2: value2, ...},
    { field1: value1, field2: value2, ...},
    ....
]);
```

### Orderd and Unorderd Insert

> Optional. If true, perform an ordered insert of the documents in the array, and if an error occurs with one of documents, MongoDB will return without processing the remaining documents in the array.

> Default is true.

> If false, perform an unordered insert, and if an error occurs with one of documents, continue processing the remaining documents in the array.

```
db.<collection-name>.insertMany([doc1, doc2, ....], {orderd: false})
```

---

## Select Operation

```
db.<collection-name>.find()
```

```
db.<collection-name>.find({key:value})
```

```
db.<collection-name>.findOne()
```
```
db.<collection-name>.findOne({key:value})
```




## Import JSON Data in MongoDB (command-line utilities) [NB: MongoDB Database Tools should be install for this command]

> mongoimport < json-file-path > -d database_name -c collection_name

#### For JSON Array

> mongoimport jsonfile.json -d database_name -c collection_name --jsonArray

## Export JSON Data in MongoDb (command-line utilities)

> mongoexport -d database_name -c collection_name -o < output-file-location >