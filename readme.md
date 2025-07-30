# Introduction
Welcome to the wide world of SQL. I hope you're ready to be confused.

## What is SQL?
SQL stands for Structured Query Language. It is a type of computer language which we primarily use to "extract" data from our databases.

There are different "types" of databases. All use SQL but have slight differences which you may or may not work out along the way. To help guide you with terms you will hear, we have:

**Oracle** - this is generally a physical server somewhere locally
**Postgres** - this is used more by the systems "in the cloud"

## Row IDs
Every  "Row ID" is specific to a table as a primary key.  This means, every row in that table has it's own unique row id.   From here that row id is used to link that line into other tables.
eg. You have 3 tables
```
CUSTOMER
ITEM
PURCHASE
```
Each customer will have a unique row id. Each Item will have a unique id. To when a customer makes a purchase, a new row will be inserted in to the purchase table, which again would get it's own row id.

So we can link each purchase to both the item and the customer, there would be columns for customer_id and item_id within the purchase table.


## Common Errors when writing SQL's
- Error states "FROM keyword not found were expected". In this case it is because a comma should be between column names in SELECT.
- Error states missing right parenthesis is the case it is because is missing the closing bracket.
