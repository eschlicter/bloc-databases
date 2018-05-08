Use the commands above to complete the following tasks, and submit the SQL statements. Real-world examples must be distinct from those used in the text.

>List the commands for adding, updating, and deleting data.

`INSERT INTO` adds data into a table
`UPDATE` edits existing records within table
`DELETE FROM` removes data from table

>Explain the structure for each type of command.

`INSERT INTO nameOfTable VALUES (columnInfo1, columnInfo2, columnInfo3 ...);`

`UPDATE nameOfTable SET specificColumn=updatedInfo WHERE locationInTable;`

`DELETE FROM nameOfTable WHERE conditionsAreListed;`

>What are some of the data types that can be used in tables? Give a real-world example of each type.

Postgres has more than 40 different data types. Some of the categories include numbers (bigint, decimal, double precision, float4, float8, int, int2, int4, int8, money, numeric, real, serial, serial2, serial4, smallint, smallserial), text (char, character, character varying, text, varchar), and Date/Time (date, interval, time, timestamp).

When going to any ticketed event (i.e. movies, festivals, concerts...) tables are used that have numbers, text, and the date/time of the event and/or the date/time of purchase.


>Decide how to create a new table to hold a list of people invited to a wedding dinner. The table needs to have first and last names, whether they sent in their RSVP, the number of guests they are bringing, and the number of meals (1 for adults and 1/2 for children).
* Which data type would you use to store each of the following pieces of information?
  * First and last name.
  * Whether they sent in their RSVP.
  * Number of guests.
  * Number of meals.
* Write a command that creates the table to track the wedding dinner.
* Write a command that adds a column to track whether the guest sent a thank you card.
* You have decided to move the data about the meals to another table, so write a command to remove the column storing the number meals from the wedding table.
* The guests will need a place to sit at the reception, so write a command that adds a column for table number.
* The wedding is over and we do not need to keep this information, so write a command that deletes the table numbers from the database.

```
CREATE TABLE guest list (
  last name text,
  first name text,
  RSVP status boolean,
  tag-alongs integer,
  meals numeric
  );

ALTER TABLE guest list ADD COLUMN thankyou boolean;
ALTER TABLE guest list DROP COLUMN meals;
ALTER TABLE guest list ADD COLUMN table number integer;
DROP TABLE guest list;
```

>Write a command to create a new table to hold the books in a library with the columns ISBN, title, author, genre, publishing date, number of copies, and available copies.
* Find three books and add their information to the table.
* Someone has just checked out one of the books. Change the number of available copies to 1 fewer.
* Now one of the books has been added to the banned books list. Remove it from the table.

```
CREATE TABLE library books (
  ISBN biginteger,
  title text,
  author text,
  genre text,
  published date(year),
  copies integer,
  copies available integer;
  );

INSERT INTO library books (isbn, title, author, genre, published, copies, copies available) VALUES
(0060256656, 'The Giving Tree', 'Shel Silverstein', 'Childrens Lit', 1964, 3, 1),
(978-0394800011, 'The Cat in the Hat', 'Dr. Seuss', 'Childrens Lit', 1957, 4, 4),
(1558580093, 'The Rainbow Fish', 'Marcus Pfister', 'Childrens Lit', 1992, 3, 2);

UPDATE library books SET copies available=3 WHERE isbn=978-0394800011;
DELETE FROM library books WHERE isbn=1558580093;

```

>Write a command to make a new table to hold spacecrafts. Information should include id, name, year launched, country of origin, a brief description of the mission, orbiting body, if it is currently operating, and its approximate miles from Earth. In addition to the table creation, provide commands that perform the following operations:
* Add three non-Earth-orbiting satellites to the table.
* Remove one of the satellites from the table since it has just crashed into the planet.
* Edit another satellite because it is no longer operating and change the value to reflect that.

```
CREATE TABLE spacecrafts (
  id varchar,
  name text,
  year launched integer,
  country text,
  mission summary text,
  orbiting body text,
  active boolean,
  miles from earth numeric
);
INSERT INTO spacecrafts (id, name, year launched, country, mission summary, orbiting body, active, miles from earth) VALUES
(2013-063A, 'Maven', 2013, 'USA', 'Give insight into the history of Mars' atmosphere and climate, liquid water and planetary habitability by determining how volatiles from the Martian atmosphere have escaped into space over time. Provide communications support to other Mars missions', 'Mars', true, 33900000),

(2009-031A, 'Lunar Reconnaissance Orbiter', 2009, 'USA', 'NASA's Lunar Reconnaissance Orbiter (LRO) was sent to the Moon to make high-resolution maps of the composition of the lunar surface and seek out potential sources of water-ice that may exist in the bottom of dark polar craters. The spacecraft is seeking potential landing sites and resources for future human exploration of the Moon. LRO was launched with theLCROSS lunar impact mission', 'Earth's Moon', true, 238,800),

(2008-052A, 'Chandrayaan-1', 2008, 'India', 'Chandrayaan-1 is an Indian Space Research Organization (ISRO) orbiter designed to test India's technological capabilities and return scientific information about the geological, mineralogical and topographical characteristics of the Moon. It also carried NASA's Moon Mineralogy Mapper (M3) instrument to the Moon', 'Earth's Moon', false, 225,623);

DELETE FROM spacecrafts WHERE id=2009-031A;
UPDATE spacecrafts SET active=false WHERE id=2013-063A;

```

>Write a command to create a new table to hold the emails in your inbox. This table should include an id, the subject line, the sender, any additional recipients, the body of the email, the timestamp, whether or not you have read the email, and the id of the email chain it's in. Also provide commands that perform the following operations:
* Add three new emails to the inbox.
* You deleted one of the emails, so write a command to remove the row from the inbox table.
* You started reading an email but just heard a crash in another room. Mark the email as unread before investigating the crash, so you can come back and read it later.

```
CREATE TABLE emails (
  id integer,
  subject text,
  sender text,
  cc text DEFAULT 'N/A',
  body text,
  receivedAt timestamp,
  read boolean,
  chainId varchar
  );

INSERT INTO emails (id, subject, sender, cc, body, receivedAt, read, chainId)
VALUES
(3, 'Your program is now frozen', 'Bloc', 'Kinsey', 'Your program is frozen until Monday, May 14', 2018-05-07 01:30:00, true, 0123),
(2, '[Bloc] [Assignment] Submission approved...', 'Bloc', '', 'Great job!', 2018-05-06 05:30:00, true, 0456),
(1, 'Hello World', 'Jessica R.', 'Rebecca L.', 'I am learning to code', 2018-05-05 12:30:00, true, 98701);

DELETE FROM emails WHERE id=1 AND read=true;
UPDATE emails SET read=false WHERE id = 3;
```
