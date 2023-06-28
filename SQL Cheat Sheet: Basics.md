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



# SQL Cheat Sheet: Intermediate - LIKE, ORDER BY, GROUP BY
| Command | Syntax                                                                                                         | Description                                                                                                             | Example                                                      |
| ------- | -------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------ |
| LIKE    | `SELECT column1, column2, ... FROM table_name WHERE columnN LIKE pattern;`                                    | `LIKE` operator is used in a WHERE clause to search for a specified pattern in a column.<br/>There are two wildcards often used in conjunction with the LIKE operator which are percent sign(%) and underscore sign (_). | `SELECT f_name , l_name FROM employees WHERE address LIKE '%Elgin,IL%';` |
| BETWEEN | `SELECT column_name(s) FROM table_name WHERE column_name BETWEEN value1 AND value2;`                          | The `BETWEEN` operator selects values within a given range. The values can be numbers, text, or dates. The `BETWEEN` operator is inclusive: begin and end values are included.  | `SELECT * FROM employees WHERE salary BETWEEN 40000 AND 80000;` |
| ORDER BY | `SELECT column1, column2, ... FROM table_name ORDER BY column1, column2, ... ASC|DESC;`                         | `ORDER BY` keyword is used to sort the result-set in ascending or descending order. The default is ascending.         | `SELECT f_name, l_name, dep_id FROM employees ORDER BY dep_id DESC, l_name;` |
| GROUP BY | `SELECT column_name(s) FROM table_name WHERE condition GROUP BY column_name(s) ORDER BY column_name(s);`         | `GROUP BY` clause is used in collaboration with the SELECT statement to arrange identical data into groups.           | `SELECT dep_id, COUNT(*) FROM employees GROUP BY dep_id;`    |
