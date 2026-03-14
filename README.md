# SQL

# SQL A–Z Guide (Beginner to Advanced)

## Introduction

**SQL (Structured Query Language)** is the standard language used to interact with relational databases. It allows developers to store, retrieve, update, and manage data efficiently.

SQL is used in systems like:

* MySQL
* PostgreSQL
* SQLite
* Microsoft SQL Server
* Oracle Database

SQL is a core skill for **Backend Development, Data Analysis, and Full-Stack Development**.

---

# 1. What is a Database?

A **database** is an organized collection of data.

Example:

| id | name  | age |
| -- | ----- | --- |
| 1  | Rahim | 22  |
| 2  | Karim | 25  |

This data is stored inside a **table**.

---

# 2. SQL Basic Concepts

### Table

A table stores data in rows and columns.

### Row

A single record in the table.

### Column

A specific attribute of the data.

Example:

```
Students Table
--------------
ID | Name | Age
```

---

# 3. Types of SQL Commands

SQL commands are divided into **5 categories**.

## 1. DDL – Data Definition Language

Used to define database structure.

Commands:

```
CREATE
ALTER
DROP
TRUNCATE
```

Example:

```sql
CREATE TABLE students (
  id INT,
  name VARCHAR(50),
  age INT
);
```

---

## 2. DML – Data Manipulation Language

Used to modify data.

Commands:

```
INSERT
UPDATE
DELETE
```

Example:

Insert Data

```sql
INSERT INTO students (id, name, age)
VALUES (1, 'Rahim', 22);
```

Update Data

```sql
UPDATE students
SET age = 23
WHERE id = 1;
```

Delete Data

```sql
DELETE FROM students
WHERE id = 1;
```

---

## 3. DQL – Data Query Language

Used to retrieve data.

Command:

```
SELECT
```

Example:

```sql
SELECT * FROM students;
```

Select specific columns:

```sql
SELECT name, age FROM students;
```

---

## 4. DCL – Data Control Language

Commands:

```
GRANT
REVOKE
```

Example:

```sql
GRANT SELECT ON students TO user1;
```

---

## 5. TCL – Transaction Control Language

Commands:

```
COMMIT
ROLLBACK
SAVEPOINT
```

Example:

```sql
ROLLBACK;
```

---

# 4. Important SQL Clauses

## WHERE

Filters records.

```sql
SELECT * FROM students
WHERE age > 20;
```

---

## ORDER BY

Sorts results.

```sql
SELECT * FROM students
ORDER BY age ASC;
```

---

## LIMIT

Limits results.

```sql
SELECT * FROM students
LIMIT 5;
```

---

## DISTINCT

Removes duplicate values.

```sql
SELECT DISTINCT age FROM students;
```

---

# 5. SQL Operators

## Comparison Operators

```
=     Equal
!=    Not Equal
>     Greater than
<     Less than
>=    Greater or Equal
<=    Less or Equal
```

Example:

```sql
SELECT * FROM students
WHERE age >= 18;
```

---

## Logical Operators

```
AND
OR
NOT
```

Example:

```sql
SELECT * FROM students
WHERE age > 18 AND age < 30;
```

---

# 6. SQL Aggregate Functions

Used to perform calculations.

```
COUNT()
SUM()
AVG()
MIN()
MAX()
```

Example:

```sql
SELECT COUNT(*) FROM students;
```

```sql
SELECT AVG(age) FROM students;
```

---

# 7. GROUP BY

Groups rows with same values.

```sql
SELECT age, COUNT(*)
FROM students
GROUP BY age;
```

---

# 8. HAVING

Filters grouped results.

```sql
SELECT age, COUNT(*)
FROM students
GROUP BY age
HAVING COUNT(*) > 2;
```

---

# 9. SQL Joins

Joins combine data from multiple tables.

## INNER JOIN

```sql
SELECT students.name, courses.course
FROM students
INNER JOIN courses
ON students.id = courses.student_id;
```

---

## LEFT JOIN

Returns all records from left table.

```sql
SELECT *
FROM students
LEFT JOIN courses
ON students.id = courses.student_id;
```

---

## RIGHT JOIN

Returns all records from right table.

---

# 10. Primary Key

A **Primary Key** uniquely identifies each record.

Example:

```sql
CREATE TABLE students (
  id INT PRIMARY KEY,
  name VARCHAR(50)
);
```

---

# 11. Foreign Key

Connects two tables.

```sql
CREATE TABLE orders (
  id INT,
  student_id INT,
  FOREIGN KEY (student_id)
  REFERENCES students(id)
);
```

---

# 12. Index

Improves database search speed.

```sql
CREATE INDEX idx_name
ON students(name);
```

---

# 13. Views

A virtual table based on SQL query.

```sql
CREATE VIEW student_view AS
SELECT name, age
FROM students;
```

---

# 14. SQL Constraints

Constraints ensure data accuracy.

Types:

```
NOT NULL
UNIQUE
PRIMARY KEY
FOREIGN KEY
CHECK
DEFAULT
```

Example:

```sql
CREATE TABLE users (
  id INT PRIMARY KEY,
  email VARCHAR(100) UNIQUE
);
```

---

# 15. Transactions

Transactions ensure **data consistency**.

Example:

```sql
BEGIN;

UPDATE accounts
SET balance = balance - 100
WHERE id = 1;

UPDATE accounts
SET balance = balance + 100
WHERE id = 2;

COMMIT;
```

---

# 16. Subqueries

Query inside another query.

Example:

```sql
SELECT name
FROM students
WHERE age > (
  SELECT AVG(age)
  FROM students
);
```

---

# 17. SQL Best Practices

✔ Use **indexes for large tables**
✔ Always use **WHERE with UPDATE or DELETE**
✔ Normalize database tables
✔ Use meaningful column names
✔ Backup databases regularly

---

# 18. Real World SQL Example

Create a simple **User System**.

Create table:

```sql
CREATE TABLE users (
 id INT PRIMARY KEY AUTO_INCREMENT,
 name VARCHAR(50),
 email VARCHAR(100),
 created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

Insert user:

```sql
INSERT INTO users (name,email)
VALUES ('Mahim','mahim@email.com');
```

Get users:

```sql
SELECT * FROM users;
```

---

# Conclusion

SQL is one of the most important technologies for:

* Backend Development
* Data Analysis
* Software Engineering
* Full Stack Development

Learning SQL deeply will allow you to build **powerful applications and manage large datasets efficiently.**

---

