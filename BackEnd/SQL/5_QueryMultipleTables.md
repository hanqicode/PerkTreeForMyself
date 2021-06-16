# Query Multiple Tables

## What is a Join?

### Cartesian Product
```sql
SELECT c.first_name, c.last_name, a.address
FROM customer c JOIN address;
```

Many of the customers seem to have the same street address. 
Because the query didn’t specify how the two tables should be joined, 
the database server generated the Cartesian product, 
which is every **permutation** of the two tables.

It is also known as **Cross Join**.

### Inner Join
```sql
SELECT c.first_name, c.last_name, a.address
FROM customer c JOIN address a
  ON c.address_id = a.address_id;
```

## Joining Three Or More Tables
Note: SQL is a nonprocedural language, 
meaning that you describe what you want to retrieve and which database objects need to be involved, 
but it is up to the database server to determine how best to execute your query.

So it's no matter how you define the order of tables to be joined.
