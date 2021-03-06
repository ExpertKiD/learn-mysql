# Chapter 5 - Shaping Results with `ORDER BY` and `GROUPING BY`

## 5.1 Introduction

Sometimes you want the result set to be different than the data returned by a simple SELECT statement.

## 5.2 ORDER BY

The main way we order the result set is using the `ORDER BY`. 

* used after the the `WHERE` clause (if there is one)
* separate columns by commas
* separate columns by commas
* `ASC` (default) or `DESC`

> Who are all the people in my contact list ordered by last name?

```sql
SELECT p.first_name, p.last_name
    FROM person p 
    ORDER BY p.last_name;
```

## 5.3 Set Functions

Now commonly used function with `ORDER BY` is the set function. Set function compute new values from column values. They 
are used in place of columns in `SELECT` clause. 

* passes column name to the function
* helps to ask more interesting questions
* often used with the `DISTINCT` qualifier

Functions:

1. `COUNT()`        - count of the column specified (inculdes `NULL` if * is specified)
2. `MAX()`          - maximum value of the column (does not include `NULL` values)
3. `MIN()`          - minimum value of the column (does not include `NULL` values)
4. `AVG()`          - average of all value of column (does not include `NULL` values)
5. `SUM()`          - sum of all the value of the column ( does not include `NULL` values, only numeric column)

> What is the toatal numbe of times I've contacted my contacts?

```sql
SELECT SUM(p.contacted_number) 
    FROM person p;
```

## 5.4 Set Function and Qualifiers

* Often used together
* Add qualifier like `DISTINCT` inside of the function
* Run against `DISTINCT` column values

> What is the count of unique first names among my contacts?

```sql
SELECT COUNT(DISTINCT p.first_name)
    FROM person p;
```

## 5.5 GROUP BY

* `GROUP BY` allows multiple columns with a set function
* It breaks the result set into subsets
* Runs se function against each subset
* Result set returns 1 row per subset
* Subset is dictated by column in `GROUP BY`
* Column must appear in the `SELECT LIST`
* Appears after `FROM` and/or `WHERE` clause

> What is the count of every unique first names amongs my contacts?

```sql
SELECT COUNT(p.first_name),
    p.first_name
    FROM person p 
    GROUP BY p.first_name;
```

## 5.6 HAVING

`HAVING` clause, like `WHERE` clause, works against `SELECT`. It allows you to restrict the subset.

> What is the count of unique first names among my contacts that appear at least 5 times?

```sql
SELECT 
    COUNT (DISTINCT p.first_name),
    p.first_name
    FROM person p
    GROUP BY p.first_name
    HAVING COUNT(DISTINCT p.first_name) >= 5;
    
-- or

SELECT
    COUNT (DISTINCT p.first_name) AS FirstNameCount,
    p.first_name
    FROM person p
    GROUP BY p.first_name
    HAVING FirstNameCount >= 5;
```
## 5.7 Summary

* Answering more complex questions requires more complex queries
* `ORDER BY` to sort result sets
* SET functions to roll-up or slice
* `GROUP BY` to create subsets
* `HAVING` to restrict `GROUP BY`