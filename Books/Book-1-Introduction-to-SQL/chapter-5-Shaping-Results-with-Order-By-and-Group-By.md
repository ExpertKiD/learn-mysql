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

## 5.5 GROUP BY

## 5.6 HAVING

## 5.7 Summary