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

The `AND` keyword combines two expressions. If both are `TRUE`, row is included. If either is `FALSE`, row is excluded.

> Who are all the people in my contact list that have the first name Jon and birthday later than 1965?

```sql
SELECT p.first_name, p.last_name
    FROM person p
    WHERE p. first_name='Jon'
    AND p.birth_date > '12/31/1965';
``` 

## 4.4 The `OR` keyword

The `OR` keyword combines two expressions. If either is `TRUE`, row is included. If both are `FALSE`, row is excluded.

> Who are all the people in my contact list that have the first name John or last name of 'Flanders'?

```sql
SELECT p.first_name, p.last_name
    FROM person p
    WHERE p. first_name='Jon'
    OR p.last_name='Flanders';
``` 
## 4.5 Other Boolean operators

Other Boolean operators:

* `BETWEEN` operator
* `LIKE` operator
* `IN` operator
* `IS` operator
* `IS NOT` operator

## 4.6 `BETWEEN`

The `BETWEEN` operator acts on a column and two values. It is `TRUE` if column value is between two values. The two 
values are included in the expression (like `>=` and `<=`).

> Who are all the people in my cotact list that I have contacted at least once but no more than 20 times?

```sql
SELECT p.first_name, p.last_name
    FROM person p
    WHERE P.contacted BETWEEN 1 AND 20;
```

## 4.7 `LIKE`

`LIKE` is a fuzzy version of `=`. It allows for string with special characters inside i.e. wildcards. If the wildcard 
match is true, the row is included otherwise excluded.

> Who are all the people in my contact list that have a first name athat beings with the letter J?

```sql
SELECT p.first_name, p.last_name
    FROM person p 
    WHERE p.first_name LIKE 'j%';
```

Wildcards: 

* Percentage(`%`): any string of zero or more characters.
* Underscore(`_`):any single character.

## 4.8 `IN`

`IN` is like a multi-value operator. It works with a list of potential values. It evaluates to `TRUE` if any of th values
in the list is "hit".

> Who are all the people in my contact list that are named Jon or Fritz?

```sql
SELECT p.first_name, p.last_name
    FROM person p 
    WHERE p.first_name IN ('Jon','Fritz');
```

## 4.9 `IS`

`IS` is a special operator like the equals operator, but only works with `NULL`.

> Who are all the people in my contact list that don't have a last name?

```sql
SELECT p.first_name, p.last_name
    FROM person p 
    WHERE p.last_name IS NULL;
```

## 4.10 `IS NOT`

`IS NOT` is a special operator like the not equals operator, but only works with `NULL`.

> Who are all the people in my contact list that have a last name?

```sql
SELECT p.first_name, p.last_name
    FROM person p 
    WHERE p.last_name IS NOT NULL;
```

## 4.11 Summary

The `WHERE` clause enables us to restrict the result set of our queries. The more complex our question is, the more complex
the `WHERE` clause becomes.
