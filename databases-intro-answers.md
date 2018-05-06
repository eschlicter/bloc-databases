Exercises
Create a new repository on GitHub to hold your assignments for the Databases module. Create a new branch for Checkpoint 1. Submit your answers.

> What data types do each of these values represent?

"A Clockwork Orange" - string
42 - integer
09/02/1945 - date
98.7 - float
$15.99 - float

>Explain when a database would be used. Explain when a text file would be used.

If we are not going to be altering or changing our data, or if only person will be manipulating data, it *might* be acceptable to use a text file. However, if multiple people are going to be making changes to data at one time, or if we need to access the data beyond a particular application process, a database should be used.

>Describe one difference between SQL and other programming languages.

SQL is a declarative language, not a procedural language.

>In your own words, explain how the pieces of a database system fit together at a high level.

A database is similar to a spreadsheet. It consists of a table, with rows and columns that are made up of individual data cells. Columns tell us what the data represents, and rows organize the data into recognizable units. It is able to be queried and/or manipulated.

>Explain the meaning of table, row, column, and value.

Again, similar to a spreadsheet. A table contains rows and columns. The columns go from top to bottom, and the rows reach from left to right, all of the values are divided into individual cells and assigned to a particular type of data.

>List three data types that can be used in a table.

Integer, float, string

Given this payments table, provide an English description of the following queries and include their results:

```
     SELECT date, amount
     FROM payments;

     SELECT amount
     FROM payments
     WHERE amount > 500;

     SELECT *
     FROM payments
     WHERE payee = 'Mega Foods';

```


Request 1 is asking for all dates and amounts from the payments table. It would return: 5/1/2016, 1500.00; 5/10/2016, 37.00; 5/15/2016, 124.93; 5/23/2016, 54.72.

Request 2 is asking for any amounts greater than $500. It will only return 1500.00.

Request 3 is asking for all information related to payee 'Mega Foods'. It will return: 5/15/2016 Mega Foods 124.93 Groceries

> Given this users table, write SQL queries using the following criteria and include the output:

The email and sign-up date for the user named DeAndre Data.

```
SELECT email, signup
FROM users
WHERE name = 'DeAndre Data';
```

The user ID for the user with email 'aleesia.algorithm@uw.edu'.

```
SELECT userid
FROM users
WHERE email = 'aleesia.algorithm@uw.edu';
```

All the columns for the user ID equal to 4.

```
SELECT *
FROM users
WHERE userid = 4;
```
