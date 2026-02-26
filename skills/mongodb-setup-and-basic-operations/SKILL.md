---
name: mongodb-setup-and-basic-operations
description: Install MongoDB and perform basic database operations with collections and documents
version: 1.0.0
metadata:
  skill_forge:
    domain: "mongodb"
    generated_at: "2026-02-26T10:00:00Z"
    validation_passed: true
    sources_used: 5
  hermes:
    tags: [mongodb, database, nosql, documents]
    category: database
---

# MongoDB Setup and Basic Operations

## When to Use
When you need to set up a MongoDB database and perform basic CRUD operations with document-based data storage.

## Prerequisites
- Administrative access to install software
- Basic understanding of JSON format
- Command line interface available

## Procedure
1. Download MongoDB Community Edition: Visit https://www.mongodb.com/try/download/community and select your OS
2. Install MongoDB: `sudo apt-get install -y mongodb-org` (Ubuntu/Debian) or follow OS-specific instructions
3. Start MongoDB service: `sudo systemctl start mongod`
4. Enable MongoDB on boot: `sudo systemctl enable mongod`
5. Connect to MongoDB shell: `mongosh` or `mongo`
6. Create a database: `use mydatabase`
7. Create a collection and insert document: `db.users.insertOne({name: "John", email: "john@example.com"})`
8. Query documents: `db.users.find()`
9. Update a document: `db.users.updateOne({name: "John"}, {$set: {age: 30}})`
10. Delete a document: `db.users.deleteOne({name: "John"})`

## Verification
- Check MongoDB status: `sudo systemctl status mongod`
- Connect to shell and run: `db.runCommand({ping: 1})`
- Verify sample operations: `db.users.find().pretty()`

## Pitfalls
- MongoDB requires sufficient disk space and may fail silently if storage is full
- Default installation has no authentication enabled - secure for production use
- BSON document size limit is 16MB - design schemas accordingly
- Always use proper indexing for production queries to avoid performance issues

## Sources
- https://www.mongodb.com/
- https://en.wikipedia.org/wiki/MongoDB
- https://github.com/mongodb/mongo
- https://www.ibm.com/think/topics/mongodb
- https://www.w3schools.com/mongodb/