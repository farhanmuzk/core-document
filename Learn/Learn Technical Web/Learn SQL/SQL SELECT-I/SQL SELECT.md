---
tags:
  - SQL
---
# SQL SELECT Syntax

The syntax of the SQL `SELECT` statement is:
For example,

```sql
-- select first_name and last_name columns from Customers table 
SELECT first_name, last_name
FROM Customers;
```

# SQL SELECT ALL
To select all columns from a database table, we use the `*` character. For example,

```sql
-- select all columns from Customers table 
SELECT *
FROM Customers;
```

# SQL SELECT WHERE Clause

A `SELECT` statement can have an optional `WHERE` clause. The `WHERE` clause allows us to fetch records from a database table that matches specified condition(s). For example,

```sql
-- select all columns from the customers table with last_name 'Doe' 
SELECT *
FROM Customers
WHERE last_name = 'Doe';
```

# SQL Operators

The `WHERE` clause uses operators to construct conditions. Some of the commonly used operators are:

## **1. Equal to Operator (=)**

```sql
-- select all columns from Customers table with first name 'John'
SELECT *
FROM Customers
WHERE first_name = 'John';
```

## **2. Greater than (>)**

```sql
-- select all columns from Customers table with age greater than 25
SELECT *
FROM Customers
WHERE age > 25;
```

## **3. AND Operator (AND)**

```sql
-- select all columns from Customers table with last_name 'Doe' and country 'USA'
SELECT *
FROM Customers
WHERE last_name = 'Doe' AND country = 'USA';
```

