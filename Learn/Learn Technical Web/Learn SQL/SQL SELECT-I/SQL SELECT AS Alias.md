---
tags:
  - SQL
---
# SQL AS Alias Syntax
The syntax of the SQL `AS` command is:
```sql
SELECT column_1 AS alias_1, 
       column_2 AS alias_2, 
... ...column_n AS alias_n
FROM table_name;
```

Here,

- `column_1, column_2,...column_n` are the table columns
- `alias_1, alias_2,...alias_n` are the aliases of the table columns

For example,

```sql
SELECT first_name AS name
FROM Customers;
```

![[Pasted image 20250113212222.png]]

# SQL AS With More Than One Column

We can also use aliases with more than one column.

For example,

```sql
SELECT customer_id AS cid, first_name AS name
FROM Customers;
```

Here, the SQL command selects customer_id as cid and first_name as name.

# SQL AS With Expression

We can combine data from multiple columns and represent it in a single column using the `CONCAT()` function. For example,

```sql
SELECT CONCAT(first_name, ' ', last_name) AS full_name
FROM Customers;
```

Here, the SQL command selects first_name and last_name. And, the name of the column will be full_name in the result set.
# More SQL AS Examples

## SQL AS With Functions

It's a common practice to use `AS` to create aliases when working with functions. For example,

```sql
-- AS with functions
SELECT COUNT(*) AS total_customers
FROM Customers;
```


Here, the SQL command counts the total number of rows and represents the value as the total_customers attribute.

The result set of this command will have a total_customers column.

## SQL Table Alias

The `AS` keyword can also be used to give temporary names to tables. For example,

```sql
-- AS table alias
SELECT cu.first_name, cu.last_name
FROM Customers AS cu;
```


Here, the SQL command temporarily names the Customers table as cu and selects first_name and last_name from cu.

The result set of this command will have first_name and last_name as columns.

## SQL AS With JOIN

We can use AS aliases with table names to make our snippet short and clean while working with `JOIN`. For example,  
  

```
SELECT C.customer_id AS cid, C.first_name AS name, O.amount
FROM Customers AS C
JOIN Orders AS O
ON C.customer_id = O.customer_id;
```

[Run Code](https://www.programiz.com/sql/online-compiler)

Here, the SQL command temporarily names the Customers table as C and the Orders table as O and selects customer_id from C, first_name from C and amount from O.

The result set of this command will have cid, name and amount columns.

To learn more, visit [SQL JOIN](https://www.programiz.com/sql/join).