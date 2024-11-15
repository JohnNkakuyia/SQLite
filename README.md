# SQLite Database Guide

This guide provides essential techniques for working with SQLite databases, focusing on connecting to a database, exploring schema information, executing queries, and modifying database structures.

## Getting Started

SQLite is a lightweight database engine ideal for local data analysis. This guide covers basic operations such as connecting to a database, retrieving data, and modifying table structures.

### Prerequisites

- Python 3.x
- `sqlite3` library (usually built-in with Python)
- `pandas` library (optional, for DataFrame operations)

---

<img src = 'Database-Schema.png' alt= 'Database-Schema.png'>

## Sections

### 1. Establishing a Connection

To connect to an SQLite database file, use the `sqlite3.connect()` method:
To connect to an SQLite database file, use the `sqlite3.connect()` method:

```python
import sqlite3

conn = sqlite3.connect('database_name.sqlite')  # Connects to the SQLite database
```
The `conn` object allows you to execute SQL commands, manage transactions, and interact with the database file.
### 2. Using a Cursor
A cursor object is essential for executing SQL commands:
```python
cur = conn.cursor()  # Creates a cursor for executing SQL commands
```
The cursor serves as an intermediary to send queries and retrieve results from the database.

### 3. Schema Exploration
To explore the database structure and get details on columns, types, and constraints, use the `PRAGMA table_info` command:
``` python
cur.execute("PRAGMA table_info(table_name)")
```
You can also load this schema information directly into a Pandas DataFrame for easier analysis:
```python
import pandas as pd

schema_df = pd.read_sql("PRAGMA table_info(table_name)", conn)
```

### 4. Executing Queries and Data Retrieval
Use SELECT statements to retrieve data, which can be loaded directly into a Pandas DataFrame:
```python
query = "SELECT * FROM table_name WHERE conditions ORDER BY column_name LIMIT 10"
df = pd.read_sql(query, conn)
```
Common Query Features:
* `WHERE`: Filters records based on specified conditions.
* `ORDER BY`: Sorts the results.
* `LIMIT`: Restricts the number of rows returned.

  ### 5. Altering Table Structure
To modify the structure of a table, use the ALTER TABLE command. For example, adding a new column with:
```sql
ALTER TABLE customers ADD COLUMN creditLimitNumeric REAL;
```
After adding the column, you can populate it by converting data types using `CAST`:

```sql
UPDATE customers SET creditLimitNumeric = creditLimit;
```

[jupyter notebook](https://github.com/JohnNkakuyia/SQLite/blob/main/SQL.ipynb)  

[pdf](https://github.com/JohnNkakuyia/SQLite/blob/main/SQL_SELECT_notebook.oxps)

# SQL Querying with Python: Planets Database
#### Goals:

This project aims to explore and manipulate a SQL database using Python. The key objectives include:

1. Connecting to a SQL database.
2. Retrieving all records and specific subsets using SELECT and WHERE clauses.
3. Filtering, ordering, and selecting specific columns from the database.
4. Writing Python code to interact with a database and display results.

Here is the []() and []()


