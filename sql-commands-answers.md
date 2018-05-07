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

>Write a command to create a new table to hold the books in a library with the columns ISBN, title, author, genre, publishing date, number of copies, and available copies.
* Find three books and add their information to the table.
* Someone has just checked out one of the books. Change the number of available copies to 1 fewer.
* Now one of the books has been added to the banned books list. Remove it from the table.


>Write a command to make a new table to hold spacecrafts. Information should include id, name, year launched, country of origin, a brief description of the mission, orbiting body, if it is currently operating, and its approximate miles from Earth. In addition to the table creation, provide commands that perform the following operations:
* Add three non-Earth-orbiting satellites to the table.
* Remove one of the satellites from the table since it has just crashed into the planet.
* Edit another satellite because it is no longer operating and change the value to reflect that.

>Write a command to create a new table to hold the emails in your inbox. This table should include an id, the subject line, the sender, any additional recipients, the body of the email, the timestamp, whether or not you have read the email, and the id of the email chain it's in. Also provide commands that perform the following operations:
* Add three new emails to the inbox.
* You deleted one of the emails, so write a command to remove the row from the inbox table.
* You started reading an email but just heard a crash in another room. Mark the email as unread before investigating the crash, so you can come back and read it later.
