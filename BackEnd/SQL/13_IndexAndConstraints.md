# Index and Constraint

## Indexes
```sql
SELECT first_name, last_name
FROM customer
WHERE last_name LIKE 'Y%';
```
To find all customers whose last name begins with Y, the server must visit each row in the customer table. 
This type of access is known as a **table scan**.

An index is simply a mechanism for finding a specific item within a resource. A database server uses indexes to locate rows in a table.

### Unique Index
When designing a database, it is important to consider which columns are allowed to contain duplicate data and which are not.

It serves as a mechanism for disallowing duplicate values in the indexed column.

### Type of Indexes

#### B-TREE INDEXES
All the indexes shown thus far are balanced-tree indexes, which are more commonly known as B-tree indexes.

#### BITMAP INDEXES
B-TREE can become unwieldy when built on a column that allows only a small number of values(like Enums).

#### TEXT INDEXES
If your database stores documents, you may need to allow users to search for words or phrases in the documents.

### How does Index work?
```sql
SELECT customer_id, first_name, last_name
FROM customer
WHERE 
  first_name LIKE 'S%' 
  AND last_name LIKE 'P%';
```

For this query, the server can employ any of the following strategies:
1. Scan all rows in the customer table
2. Use the index on the last_name column to find all customers whose last name starts with P, 
and then visit each row of the customer table to find only rows whose first name starts with S
3. Use the index on the last_name, first_name columns to find all customers whose last name starts with P and whose first name starts with S

### The Downside of Index
Every time a row is added to or removed from a table, all indexes on that table must be modified.

Therefore, the more indexes you have, the more work the server needs to do to keep all schema objects up-to-date, which tends to slow things down.
