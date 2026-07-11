# SQL Notes

## What is SQL?
- **SQL** (Structured Query Language) — A programming language used to
query, define and manipulate data stored in a relational database
- SQL allows you to create tables, modify them, delete them and
manipulate the data contained in them
- Every SQL query ends with a semicolon `;`

---

## Relational vs Non-Relational Databases
| | Relational (SQL) | Non-Relational (NoSQL) |
|---|---|---|
| **Data format** | Structured, tables with rows and columns | Non-tabular, flexible format |
| **Examples** | MySQL, Oracle, PostgreSQL, Microsoft SQL Server | MongoDB, Redis, CouchDB |
| **Best for** | Structured data with clear relationships | Unstructured or varying data |
| **Relationships** | Yes, via foreign keys | No fixed relationships |

---

## Key Database Concepts
- **Table** — Where all data is stored in a relational database
(ex: a Books table storing book records)
- **Column** — Defines what pieces of information are stored
(ex: id, name, published_date)
- **Row** — A single record inserted into a table
(ex: one book entry)
- **Primary Key** — A column that ensures data is unique for each
record in a table
- **Foreign Key** — A column in one table that links to another
table, creating a relationship between them
- **DBMS** — Database Management System, software that allows users
to retrieve, update and manage stored data:
  - MySQL
  - Oracle Database
  - Microsoft SQL Server
  - PostgreSQL
  - MariaDB
  - MongoDB

---

## CRUD Operations
CRUD stands for the four basic database operations:
| Operation | SQL Command | Description |
|-----------|-------------|-------------|
| **Create** | `INSERT INTO` | Add new records to a table |
| **Read** | `SELECT` | Fetch data from a table |
| **Update** | `UPDATE` | Modify existing records |
| **Delete** | `DELETE` | Remove records from a table |

---

## Database Commands
```sql
-- Create a database
CREATE DATABASE database_name;

-- Show all databases
SHOW DATABASES;

-- Select a database to use
USE database_name;

-- Delete a database
DROP DATABASE database_name;
```

---

## Table Commands
```sql
-- Create a table
CREATE TABLE table_name (
  id INT PRIMARY KEY,
  name VARCHAR(100),
  published_date DATE
);

-- Show table structure and column types
DESCRIBE table_name;

-- Modify a table
ALTER TABLE table_name ADD column_name datatype;

-- Delete a table
DROP TABLE table_name;
```

---

## The SELECT Statement
The SELECT statement has 6 clauses — only the first two are mandatory:

```sql
SELECT column1, column2      -- Clause 1: MANDATORY - columns to retrieve
FROM table_name              -- Clause 2: MANDATORY - table to query
WHERE condition              -- Clause 3: optional - filter results
GROUP BY column              -- Clause 4: optional - group results
HAVING condition             -- Clause 5: optional - filter grouped results
ORDER BY column ASC/DESC;    -- Clause 6: optional - sort results
LIMIT number;                -- Limit the number of results displayed
```

### SELECT Examples
```sql
-- Select all columns
SELECT * FROM users;

-- Select specific columns
SELECT first_name, last_name FROM users;

-- Select with condition
SELECT * FROM users WHERE username = 'pierre';

-- Select with ordering
SELECT * FROM books ORDER BY published_date DESC;

-- Select with limit
SELECT * FROM users LIMIT 10;
```

---

## INSERT Statement
```sql
-- Insert a new record
INSERT INTO table_name (column1, column2, column3)
VALUES (value1, value2, value3);

-- Example
INSERT INTO users (first_name, last_name, email)
VALUES ('Pierre', 'Diedhiou', 'pierre@email.com');
```

---

## UPDATE Statement
```sql
-- Update an existing record
UPDATE table_name
SET column1 = value1, column2 = value2
WHERE condition;

-- Example
UPDATE users SET email = 'new@email.com' WHERE id = 1;
```

---

## DELETE Statement
```sql
-- Delete records matching a condition
DELETE FROM table_name WHERE condition;

-- Example
DELETE FROM users WHERE id = 1;
```

---

## Comparison Operators
| Operator | Name | Description |
|----------|------|-------------|
| `=` | Equal | Checks if two values are equal |
| `!=` | Not Equal | Checks if two values are not equal |
| `<` | Less Than | Checks if value is less than another |
| `>` | Greater Than | Checks if value is greater than another |
| `<=` | Less Than or Equal | Checks if value is less than or equal |
| `>=` | Greater Than or Equal | Checks if value is greater than or equal |

---

## ORDER BY Options
| Option | Description | Example |
|--------|-------------|---------|
| `ASC` | Ascending order (A to Z, smallest to largest) | `ORDER BY name ASC` |
| `DESC` | Descending order (Z to A, largest to smallest) | `ORDER BY name DESC` |

---

## String Functions
| Function | Description | Example |
|----------|-------------|---------|
| `CONCAT()` | Combines two or more strings together | `CONCAT(first_name, ' ', last_name)` |
| `GROUP_CONCAT()` | Concatenates data from multiple rows into one field | `GROUP_CONCAT(name)` |
| `SUBSTRING()` | Retrieves a substring from a string at a given position | `SUBSTRING(name, 1, 3)` |
| `LENGTH()` | Returns the number of characters in a string | `LENGTH(password)` |

---

## Aggregate Functions
Aggregate functions combine multiple row values into a single result:

| Function | Description | Example |
|----------|-------------|---------|
| `COUNT()` | Returns the number of records | `COUNT(id)` |
| `SUM()` | Returns the sum of all values in a column | `SUM(salary)` |
| `AVG()` | Returns the average value of a column | `AVG(salary)` |
| `MAX()` | Returns the maximum value in a column | `MAX(salary)` |
| `MIN()` | Returns the minimum value in a column | `MIN(salary)` |

### Aggregate Function Examples
```sql
-- Count all users
SELECT COUNT(*) FROM users;

-- Sum of all salaries
SELECT SUM(salary) FROM employees;

-- Average salary
SELECT AVG(salary) FROM employees;

-- Highest salary
SELECT MAX(salary) FROM employees;

-- Lowest salary
SELECT MIN(salary) FROM employees;

-- Group by with aggregate
SELECT department, AVG(salary)
FROM employees
GROUP BY department
HAVING AVG(salary) > 50000;
```

---

## GROUP BY and HAVING
```sql
-- Group results by a column
SELECT department, COUNT(*)
FROM employees
GROUP BY department;

-- Filter grouped results using HAVING
SELECT department, COUNT(*)
FROM employees
GROUP BY department
HAVING COUNT(*) > 5;
```

---

## SQL Injection (Security Note)
SQL Injection is one of the most common web vulnerabilities.
It occurs when user input is inserted directly into a SQL query
without validation, allowing attackers to manipulate the query.

```sql
-- Normal login query
SELECT * FROM users WHERE username='pierre' AND password='1234';

-- SQL Injection attack input: ' OR '1'='1
-- Resulting malicious query:
SELECT * FROM users WHERE username='' OR '1'='1' AND password='';
-- This returns ALL users because '1'='1' is always true!
```

**Prevention:** Always use prepared statements and validate user input.
## SQL Injection (SQLi)

### What is SQL Injection?
SQL Injection is a cyberattack where an attacker inserts malicious
SQL code into a website input field (like a login form or search bar)
to trick the backend database into running unauthorized commands.

### How SQL Injection Works
```sql
-- Normal login query
SELECT * FROM users WHERE username='pierre' AND password='1234';

-- Attacker input: ' OR '1'='1
-- Resulting malicious query:
SELECT * FROM users WHERE username='' OR '1'='1' AND password='';
-- Returns ALL users because '1'='1' is always true!
```

### Types of SQL Injection
| Type | Description |
|------|-------------|
| **In-band SQLi** | Results returned directly in the web page |
| **Blind SQLi** | No visible output, attacker infers results |
| **Error-based SQLi** | Database error messages reveal information |
| **Union-based SQLi** | Uses UNION to retrieve data from other tables |
| **Time-based SQLi** | Uses time delays to infer true/false conditions |

### SQL Injection Prevention
| Method | Description |
|--------|-------------|
| **Prepared Statements** | Separates SQL code from user input |
| **Input Validation** | Validates and sanitizes all user input |
| **WAF** | Web Application Firewall blocks malicious queries |
| **Least Privilege** | Database accounts only have minimum required permissions |

### SQLMap — Automated SQL Injection Tool
- See `linux-commands.md` for full SQLMap command reference
## Pentest Key Lessons

### Core Penetration Testing Principles
| Principle | Description |
|-----------|-------------|
| **Enumeration is everything** | Map the application structure, headers, endpoints and behavior before attempting exploitation |
| **Small flaws chain into big compromises** | IDOR, weak password resets and upload bypasses connect to create devastating attacks |
| **Client-side restrictions are not security** | Browser-side checks are easily bypassed, always enforce server-side validation |
| **Use allowlists not blocklists** | Blocklists miss alternative extensions and edge cases, allowlists are more secure |
| **Password resets need careful attention** | A single design flaw can lead to full account takeover |
| **Think like an attacker, report like a consultant** | Finding vulnerabilities is half the job, documenting them clearly with severity ratings and remediation advice is what makes the engagement valuable |

### Vulnerability Severity Rating Guide
| Severity | Description | Example |
|----------|-------------|---------|
| **Critical** | Immediate full system compromise | Remote Code Execution |
| **High** | Significant data exposure or takeover | IDOR exposing all user data |
| **Medium** | Limited impact or requires chaining | Weak password reset token |
| **Low** | Minimal impact, hard to exploit | Information disclosure |
| **Informational** | No direct impact but worth noting | Server version in headers |
## SQL Injection — OWASP Context

### Why SQL Injection is Still Critical
SQL Injection has been in the OWASP Top 10 for over a decade
because it remains one of the most common and impactful web
vulnerabilities. It falls under the broader **Injection** category
in OWASP Top 10 2025 (A03).

### Prevention in SQL Context
```sql
-- VULNERABLE — never do this
query = "SELECT * FROM users WHERE username='" + username + "'"

-- SAFE — use parameterized queries
query = "SELECT * FROM users WHERE username = ?"
execute(query, [username])
```
