## Selecting Data
When trying to get data, all SQL queries start with a SELECT statement. You can specify columns, or use * to display all columns. For example:

```sql
SELECT * -- this will display all columns in the table.
```
 ```sql
SELECT client_number -- This will only display the client number column.
;
```
```
SELECT client_number, first_given_name, surname -- This will display the client number, first name and surname columns.
;
```

Tables are identified by the FROM statement which comes directly after the SELECT statement. Using the above statements, we can expand them like this:
```sql
SELECT * -- this will display all columns in the table.
FROM clients -- This means the query will look at the clients table.
;
 ```

```sql
SELECT client_number -- This will only display the client number column.
FROM clients -- This means the query will look at the clients table.
;
 ```

```sql
SELECT client_number, first_given_name, surname -- This will display the client number, first name and surname columns.
FROM clients -- This means the query will look at the clients table.
;
```


## Table Aliases
To easily identify tables, you can add aliases when selecting them. This is particularly useful when using multiple tables which could include columns with the same names.

```sql
SELECT * FROM clients cc
;
```
In this example we give the clients table the alias "cc". This means next time we want to refer to this table, we can simply use cc. You can use any sort of alias you like, using the first letter of each word can be helpful.

###Ending a statement
Sometimes you have multiple queries on the same file. To ensure the system knows where one query ends and the next one begins we add ; to the end.

```sql
SELECT surname, first_given_name, birth_date
FROM clients
;
```

## Comments
Some queries you might want to leave notes so you (or future you) won't forget why you have that line there. You might also decide to remove a line temporarily to see if it is actually required. You can do that using comments:

```sql
-- Lines starting with "--" are "Comments".  These lines are ignored in the query.
select --select the headings/column names you want
from --the name of the table
;
```

## A Simple Query
The basic query which you can use for any table to return all columns. Try it, just replace TABLE_NAME with the table of your choosing.

```sql
--This quick query shows all columns in the table.
SELECT * FROM table_name
```

## Where / And
Now you now how to get data, we need to work out how to get the actual data we need. For this we have the WHERE statement. WHERE follows the FROM statement.

```sql
SELECT *
FROM clients
WHERE surname = 'SMITH'
```

 You can choose how to define this with a where statement.  Using where you can use different "identifiers" including:
```sql
where SURNAME in ('name','another name','yet another name') --only those in list will be returned
and SURNAME not in ('name','another name','yet another name') --everything but those in list will be returned
and SURNAME like ('l%') --everything that starts with "l" will be returned (% is a wildcard)
and SURNAME not like ('%m') --everything that does not end with "m" will be returned
and SURNAME = 'list' --exact match will be returned
and SURNAME <> 'each' --everything that does not match will be returned
and BIRTH_DATE between '01JAN1970' and '01DEC1970' --where date falls between these.
-- NOTE: "where" only applies for first line.  Additional "where" statements are to be "and" statements.
```
