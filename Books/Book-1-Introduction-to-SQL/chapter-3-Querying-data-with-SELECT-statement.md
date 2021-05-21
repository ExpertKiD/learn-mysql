# Chapter 3 - Querying data with SELECT statement

## 3.1 Introduction

> You can think of a SELECT statement as a question you are asking the database.

Example:
* Who are all my contacts?
* Who are all my contacts with a first name of Jon?
* How many contacts do I have?

A Simple Query with SELECT:

```sql
SELECT 'Hello','World';
```

## 3.2 The SELECT List

The SELECT List most of the time contains:
* a list of columns from a table you want to query.
* a FROM clause is required for this cause.
* after every column comes a comma.
* Except: no comma after the last column.

```sql
SELECT <column_name>,<column_name>,<column_name> FROM <table_name>;

SELECT first_name, last_name FROM person;
```

## 3.3 SELECT List Wildcard (*)

 The `*` is the wild card character that pulls all the columns from a table.

```sql
SELECT * FROM person;
```

**BAD PRACTICE:** It's considered bad practice to select all the columns. So, it's better to specify the columns you want to 
fetch.

## 3.4 The FROM Clause

The FROM clause defines the table you want to query. It is possible to query multiple tables as well.

**GOOD PRACTICE:** It is a good practice to always qualify the `table` for the `column`.

```sql
SELECT first_name, last_name FROM person;
-- vs.
SELECT person.first_name, person.last_name FROM person;
```

**BEST PRACTICE:** It's best practice to always alias the table name as well as qualify the `table` name for the `column`.

```sql
SELECT person.first_name, person.last_name FROM person;
-- vs.
SELECT p.first_name, p.last_name FROM person p;
```

## 3.5 How to Constrain the Result Set

There are two ways to constrain the number of results.

1. WHERE Clause
2. DISTINCT Qualifier

## 3.6 DISTINCT and NOT DISTINCT

`NOT DISTINCT` is used by default in `SELECT` statement. It is used to ask question like below:

> What are the first names of all the people I knw?
```sql
SELECT p.first_name FROM person p;
```

`DISTINCT` gives all the unique entries for the `SELECT` statement.

> What are all the **unique** first_names of people I know?
```sql
SELECT DISTINCT p.first_name FROM person p;

SELECT DISTINCT p.first_name, p.last_name FROM person p;
```

**NOTE:** `DISTINCT` constraint applies to all the column names in the `SELECT` statement.

## 3.7 Summary