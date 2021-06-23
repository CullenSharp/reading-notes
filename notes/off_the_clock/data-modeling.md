# Data Modeling

June 17th, 2021

## NoSQL vs SQL

Mongo, an example of a noSQL db, is document based. Think of a JSON object.

SQL is structed and relational. Relationships are made formal by keys. 

- a 'Primary KEY' is completely unique and used for keeping data seperate
- a 'Foreign KEY' is a key that isn't always unique, but always refers to a place in another table

for example...

### Children table

| _ID | name | parent |
| --- | --- | --- |
| 1 | Peter | Roger |
| 2 | Sam | Margaret |

---

### Parent table

| _ID | name | child |
| --- | ---| --- |
| 3 | Roger | Peter |
| 4 | Maragaret | Sam |

The _ID is the primary key

child and parent are foreign keys that allow us to refer and connect different tables

### types of realtionships

- One-to-Many
- One-to-One
- Many-to-Many

### using collections to create one to many
<!--  -->