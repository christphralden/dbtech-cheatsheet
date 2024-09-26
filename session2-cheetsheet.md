
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
This will return all students whose names start with 'A'.

- `IS NULL`: Used to check if a value is NULL.
```sql
SELECT * FROM students WHERE age IS NULL;
```
This will return all students whose `age` value is NULL.

- `BETWEEN`: Used to filter values within a given range.
```sql
SELECT * FROM students WHERE age BETWEEN 18 AND 25;
```
This will return all students whose age is between 18 and 25.

## 3. String Functions
String functions are used to perform operations on string data types. Here are some common ones:

- `CONCAT`: Concatenates two or more strings together.
```sql
SELECT CONCAT(first_name, ' ', last_name) AS full_name FROM students;
```

- `GROUP_CONCAT`: Returns a concatenated string of values from a group.
```sql
SELECT GROUP_CONCAT(name SEPARATOR ', ') FROM students;
```

- `LENGTH`: Returns the length of a string.
```sql
SELECT LENGTH(name) FROM students WHERE id = 1;
```

- `LOWER`: Converts a string to lowercase.
```sql
SELECT LOWER(name) FROM students;
```

- `UPPER`: Converts a string to uppercase.
```sql
SELECT UPPER(name) FROM students;
```

- `LEFT`: Extracts a substring from a string (starting from the left).
```sql
SELECT LEFT(name, 3) FROM students;
```

- `RIGHT`: Extracts a substring from a string (starting from the right).
```sql
SELECT RIGHT(name, 3) FROM students;
```

- `LIKE`: Used to search for a specified pattern in a column.
```sql
SELECT * FROM students WHERE name LIKE '%son';
```

- `REPLACE`: Replaces occurrences of a specified substring.
```sql
SELECT REPLACE(name, 'John', 'Jonathan') FROM students;
```

- `SUBSTR`/`SUBSTRING`: Extracts a substring from a string.
```sql
SELECT SUBSTRING(name, 2, 4) FROM students;
```

- `REVERSE`: Reverses a string.
```sql
SELECT REVERSE(name) FROM students;
```

## 4. Date Functions
Date functions are used to manipulate date values.

- `ADDDATE`: Adds a specific number of days to a date.
```sql
SELECT ADDDATE('2023-09-01', 10) AS new_date;
```

- `CURDATE`: Returns the current date.
```sql
SELECT CURDATE();
```

- `DATE_FORMAT`: Formats a date based on a specified format.
```sql
SELECT DATE_FORMAT(NOW(), '%Y-%m-%d');
```

- `DATEDIFF`: Returns the difference in days between two dates.
```sql
SELECT DATEDIFF('2023-09-26', '2023-09-01');
```

- `DAYNAME`: Returns the name of the day for a given date.
```sql
SELECT DAYNAME('2023-09-26');
```

- `DAY`, `MONTH`, `YEAR`: Extracts the day, month, or year from a date.
```sql
SELECT DAY(NOW()), MONTH(NOW()), YEAR(NOW());
```
