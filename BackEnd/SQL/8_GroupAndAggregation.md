# Group and Aggregation

## Grouping Concepts
```
SELECT customer_id, count(*)
FROM rental
GROUP BY customer_id;
```

The aggregate function `count()` counts the number of rows in each group, 
and the asterisk tells the server to count everything in the group.

When grouping data, you may need to filter out undesired data:
```sql
SELECT customer_id, count(*)
FROM rental
WHERE count(*) >= 40
GROUP BY customer_id;
# ERROR 1111 (HY000): Invalid use of group function
```

You cannot refer to the aggregate function `count(*)` in your where clause, 
because the groups have not yet been generated at the time the where clause is evaluated.

```sql
SELECT customer_id, count(*)
FROM rental
GROUP BY customer_id
HAVING count(*) >= 40;
```
So，the database server execute `WHERE` first and then `GROUP BY`;

## Aggregate Functions
Aggregate functions perform a specific operation over all rows in a group.

- Max(): Returns the maximum value within a set
- Min(): Returns the minimum value within a set
- Avg() Returns the average value across a set
- Sum(): Returns the sum of the values across a set
- Count(): Returns the number of values in a set

```sql
SELECT MAX(amount) max_amt, MIN(amount) min_amt, AVG(amount) avg_amt, SUM(amount) tot_amt, COUNT(*) num_payments
FROM payment;
# GROUP BY all rows in the table
```

```sql
SELECT customer_id, MAX(amount) max_amt, MIN(amount) min_amt, AVG(amount) avg_amt, SUM(amount) tot_amt, COUNT(*) num_payments
FROM payment
GROUP BY customer_id;
```

## Generating Groups
```sql
SELECT fa.actor_id, f.rating, count(*)
FROM film_actor fa
  INNER JOIN film f
  ON fa.film_id = f.film_id
GROUP BY fa.actor_id, f.rating
ORDER BY 1,2;
```
