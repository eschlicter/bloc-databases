>Write out a generic SELECT statement.

```
SELECT column
FROM table
WHERE condition;
```

>Create a fun way to remember the order of operations in a SELECT statement, such as a mnemonic.

SELECT your columns
FROM & JOINs determine & filter rows
WHERE more filters on the rows
GROUP BY combines those rows into groups
HAVING filters groups
ORDER BY arranges the remaining rows/groups
LIMIT filters on the remaining rows/groups

S-F-J-W-G-H-O-L

"Sam's Friends Just Won't Go Home Or Leave"

>Given this dogs table, write queries to select the following pieces of data:
Intake teams typically guess the breed of shelter dogs, so the breed column may have multiple words (for example, "Labrador Collie mix").
* Display the name, gender, and age of all dogs that are part Labrador.
* Display the ids of all dogs that are under 1 year old.
* Display the name and age of all dogs that are female and over 35lbs.
* Display all of the information about all dogs that are not Shepherd mixes.
* Display the id, age, weight, and breed of all dogs that are either over 60lbs or Great Danes.

```
SELECT name, gender, age
FROM dogs
WHERE breed LIKE '%labrador%';

SELECT id
FROM dogs
WHERE age < 1;

SELECT name
FROM dogs
WHERE gender = 'F' AND weight > 35;

SELECT *
FROM dogs
WHERE breed NOT LIKE '%shepherd%';

SELECT id, age, weight, breed
FROM dogs
WHERE weight > 60 OR breed='great dane';

```

>Given this cats table, what records are returned from these queries?
* SELECT name, adoption_date FROM cats;
* SELECT name, age FROM cats;

```
name	adoption_date
Mushi	2016-03-22
Seashell	(null)
Azul	2016-04-17
Victoire	2016-09-01
Nala	(null)


name	age
Mushi	1
Seashell	7
Azul	3
Victoire	7
Nala	1
```

>From the cats table, write queries to select the following pieces of data.
* Display all the information about all of the available cats.
* Choose one cat of each age to show to potential adopters.
* Find all of the names of the cats, so you don’t choose duplicate names for new cats.

```
SELECT *
FROM cats
WHERE adoption_date=null;

SELECT DISTINCT age
FROM cats;

SELECT DISTINCT name
FROM cats;
```

>List each comparison operator and explain when you would use it. Include a real world example for each.

equal =
not equal != , <>
greater than or equal to >=
less than or equal to <=
greater than >
less than <


>From the cats table, what data is returned from these queries?
* SELECT name FROM cats WHERE gender = ‘F’;
* SELECT name FROM cats WHERE age <> 3;
* SELECT ID FROM cats WHERE name != ‘Mushi’ AND gender = ‘M’;

```
name
Seashell
Nala

name
Mushi
Seashell
Victoire
Nala

id
3
4
```
