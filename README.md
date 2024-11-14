# SQLite Database Guide

This guide provides essential techniques for working with SQLite databases, focusing on connecting to a database, exploring schema information, executing queries, and modifying database structures.

## Getting Started

SQLite is a lightweight database engine ideal for local data analysis. This guide covers basic operations such as connecting to a database, retrieving data, and modifying table structures.

### Prerequisites

- Python 3.x
- `sqlite3` library (usually built-in with Python)
- `pandas` library (optional, for DataFrame operations)

---

## Sections

### 1. Establishing a Connection

To connect to an SQLite database file, use the `sqlite3.connect()` method:

```python
import sqlite3

conn = sqlite3.connect('database_name.sqlite')  # Connects to the SQLite database
### Using the Connection Object

The `conn` object allows you to execute SQL commands, manage transactions, and interact with the database file.

### 2. Using a Cursor

A cursor object is essential for executing SQL commands:

```python
cur = conn.cursor()  # Creates a cursor for executing SQL commands
