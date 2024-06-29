MongoDB is a NoSQL database that uses a flexible, document-oriented data model. It stores data in JSON-like documents with dynamic schemas, making it easier to model and manipulate data. Here are some key reasons why MongoDB is used:

1. **Scalability**: MongoDB can handle large volumes of data and traffic by scaling out horizontally through sharding.
2. **Flexibility**: Its schema-less nature allows for easy changes to data structure without requiring a complex migration process.
3. **Performance**: MongoDB provides high performance for read and write operations due to its efficient indexing and in-memory storage engine.
4. **Ease of Use**: The document-oriented approach aligns well with how developers think in objects, making it intuitive to use and integrate with various programming languages.
5. **Rich Query Language**: MongoDB supports a powerful, flexible query language that allows for complex queries and aggregations.

These features make MongoDB a popular choice for modern applications that require agility, scalability, and high performance.

---

# Managing Databases and Collections

```
show dbs;
```

### Create Database 

```
use <database-name>
```

### Drop Database

```
db.dropDatabse();
```

---

```
show collections;
```

### Create Collection

```
db.createCollection('<collection-name>');
```

### Drop Collection
```
db.<collection-name>.drop();
```


