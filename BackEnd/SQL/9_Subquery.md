# Subquery

## What is a Subquery?
A subquery is a query contained within another SQL statement.

A subquery is always enclosed within parentheses, 
and it is usually executed prior to the containing statement.

```sql
SELECT customer_id, first_name, last_name
FROM customer
WHERE customer_id = 
  (SELECT MAX(customer_id) 
  FROM customer);
```
