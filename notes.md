### Introduction
🗃️ 1. Database
A MongoDB database is a container for collections. It’s similar to a schema or database in SQL systems.<br/>
- You can have multiple databases.
- Each database is independent and stores its own collections and indexes.

📂 2. Collection
A collection is like a table in relational databases. It holds documents.

Collections do not enforce schemas (schema-less).

A collection can store documents with different fields.

📄 3. Document
A document is a single record in MongoDB. It’s stored in BSON format (Binary JSON), but you write and read it as JSON.

Each document is a key-value pair object.

Every document must have a unique _id field (auto-generated if not provided).
