# Query Primer

## Query Mechanics
Once the server has verified your username and password, it will generate a **database connection**.

Once the server has verified you and issued you a connection, you are ready to execute queries. The server will do 3 pre-checks:
1. Do you have the permission to execute the statement?
2. Do you have the permission to access the desired data?
3. Is you statement syntax correct?

Then the **query optimizer** will determine the most efficient way to execute your query.

## Query Clauses
- Select: which columns to include in the result set;
- From: identify tables from which to retrieve data and how the tables should be joined;
- Where: filter out unwanted data;
- Group By: group rows together by common column values;
- Having: filter out unwanted groups;
- Order By: sort rows of the final result set by one or more columns;

## Select
It is one of the **last** clauses that the database server evaluates.

### Column Alias
```sql
SELECT language_id AS id
FROM language;
```

### Removing Duplicates
```sql
SELECT DISTINCT actor_id
FROM actors
ORDER BY actor_id;
```

## From
The from clause defines:
1. the tables used by a query
2. along with the means of linking the tables together

### Table Links
```sql
SELECT customer.name, rental_time
FROM customer 
  JOIN rental
  ON customer.customer_id = rental.customer_id
WHERE xxxx;
```

### Table Alias
```sql
SELECT c.first_name, r.rental_time
FROM customer AS c
  JOIN rental AS r
  ON c.customer_id = r.customer_id
WHERE xxxx;
```

## Where
```sql
SELECT  title
FROM film
WHERE film.rating = 'G' 
  AND film.duration >= 7; 
```

```sql
SELECT  title
FROM film
WHERE 
  (film.rating = 'G' AND film.duration >= 7)
  OR
  (film.rating = 'F' AND file.duration >= 10);
```

## Group By and Having
