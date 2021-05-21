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



## 5.4 Set Function and Qualifiers

## 5.5 GROUP BY

## 5.6 HAVING

## 5.7 Summary