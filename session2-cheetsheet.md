
# SQL Query Notes

## 1. Simple Query
Simple queries are the most basic form of SQL query, allowing you to retrieve data from a database.

**Example:**
```sql
SELECT * FROM students;
```
This query selects all records from the `students` table.

## 2. Conditional Query
Conditional queries allow you to filter records based on specific conditions using the `WHERE` clause.

**Common Conditions:**
- `LIKE`: Used to search for a specified pattern in a column.
```sql
SELECT * FROM students WHERE name LIKE 'A%';
```
*Output Example:* This will return all students whose names start with 'A'.

- `IS NULL`: Used to check if a value is NULL.
```sql
SELECT * FROM students WHERE age IS NULL;
```
*Output Example:* This will return all students whose `age` value is NULL.

- `BETWEEN`: Used to filter values within a given range.
```sql
SELECT * FROM students WHERE age BETWEEN 18 AND 25;
```
*Output Example:* This will return all students whose age is between 18 and 25.

## 3. String Functions
String functions are used to perform operations on string data types. Here are some common ones:

- `CONCAT`: Concatenates two or more strings together.
```sql
SELECT CONCAT(first_name, ' ', last_name) AS full_name FROM students;
```
*Output Example:* John Doe

- `GROUP_CONCAT`: Returns a concatenated string of values from a group.
```sql
SELECT GROUP_CONCAT(name SEPARATOR ', ') FROM students;
```
*Output Example:* John, Mary, Tom

- `LENGTH`: Returns the length of a string.
```sql
SELECT LENGTH(name) FROM students WHERE id = 1;
```
*Output Example:* 4 (Length of 'John')

- `LOWER`: Converts a string to lowercase.
```sql
SELECT LOWER(name) FROM students;
```
*Output Example:* john

- `UPPER`: Converts a string to uppercase.
```sql
SELECT UPPER(name) FROM students;
```
*Output Example:* JOHN

- `LEFT`: Extracts a substring from a string (starting from the left).
```sql
SELECT LEFT(name, 3) FROM students;
```
*Output Example:* Joh (First three letters)

- `RIGHT`: Extracts a substring from a string (starting from the right).
```sql
SELECT RIGHT(name, 3) FROM students;
```
*Output Example:* ohn (Last three letters)

- `LIKE`: Used to search for a specified pattern in a column.
```sql
SELECT * FROM students WHERE name LIKE '%son';
```
*Output Example:* Jason (Names that end with 'son')

- `REPLACE`: Replaces occurrences of a specified substring.
```sql
SELECT REPLACE(name, 'John', 'Jonathan') FROM students;
```
*Output Example:* Jonathan (Replaces 'John' with 'Jonathan')

- `SUBSTR`/`SUBSTRING`: Extracts a substring from a string.
```sql
SELECT SUBSTRING(name, 2, 4) FROM students;
```
*Output Example:* ohn (From 2nd position, 4 characters)

- `REVERSE`: Reverses a string.
```sql
SELECT REVERSE(name) FROM students;
```
*Output Example:* nhoJ (Reversed name)

- `POSITION`: Finds the position of a substring in a string.
```sql
SELECT POSITION('a' IN 'database') AS pos;
```
*Output Example:* 2 (The first occurrence of 'a')

## 4. Date Functions
Date functions are used to manipulate date values.

- `ADDDATE`: Adds a specific number of days to a date.
```sql
SELECT ADDDATE('2023-09-01', 10) AS new_date;
```
*Output Example:* 2023-09-11

- `CURDATE`: Returns the current date.
```sql
SELECT CURDATE();
```
*Output Example:* 2023-09-26 (The current date)

- `DATE_FORMAT`: Formats a date based on a specified format.
```sql
SELECT DATE_FORMAT(NOW(), '%Y-%m-%d');
```
*Output Example:* 2023-09-26

- `DATEDIFF`: Returns the difference in days between two dates.
```sql
SELECT DATEDIFF('2023-09-26', '2023-09-01');
```
*Output Example:* 25 (Difference in days)

- `DAYNAME`: Returns the name of the day for a given date.
```sql
SELECT DAYNAME('2023-09-26');
```
*Output Example:* Tuesday

- `DAY`, `MONTH`, `YEAR`: Extracts the day, month, or year from a date.
```sql
SELECT DAY(NOW()), MONTH(NOW()), YEAR(NOW());
```
*Output Example:* 26, 9, 2023 (Day, Month, Year)

- `DATE_ADD`: Adds a specified interval to a date.
```sql
SELECT DATE_ADD('2023-09-01', INTERVAL 2 MONTH);
```
*Output Example:* 2023-11-01 (Adds 2 months)

- `DATE_SUB`: Subtracts a specified interval from a date.
```sql
SELECT DATE_SUB('2023-09-01', INTERVAL 7 DAY);
```
*Output Example:* 2023-08-25 (Subtracts 7 days)

## Conclusion
These SQL functions are essential for performing various operations on databases. By mastering them, you will be able to manipulate and retrieve data more effectively.
