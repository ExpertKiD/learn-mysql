# Chapter 3 - Querying data with SELECT statement

## 3.1 Introduction

> You can think of a SELECT statement as a question you are asking the database.

Example:
* Who are all my contacts?
* Who are all my contacts with a first name of Jon?
* How many contacts do I have?

A Simple Query with SELECT:

```go
SELECT 'Hello','World';
```

## 3.2 The SELECT List

The SELECT List most of the time contains:
* a list of columns fro a table you want to query.
* a FROM clause is required for this cause.
* after every column comes a comma.
* Except: no comma ater the last column.

```sql
SELECT <column_name>,<column_name>,<column_name> FROM <table_name>;

SELECT first_name, last_name FROM person;
```

## 3.3 SELECT List Wildcard (*)

 The `*` is the wild card character that pulls all the columns from a table.

```sql
SELECT * FROM person;
```

## 3.4 The FROM Clause
## 3.5 How to Constrain the Result Set
## 3.6 DISTINCT and NOT DISTINCT
## 3.7 Summary