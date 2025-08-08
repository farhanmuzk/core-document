---
tags:
  - SQL
---
# SQL AND Operator

The SQL `AND` operator selects data if all conditions are `TRUE`. For example,

```sql
-- select the first_name and last_name of all customers
-- who live in 'USA' and have the last name 'Doe'

SELECT first_name, last_name
FROM Customers
WHERE country = 'USA' AND last_name = 'Doe';
```

# SQL OR Operator

The SQL `OR` operator selects data if any one condition is `TRUE`. For example,

```
-- select first and last name of customers
-- who either live in the USA
-- or have the last name 'Doe'

SELECT first_name, last_name
FROM Customers
WHERE country = 'USA' OR last_name = 'Doe';
```
# SQL NOT Operator

The SQL `NOT` operator selects data if the given condition is `FALSE`. For example,

```sql
-- select customers who don't live in the USA

SELECT first_name, last_name
FROM Customers
WHERE NOT country = 'USA';
```

# Example: Combining Multiple Operators in SQL
Let's look at another example of combining operators.

```sql
-- exclude customers who are from the USA and have 'Doe' as their last name

SELECT *
FROM customers
WHERE NOT country = 'USA' AND NOT last_name = 'Doe';
```

Here, the SQL command selects all customers where the country is not **USA** and last_name is not **Doe** from the Customers table.