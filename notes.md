## Introduction
🗃️ 1. Database
A MongoDB database is a container for collections. It’s similar to a schema or database in SQL systems.<br/>
- You can have multiple databases.
- Each database is independent and stores its own collections and indexes.

📂 2. Collection
A collection is like a table in relational databases. It holds documents.
- Collections do not enforce schemas (schema-less).
- A collection can store documents with different fields.

📄 3. Document
A document is a single record in MongoDB. It’s stored in BSON format (Binary JSON), but you write and read it as JSON.
- Each document is a key-value pair object.
- Every document must have a unique _id field (auto-generated if not provided).

## Database Commands

Create database

```
use <database_name>
```
This will create a new database by provided name or use an existing one.

Show databases

```
show dbs
```
This will display all existing databases.

Delete database

```
use <database_name>
db.dropDatabase()
```

## Collection Commands (CRUD operations)

### CREATE
Create collection

```
db.createCollection("<collection_name>")
```

Insert 1 record

```
db.student.insertOne({ name: "Binay", age: 30, score: {"maths":65, "english":60 })
```
Insert multiple records

```
db.student.insertMany([{name:"Ajay",age:24, score:{"maths":85, "english":90 }},
                       {name:"Bina",age:24, score:{"maths":65, "english":60 }},
                       {name:"Ram",age:23, score:{"maths":55, "english":60 }}])
```

### READ
Show all records

```
db.student.find()
```

Show record by filter
```
db.student.find({age:18})
```

Complex filter

```
db.student.find({score:{"maths":55, "english":60}})
```

Limit the row count

```
db.student.find().limit(2)
```

Sort output in asc

```
db.student.find().sort({ age: 1 })
```

Display all collections in db
```
show collections;
```

### UPDATE

Update single row

```
db.student.updateOne({ name: 'Nitesh' },
  { $set: { age: '35' } })
```
- Note : If you run this command and multiple records have the name "Nitesh", only the first matching document will be updated.

Update multiple rows

```
db.students.updateMany(
  { age: 27 },
  { $set: { age: '35' } }
)
```

Update table name

```
db.students.renameCollection('classroom')
```
Update column name (multiple)

```
db.students.updateMany(
  {},
  { $rename: { "subject": "course" } }
)
```

Update single column name

```
db.students.updateOne(
  { name: "Nitesh" },
  { $rename: { "subject": "course" } }
)
```

### DELETE
Delete single record

```
db.student.deleteOne({ name: "Ajay" })
```

Delete multiple records

```
db.student.deleteMany({ age: 24 })
```

Delete a collection
```
db.students.drop()
```


Start and stop mongoDB in macOS

```
brew services start mongodb/brew/mongodb-community@7.0
brew services stop mongodb/brew/mongodb-community@7.0
```
