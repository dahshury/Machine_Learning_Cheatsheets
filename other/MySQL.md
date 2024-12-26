# MySQL Cheatsheet

## 1. Querying Tables

| **Description**                     | **Query**                                   | **Additional Notes**                                      |
|--------------------------------------|---------------------------------------------|-----------------------------------------------------------|
| Select all columns from a table      | `SELECT * FROM table_name;`                 | Returns all rows and columns from the specified table.     |
| Select specific columns              | `SELECT column1, column2 FROM table_name;`  | Used to query specific columns for better performance.     |
| Select with alias                    | `SELECT column1 AS alias1 FROM table_name;` | Useful for renaming columns in the output for readability. |
| Select distinct values               | `SELECT DISTINCT(column) FROM table_name;`  | Eliminates duplicate values in the results.                |
| Select with conditions (WHERE)       | `SELECT * FROM table_name WHERE condition;` | Filters rows based on a condition. See filtering section.  |
| Select with LIMIT                    | `SELECT * FROM table_name LIMIT 10;`        | Restricts the number of rows returned to a specific limit. |
| Select with ORDER BY                 | `SELECT * FROM table_name ORDER BY column1 DESC;` | Sorts results based on one or more columns, ascending or descending. |
| Select with JOIN (Inner Join)        | `SELECT * FROM table1 INNER JOIN table2 ON table1.id = table2.fk_id;` | Combines rows from two tables based on a related column.   |
| Select with LEFT JOIN                | `SELECT * FROM table1 LEFT JOIN table2 ON table1.id = table2.fk_id;`  | Returns all rows from the left table, with matching rows from the right table. |
| Select with RIGHT JOIN               | `SELECT * FROM table1 RIGHT JOIN table2 ON table1.id = table2.fk_id;` | Returns all rows from the right table, with matching rows from the left table. |

---

## 2. Filtering Data

| **Description**                          | **Query**                                                  | **Additional Notes**                                         |
|-------------------------------------------|------------------------------------------------------------|--------------------------------------------------------------|
| Filter with single condition              | `SELECT * FROM table_name WHERE column = 'value';`          | Filters rows where the column matches the specified value.    |
| Filter with multiple conditions (AND)     | `SELECT * FROM table_name WHERE column1 = 'val1' AND column2 = 'val2';` | Both conditions must be true for the row to be selected.     |
| Filter with multiple conditions (OR)      | `SELECT * FROM table_name WHERE column1 = 'val1' OR column2 = 'val2';`  | Either condition can be true for the row to be selected.      |
| Filter using IN                           | `SELECT * FROM table_name WHERE column IN ('val1', 'val2');` | Filters rows where the column matches any value in the list. |
| Filter using BETWEEN                      | `SELECT * FROM table_name WHERE column BETWEEN 10 AND 20;`  | Filters rows within a range of values.                        |
| Filter with NULL values                   | `SELECT * FROM table_name WHERE column IS NULL;`            | Returns rows where the column contains NULL values.           |
| Filter with NOT NULL values               | `SELECT * FROM table_name WHERE column IS NOT NULL;`        | Returns rows where the column does not contain NULL values.   |
| Filter with LIKE (partial match)          | `SELECT * FROM table_name WHERE column LIKE 'abc%';`        | Filters rows with values that match the pattern. `%` is a wildcard. |
| Filter with case sensitivity (BINARY)     | `SELECT * FROM table_name WHERE BINARY column = 'value';`   | Enforces case-sensitive comparison in the WHERE clause.       |
| Filter with EXISTS                        | `SELECT * FROM table_name WHERE EXISTS (SELECT 1 FROM other_table WHERE condition);` | Returns rows only if the subquery returns any rows.           |

---

## 3. Aggregating Data

| **Description**                             | **Query**                                                | **Additional Notes**                                            |
|---------------------------------------------|----------------------------------------------------------|-----------------------------------------------------------------|
| Count all rows                              | `SELECT COUNT(*) FROM table_name;`                        | Counts all rows, including those with NULL values.               |
| Count non-NULL values                       | `SELECT COUNT(column) FROM table_name;`                   | Counts non-NULL values in the specified column.                  |
| Calculate sum                               | `SELECT SUM(column) FROM table_name;`                     | Returns the sum of all non-NULL values in the specified column.   |
| Calculate average                           | `SELECT AVG(column) FROM table_name;`                     | Returns the average of all non-NULL values.                       |
| Find minimum value                          | `SELECT MIN(column) FROM table_name;`                     | Returns the minimum value in the specified column.                |
| Find maximum value                          | `SELECT MAX(column) FROM table_name;`                     | Returns the maximum value in the specified column.                |
| Group by column                             | `SELECT column, COUNT(*) FROM table_name GROUP BY column;`| Groups rows that have the same values in the specified column.    |
| Group by with HAVING (filter groups)        | `SELECT column, COUNT(*) FROM table_name GROUP BY column HAVING COUNT(*) > 1;` | Filters groups after the grouping stage, similar to WHERE but for aggregated results. |
| Group by with multiple columns              | `SELECT col1, col2, COUNT(*) FROM table_name GROUP BY col1, col2;` | Groups by multiple columns. Useful for more complex aggregations. |

---

## 4. MySQL Syntax

| **Description**                          | **Query**                                                | **Additional Notes**                                          |
|------------------------------------------|----------------------------------------------------------|---------------------------------------------------------------|
| Create a new database                    | `CREATE DATABASE database_name;`                         | Creates a new database in the MySQL server.                    |
| Drop a database                          | `DROP DATABASE database_name;`                           | Deletes the database and all its tables. Be careful with this! |
| Create a new table                       | `CREATE TABLE table_name (column1 datatype, column2 datatype, ...);` | Defines a new table with specified columns and datatypes.      |
| Drop a table                             | `DROP TABLE table_name;`                                 | Deletes the table. Irreversible operation.                     |
| Alter a table (add column)               | `ALTER TABLE table_name ADD column_name datatype;`        | Adds a new column to the existing table.                       |
| Alter a table (modify column)            | `ALTER TABLE table_name MODIFY column_name datatype;`     | Modifies the datatype or properties of an existing column.      |
| Alter a table (drop column)              | `ALTER TABLE table_name DROP COLUMN column_name;`         | Removes a column from the table. Irreversible operation.        |
| Create index                             | `CREATE INDEX index_name ON table_name (column1, column2);` | Creates an index to speed up queries on specified columns.     |
| Drop index                               | `DROP INDEX index_name ON table_name;`                    | Removes an index from a table.                                 |

---

## 5. CRUD Operations (Create, Read, Update, Delete)

| **Description**                          | **Query**                                                | **Additional Notes**                                          |
|------------------------------------------|----------------------------------------------------------|---------------------------------------------------------------|
| Insert a new row                         | `INSERT INTO table_name (column1, column2) VALUES (value1, value2);` | Adds a new row with the specified values into the table.       |
| Insert multiple rows                     | `INSERT INTO table_name (column1, column2) VALUES (val1, val2), (val3, val4);` | Inserts multiple rows in a single query.                      |
| Update existing row                      | `UPDATE table_name SET column1 = value1 WHERE condition;` | Updates one or more columns for rows that match the condition. |
| Delete row                               | `DELETE FROM table_name WHERE condition;`                 | Deletes rows that match the specified condition. Irreversible. |
| Truncate table (delete all rows)         | `TRUNCATE TABLE table_name;`                              | Removes all rows from a table without logging individual row deletions. |
| Replace existing row                     | `REPLACE INTO table_name (column1, column2) VALUES (value1, value2);` | Deletes existing row if it exists, then inserts a new row.     |
| Insert if not exists (ON DUPLICATE KEY)  | `INSERT INTO table_name (column1, column2) VALUES (val1, val2) ON DUPLICATE KEY UPDATE column1 = value1;` | Inserts or updates a row based on key conflicts.               |
