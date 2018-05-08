>How do you find related data held in two separate data tables?

an INNER JOIN statement

>Explain, in your own words, the difference between an INNER JOIN, LEFT OUTER JOIN, and RIGHT OUTER JOIN. Give a real-world example for each.

`INNER JOIN` returns what matches in both tables. example: two tables for an online student chat forum. one table holds information about the students (id, username, name) and the other holds information on the comments made (id, username, comment). INNER JOIN could be used to find the actual student name for the comments in the chat.
`LEFT OUTTER JOIN` returns all rows from the left table, even if there are no matches in the right table. Also returns matches from right table. example: continuing with the example above, if I wanted to have a record for all students in the db even if they didn't send a message, i could use `LEFT OUTTER JOIN`
`RIGHT OUTER JOIN` returns all rows from the right table, even if there are no matches in the left table. Also returns matches from left table.

>Define primary key and foreign key. Give a real-world example for each.

`Primary key` is a unique identifier for each row in a table. They can be thought of as an address.  If the rows in a table were mailboxes, then the primary key would be the listing of street addresses.

`Foreign key` is a set of one or more columns in a table that refers to the primary key in another table and is not unique to table.

>Define aliasing.

The technique of creating short variable names, usually a single letter, to replace the table name in, and simplify, a query.

>Change this query so that you are using aliasing:
SELECT professor.name, compensation.salary, compensation.vacation_days
FROM professor JOIN
compensation ON professor.id =
compensation.professor_id;

```
SELECT p.name, c.salary, c.vacation_days
FROM professor AS p
JOIN compensation AS c
ON p.id = c.professor_id;

```

>Why would you use a NATURAL JOIN? Give a real-world example.

A `NATURAL JOIN` is the method of implicitly joining tables based on shared columns. A natural join is just a shortcut to avoid typing, with a presumption that the join is simple and matches fields of the same name.

>Using this Employee schema and data, write queries to find the following information:
* List all employees and all shifts.

```
SELECT employees.name, shifts.date, shifts.start_time, shifts.end_time
FROM employees
JOIN shifts
ON employees.id = shifts.id;
```

>Using this Adoption schema and data, please write queries to retrieve the following information and include the results:
* Create a list of all volunteers. If the volunteer is fostering a dog, include each dog as well.

```
SELECT volunteers.first_name, dogs.name AS dog_name
FROM volunteers
LEFT OUTER JOIN dogs
ON volunteers.foster_dog_id = dogs.id;


first_name	dog_name
Rubeus	Munchkin
Marjorie	Marmaduke
Sirius	(null)
Remus	(null)
Albus	(null)
```
> * The cat's name, adopter's name, and adopted date for each cat adopted within the past month to be displayed as part of the "Happy Tail" social media promotion which posts recent successful adoptions.

```

```
* Create a list of adopters who have not yet chosen a dog to adopt.
* Lists of all cats and all dogs who have not been adopted.
* The name of the person who adopted Rosco.

```

```

>Using this Library schema and data, write queries applying the following scenarios and include the results:
* To determine if the library should buy more copies of a given book, please provide the names and position, in order, of all of the patrons with a hold (request for a book with all copies checked out) on "Advanced Potion-Making".
* List all of the library patrons. If they have one or more books checked out, list the books with the patrons.
