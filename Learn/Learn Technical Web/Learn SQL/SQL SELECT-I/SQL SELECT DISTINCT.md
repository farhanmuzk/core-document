---
tags:
  - SQL
---
	# Syntax of SQL SELECT DISTINCT

```sql
SELECT DISTINCT column1, column2 ...
FROM table;
```

Here,

- `column1, column2, ...` are the table columns
- `table` is table name from where we retrieve the distinct columns

---

## Example: SQL SELECT DISTINCT

```sql
-- select the unique countries from the customers table

SELECT DISTINCT country
FROM Customers;
```

![[Pasted image 20250113211636.png]]

---
# SQL DISTINCT on Multiple Columns

We can also use `SELECT DISTINCT` with multiple columns. For example,

```sql
-- select rows if the first name and country of a customer is unique

SELECT DISTINCT country, first_name
FROM Customers;
```

![[Pasted image 20250113211722.png]]

# DISTINCT With COUNT

We can use SQL `DISTINCT` with the [COUNT()](https://www.programiz.com/sql/count) function to count the number of unique rows.

Let's look at an example.

```sql
-- count the unique countries where customers are from 
SELECT COUNT(DISTINCT country)
FROM Customers;
```

![[Pasted image 20250113211807.png]]

