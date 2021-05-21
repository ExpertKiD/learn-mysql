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

Boolean Operators:
* Equals (`=`)
* Not equal to (`<>`)
* Greater than (`>`)
* Less than (`<`)
* Greater or equal (`>=`)
* Less or equal (`<=`)

All these operators are used to form a single expression, but we need to link multiple expression most of the time. And, we'll learn
those keywords in the next section.

## 4.3 The `AND` keyword

The `AND` keyword combines two expressions. If both are `TRUE`, row is included. If either is `FALSE`, now is excluded.

> Who are all the people in my contact list that have the first name John and birthday later than 1965?

```sql
SELECT p.first_name, p.last_name
    FROM person p
    WHERE p. first_name, p.last_name
    AND p.birth_date > '12/31/1965';
``` 

## 4.4 The `OR` keyword

## 4.5 Other Boolean operators

## 4.6 `BETWEEN`

## 4.7 `LIKE`

## 4.8 `IN`

## 4.9 `IS`

## 4.10 `IS NOT`

## 4.11 Summary