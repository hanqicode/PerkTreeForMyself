# Filtering

## Condition Evaluation
If your where clause includes three or more conditions using both the `AND` and `OR` operators, 
you should use parentheses to make your intent clear, 
both to the database server and to anyone else reading your code.

## Condition Types

### Equality
`column = expression`;

### Inequality
`column != expression`;

### Range
```sql
SELECT customer_id, rental_date
FROM rental
WHERE rental_date < '2005-05-25';
```

### Between
```sql
SELECT customer_id, rental_date
FROM rental
WHERE rental_date BETWEEN '2005-06-14' AND '2005-06-16';
```
Remember that your upper and lower limits are **inclusive**, 
meaning that the values you provide are included in the range limits.

### String Ranges
```sql
SELECT last_name, first_name
FROM customer
WHERE last_name BETWEEN 'FA' AND 'FR';
```
Returns customers whose last name falls between FA and FR.

### Membership
```sql
SELECT title, rating
FROM film
WHERE rating IN ('G','PG');
```

## Null
`Null` can mean:
- Not applicable
- Value not yet known
- Value undefined

When working with `null`, you should remember:
- An expression can be null, but it can never equal null.
- Two nulls are never equal to each other.

```sql
SELECT rental_id, customer_id
FROM rental
WHERE return_date IS NULL;
```
