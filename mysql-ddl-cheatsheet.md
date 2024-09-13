
# MySQL DDL (Data Definition Language) Cheatsheet

## Overview
DDL (Data Definition Language) is used to define and modify the database structure or schema. This includes commands to create, alter, and drop database objects such as tables, indexes, and views.

---

## Database Commands

### 1. Create Database
```sql
CREATE DATABASE database_name;
```

### 2. Drop Database
```sql
DROP DATABASE database_name;
```

### 3. Select Database
```sql
USE database_name;
```

---

## Table Commands

### 1. Create Table
```sql
CREATE TABLE table_name (
    column1 datatype [constraint],
    column2 datatype [constraint],
    ...
);
```

**Common Data Types**:
- `INT`, `FLOAT`, `DOUBLE`, `DECIMAL`, `VARCHAR(size)`, `CHAR(size)`, `DATE`, `DATETIME`, `TEXT`, `BOOLEAN`

**Common Constraints**:
- `PRIMARY KEY`, `FOREIGN KEY`, `UNIQUE`, `NOT NULL`, `AUTO_INCREMENT`

### Example:
```sql
CREATE TABLE employees (
    employee_id INT AUTO_INCREMENT PRIMARY KEY,
    first_name VARCHAR(50) NOT NULL,
    last_name VARCHAR(50) NOT NULL,
    hire_date DATE,
    department_id INT
);
```

### 2. Alter Table

- Add a column:
```sql
ALTER TABLE table_name ADD column_name datatype;
```

- Modify a column:
```sql
ALTER TABLE table_name MODIFY column_name datatype;
```

- Drop a column:
```sql
ALTER TABLE table_name DROP column_name;
```

- Rename a column:
```sql
ALTER TABLE table_name RENAME COLUMN old_name TO new_name;
```

- Rename a table:
```sql
ALTER TABLE old_table_name RENAME TO new_table_name;
```

### 3. Drop Table
```sql
DROP TABLE table_name;
```

---

## Index Commands

### 1. Create Index
```sql
CREATE INDEX index_name ON table_name (column1, column2, ...);
```

### 2. Drop Index
```sql
DROP INDEX index_name ON table_name;
```

---

## Primary Key & Foreign Key

### 1. Add Primary Key
```sql
ALTER TABLE table_name ADD PRIMARY KEY (column_name);
```

### 2. Drop Primary Key
```sql
ALTER TABLE table_name DROP PRIMARY KEY;
```

### 3. Add Foreign Key
```sql
ALTER TABLE table_name
ADD CONSTRAINT fk_name
FOREIGN KEY (column_name) REFERENCES parent_table (column_name);
```

### 4. Drop Foreign Key
```sql
ALTER TABLE table_name DROP FOREIGN KEY fk_name;
```

---

## Views

### 1. Create View
```sql
CREATE VIEW view_name AS
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

### 2. Drop View
```sql
DROP VIEW view_name;
```

---

## Constraints

### 1. Add Constraint
- Adding constraints while creating a table:
```sql
CREATE TABLE table_name (
    column1 datatype CONSTRAINT constraint_name constraint_type,
    column2 datatype CONSTRAINT constraint_name constraint_type
);
```

- Adding constraints to existing tables:
```sql
ALTER TABLE table_name ADD CONSTRAINT constraint_name constraint_type (column_name);
```

**Types of Constraints**:
- `PRIMARY KEY`
- `FOREIGN KEY`
- `UNIQUE`
- `NOT NULL`
- `CHECK`

### 2. Drop Constraint
```sql
ALTER TABLE table_name DROP CONSTRAINT constraint_name;
```

---

## Example Schema Creation

```sql
CREATE DATABASE company;
USE company;

CREATE TABLE departments (
    department_id INT AUTO_INCREMENT PRIMARY KEY,
    department_name VARCHAR(50) NOT NULL
);

CREATE TABLE employees (
    employee_id INT AUTO_INCREMENT PRIMARY KEY,
    first_name VARCHAR(50) NOT NULL,
    last_name VARCHAR(50) NOT NULL,
    hire_date DATE,
    department_id INT,
    FOREIGN KEY (department_id) REFERENCES departments(department_id)
);

CREATE INDEX idx_last_name ON employees (last_name);
```

---

## Other Commands

### 1. Truncate Table
```sql
TRUNCATE TABLE table_name;
```

### 2. Rename Table
```sql
RENAME TABLE old_table_name TO new_table_name;
```

---

## Conclusion

This cheat sheet summarizes essential DDL commands for MySQL, focusing on defining, altering, and deleting database objects like databases, tables, and indexes. DDL is a critical part of SQL that shapes the structure of your data. For more advanced usage, consider exploring MySQL's documentation.
