# SQL Cheat Sheet: Basics
Command  | Syntax                                    | Description                                        | Example
---------|-------------------------------------------|----------------------------------------------------|---------------
SELECT   | `SELECT column1, column2, ... FROM table_name;` | Fetch data from a database                         | `SELECT city FROM placeofinterest;`
WHERE    | `SELECT column1, column2, ... FROM table_name WHERE condition;` | Extract records that fulfill a specified condition | `SELECT * FROM placeofinterest WHERE city = 'Rome';`
COUNT    | `SELECT COUNT * FROM table_name;`          | Count the number of rows when a column is not NULL  | `SELECT COUNT(country) FROM placeofinterest WHERE country = 'Canada';`
DISTINCT | `SELECT DISTINCT columnname FROM table_name;` | Return unique values in specified columns           | `SELECT DISTINCT country FROM placeofinterest WHERE type = 'historical';`
LIMIT    | `SELECT * FROM table_name LIMIT number;`   | Specify the maximum number of rows in the result set | `SELECT * FROM placeofinterest WHERE airport = 'pearson' LIMIT 5;`
INSERT   | `INSERT INTO table_name (column1,column2,column3...) VALUES(value1,value2,value3...);` | Insert new rows in the table | `INSERT INTO placeofinterest (name,type,city,country,airport) VALUES('Niagara Waterfalls','Nature','Toronto','Canada','Pearson');`
UPDATE   | `UPDATE table_name SET [column1]=[VALUES] WHERE [condition];` | Update rows in the table | `UPDATE placeofinterest SET name = 'Niagara Falls' WHERE name = "Niagara Waterfalls";`
DELETE   | `DELETE FROM table_name WHERE [condition];` | Remove rows from the table specified in the WHERE condition | `DELETE FROM placeofinterest WHERE city IN ('Rome','Vienna');`
