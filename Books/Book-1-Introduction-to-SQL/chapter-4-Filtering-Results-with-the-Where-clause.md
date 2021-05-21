# 4. Filtering Results with the WHERE Clause

## 4.1 The `WHERE` Clause

* The `WHERE` clause tells the database to constrain the result set. 
* It comes after the `FROM` clause. 
* It only returns the result set that have the boolean expression results to `true`.

> What is the last name of all the people I know whose first name is John?

```sql
SELECT p.last_name                  -- SELECT clause
    FROM person p                   -- FROM clause
    WHERE p.first_name = 'John'     -- WHERE clause
``` 

## 4.2 Boolean Operators

## 4.3 The `AND` keyword

## 4.4 The `OR` keyword

## 4.5 Other Boolean operators

## 4.6 `BETWEEN`

## 4.7 `LIKE`

## 4.8 `IN`

## 4.9 `IS`

## 4.10 `IS NOT`

## 4.11 Summary