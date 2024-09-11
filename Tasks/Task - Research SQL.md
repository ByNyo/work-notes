## Tables
#### CREATE
**CREATE Syntax**
```mysql
CREATE TABLE table_name(
	column1 datatype,
	column2 datatype,
	column3 datatype,
	.....
	columnN datatype,
	PRIMARY KEY ( one or more columns )
);
```
**CREATE Example**
```mysql
CREATE TABLE Customers(
	ID INT NOT NULL,
	NAME VARCHAR(20) NOT NULL,
	AGE INT NOT NULL,
	ADRESS CHAR(25),
	SALARY DECIMAL(18,2),
	PRIMARY KEY (ID)
);
```
With the last example you can run into problems. For example because the table already exists. But don't worry there is a way to make sure you don't run into these problems.

**CREATE if not exists Syntax**
```mysql
CREATE TABLE IF NOT EXISTS table_name(
	column1 datatype,
	column2 datatype,
	column3 datatype,
	.....
	columnN datatype,
	PRIMARY KEY ( one or more columns )
)
```
**CREATE if not exists Example**
```mysql
CREATE TABLE IF NOT EXISTS Customers(
	ID INT NOT NULL,
	NAME VARCHAR(20) NOT NULL,
	AGE INT NOT NULL,
	ADDRESS CHAR(25),
	SALARY DECIMAL(18,2),
	PRIMARY KEY (ID)
);
```
If you already have an existing Table and want to clone it. Don't worry there is a way. 

**CREATE & Clone Syntax**
```mysql
CREATE TABLE NEW_TABLE_NAME AS
SELECT [column1]
FROM EXISTING_TABLE_NAME
WHERE CONDITION;
```
**CREATE & Clone Example**
```mysql
CREATE TABLE SALRAY AS
SELECT ID, SALARY
FROM Customers;
```
#### UPDATE
**UPDATE Syntax**
```mysql
UPDATE table_name
SET cloumn1=value1, column2=value2, ...
WHERE condition;
```
**UPDATE Example**
```mysql
UPDATE Customers
SET ContactName='Alfred Schmidt', City='Frankfurt'
WHERE CustomerID=1;
```
**UPDATE multiple Example**
```mysql
UPDATE Customers
SET ContactName='Juan'
WHERE County='Mexico'
```
**!!!WARNING!!! Without the `WHERE` clause, ALL records will be updated!**
**UPDATE all records**
```mysql
UPDATE Customers
SET ContactName='Juan';
```
#### DELETE
**!!!WARNING!!! You should be careful when deleting records in a table! Without the `WHERE` clause, all your recors in the table will be deleted!**

**DELETE Syntax**
```mysql
DELETE FROM table_name WHERE condition;
```
**DELETE Example Syntax**
```mysql
DELETE FROM Customers WHERE CustomerName='Alfreds Futterkiste';
```
**DELETE all Syntax**
```mysql
DELETE FROM table_name;
```
**DELETE all Example**
```mysql
DELETE FROM Customers;
```
**DELETE Table Syntax**
```mysql
DROP TABLE table_name;
```
**DELETE Table Example**
```mysql
DROP TABLE Customers;
```
#### SELECT
**SELECT Syntax**
```mysql
SELECT column1, column2, ... FROM table_name;
```
**SELECT Example**
```mysql
SELECT CustomerName, City From Customers;

```
**SELECT All Syntax**
```mysql
SELECT * FROM table_name;
```
**SELECT All Example**
```mysql
SELECT * FROM Customers;
```

##### SELECT DISTINCT
**`SELECT DISTINCT`** is only used to return distinct (different) values. For example you can ignore duplicates.

**SELECT DISTINCT Syntax**
```mysql
SELECT DISTINCT column1, column2, ... FROM Customers
```
**SELECT DISTINCT Example**
```mysql
SELECT DISTINCT Country FROM Customers;
```
**SELECT DISTINCT COUNT Examples**
```mysql
SELECT Count(DISTINCT Country) FROM Customers;
```
or
```mysql
SELECT Count(*) AS DistinctCountires FROM (SELECT DISTINCT Country FROM Customers);
```
#### JOINs
The **`JOIN`** clause is used to combine rows from two or more tables, based on a related column between them.

There are different types of SQL JOINs

**(INNER) JOIN:** Returns records that have matching values in both tables.

**LEFT (OUTER) JOIN:** Returns all records from the left table and the matched records from the right table.

**RIGHT (OUTER) JOIN:** Returns all records from the right table and the matched records from the left table.

**FULL (OUTER) JOIN:** Returns all records when there is a match in either left or right table.

**INNER JOIN Syntax**
```mysql
SELECT column1, column2, ...
FROM table_name1
INNER JOIN table_name2 ON table_name1.column = table_name2.column;
```
**INNER JOIN Example**
```mysql
SELECT ProductID, ProductName, CategoryName
FROM Products
INNER JOIN Categories ON Products.CategoryID = Categories.CategoryID;
```
**LEFT JOIN Syntax**
The left table is the one that is selected, which here would be called table_name1.
```mysql
SELECT column1, column2, ...
FROM table_name1
LEFT JOIN table_name2 ON table_name1.column = table_name2.column;
```
**LEFT JOIN Examples**
```mysql
SELECT Customers.CustomerName, Orders.OrderID
FROM Customers
LEFT JOIN table_name2 ON Customers.column = Orders.CustomerID;
```
You can also use **`ORDER BY`** or **`GROUP BY`** 
```mysql
SELECT Customers.CustomerName, Orders.OrderID
FROM Customers
LEFT JOIN Orders ON Customers.column = Orders.CustomerID
ORDER BY Customers.CustomerName;
```
**RIGHT JOIN Syntax**
The right table is the one after **`JOIN`**, which here would be called table_name2.
```mysql
SELECT column1, column2, ...
FROM table_name1
RIGHT JOIN table_name2 ON table_name1.column = table_name2.column;
```
**RIGHT JOIN Examples**
```mysql
SELECT Orders.OrderID, Employees.LastName, Employees.FirstName
FROM Orders
RIGHT JOIN Employees ON Orders.column = Employees.ID;
```
You can also use **`ORDER BY`** or **`GROUP BY`** 
```mysql
SELECT Orders.OrderID, Employees.LastName, Employees.FirstName
FROM Orders
RIGHT JOIN Employees ON Orders.column = Employees.ID;
ORDER BY Orders.OrderID;
```
**FULL JOIN Syntax**
**Note: The full join can create large result-sets.**
```mysql
SELECT column1, column2, ...
FROM table_name1
FULL OUTER JOIN table_name2 ON table_name1.column = table_name2.column;
```
**FULL JOIN Examples**
```mysql
SELECT Customers.CustomerName, Order.OrderID
FROM Customers
FULL OUTER JOIN Orders ON Customers.CustomerID = Orders.CustomerID;
```
You can also use **`ORDER BY`** or **`GROUP BY`** or others.
```mysql
SELECT Customers.CustomerName, Order.OrderID
FROM Customers
FULL OUTER JOIN Orders ON Customers.CustomerID = Orders.CustomerID;
ORDER BY Customers.CustomerName;
```
## Extra
#### MIN
**`MIN`** is used to get smallest value of the selected column.
**MIN Syntax**
```mysql
SELECT MIN(column) FROM table_name;
```
**MIN Example**
```mysql
SELECT MIN(Price) FROM Products;
```
#### MAX
**`MAX`** is used to get largest value of the selected column.
**MAX Syntax**
```mysql
SELECT MAX(column) FROM table_name;
```
**MAX Example**
```mysql
SELECT MAX(Price) FROM Products;
```
#### COUNT
**`COUNT`** returns the number of rows that match the condition if there is one.

**COUNT Syntax**
```mysql
SELECT COUNT(column) FROM table_name;
```
**COUNT Example**
```mysql
SELECT COUNT(ProductName) FROM Products;
```
**COUNT All Syntax**
```mysql
SELECT COUNT(*) FROM table_name;
```
**COUNT All Example**
```mysql
SELECT COUNT(*) FROM Products;
```
**COUNT with Condition Syntax**
```mysql
SELECT COUNT(column) FROM table_name WHERE condition;
```
**COUNT with Condition Example**
```mysql
SELECT COUNT(ProductName) FROM Products WHERE Price > 20;
```
**COUNT ignore duplicates Syntax**
```mysql
SELECT COUNT(DISTINCT column) FROM table_name;
```
**COUNT ignore duplicates Example**
```mysql
SELECT COUNT(DISTINCT Price) FROM Products;
```
**COUNT with Alias Syntax**

Alias is used to give the counted column a name
```mysql
SELECT COUNT(column) AS [column_name]
FROM table_name;
```
**COUNT with Alias Example**
```mysql
SELECT COUNT(*) AS [Number of records]
FROM Products;
```
#### GROUP BY
**`GROUP BY`** is used to group rows that have the same values into summary rows, like "find the number of customers in each country". It is often used with aggregate Functions (COUNT(), MAX(), MIN(), ...) to group the result-set by one or more columns.

**GROUP BY Syntax**
```mysql
SELECT column_name
FROM table_name
WHERE condition # Optional
GROUP BY column_name # Optional
ORDER BY column_name; # Optional
```
**GROUP BY Examples**
```mysql
SELECT COUNT(CustomerID), Country
FROM Customers
GROUP BY Country;
```

```mysql
SELECT COUNT(CustomerID), Country
FROM Customers
GROUP BY Country
ORDER BY COUNT(CustomerID) DESC;
```
#### ORDER BY (ASC | DESC)
You can use **`ORDER BY`** to sort the column/s in ascending or descending order.

**ORDER BY Syntax**
```mysql
SELECT column1, column2, ...
FROM Products;
ORDER BY column1, column2, ... ASC|DESC;
```
**ORDER BY Examples**
```mysql
SELECT COUNT(*)
FROM Products;
ORDER BY Price;
```
It will defaultly order ascending so you can leave ASC away. But if you want to get it descending you need to use DESC as in the following example.
```mysql
SELECT COUNT(*)
FROM Products;
ORDER BY Price DESC;
```
You can also sort it by multiple columns.
```mysql
SELECT COUNT(*)
FROM Customers;
ORDER BY Country, CustomerName;
```
But how does that work you think? It is because it first orders by the Country and if some rows have the same Country, it orders them by the CustomerName.
This also works with ASC and DESC as you can see in the following example.
```mysql
SELECT COUNT(*)
FROM Customers;
ORDER BY Country ASC, CustomerName DESC;
```
Here it will first order ascending by the country and if some rows have the same country, it orders them descending by the CustomerName.

---
### Constraints
#### PRIMARY KEY
A Table can only have one **PRIMARY KEY**. A PRIMARY KEY is a constraint that uniquely identifies each record in a table. So it is a unique value that cannot contain NULL values, but it can consist of single or multiple columns.
*A common use of a primary key is the userID.*
#### <u>Example use cases</u>
```mysql
CREATE TABLE Persons (
	ID INT NOT NULL PRIMARY KEY,
	LastName VARCHAR(255) NOT NULL,
	FirstName VARCHAR(255),
	Age INT
);
```

```mysql
CREATE TABLE Persons (
	ID INT NOT NULL,
	LastName VARCHAR(255) NOT NULL,
	FirstName VARCHAR(255),
	Age INT
	PRIMARY KEY (ID)
);
```

```mysql
CREATE TABLE Persons (
	ID INT NOT NULL,
	LastName VARCHAR(255) NOT NULL,
	FirstName VARCHAR(255),
	Age INT
	CONSTRAINT PK_Person PRIMARY KEY (ID,LastName)
);
```
##### <u>ALTER TABLE Examples</u>
```mysql
ALTER TABLE Persons
ADD PRIMARY KEY (ID);
```

```mysql
ALTER TABLE Persons
ADD CONSTRAINT PK_Person PRIMARY KEY (ID,LastName);
```
###### <u>DROP Examples</u>
```mysql
ALTER TABLE Persons
DROP PRIMARY KEY;
```

```mysql
ALTER TABLE Persons
DROP CONSTRAINT PK_Person;
```
#### FOREIGN KEY
A **FOREIGN KEY** constraint is used to prevent acitons that would destroy links between tables. It is a field (or colleciton of fields) in one table, that refers to the ***PRIMARY KEY*** of another table. The table with the primary key is called "the parent table" or "the referenced" and the table with the foreign key is called "the child table".
#### <u>Example use cases</u>
```mysql
CREATE TABLE Orders(
	OrderID INT NOT NULL,
	OrderNumber INT NOT NULL,
	PersonID INT,
	PRIMARY KEY (OrderID),
	FOREIGN KEY (PersonID) REFERENCES Persons(PersonID)
);
```

```mysql
CREATE TABLE Orders(
	OrderID INT NOT NULL,
	OrderNumber INT NOT NULL,
	PersonID INT,
	PRIMARY KEY (OrderID),
	CONSTRAINT FK_PersonOrder FOREIGN KEY (PersonID)
	REFERENCES Persons(PersonID)
);
```
##### <u>ALTER TABLE examples</u>
```mysql
ALTER TABLE Orders
ADD FOREIGN KEY (PersonID) REFERENCES Persons(PersonID);
```

```mysql
ALTER TABLE Orders
ADD CONSTRAINT FK_PersonOrder
FOREIGN KEY Persons(PersonID) REFERENCES Persons(PersonID);
```
###### <u>DROP examples</u>
```mysql
ALTER TABLE Orders
DROP FOREIGN KEY FK_PersonOrder;
```

```mysql
ALTER TABLE Orders
DROP CONSTRAINT FK_PersonOrder;
```
#### Tasks
1. Run make startdb to start the DB in docker. Run make stop db to stop the DB  
2. Connect to the database with psql -h localhost -p 5544 -U forecast (password forecast)  
3. Find how many rows are in weather_records table  
4. Find what distinct cities are in weather_records table  
5. Select data from both cities and weather_records tables using JOIN  
6. Find records where condition was "dry" in all three cities. The output should contain city, timestamp, condition  
7. Find records where condition was "dry" and icon "clear-day". The output should contain city, timestamp, condition, icon  
8. Find records where icon was not in "clear_night", "clear_day". The output should contain city, timestamp, icon  
9. Find a number of cloudy days per city. The output should contain city, num_of_cloudy_days  
10. Find maximum wind speed per city. The output should contain city, max_wind_speed  
11. Order record by the temperature. The output should have city, timestamp, temperature (goes from high to low)

##### Solutions
1. `make startdb` and `make stopdb`
2. `psql -h localhost -p 5544 -U forecast` then enter the password
3. `SELECT COUNT(*) FROM (SELECT DISTINCT * FROM weather_records);`
4. `SELECT city FROM weather_records GROUP BY city;`
5. `SELECT city, icon FROM weather_records INNER JOIN cities ON weather_records.city = cities.name;`
6. `SELECT city, timestamp, condition FROM weather_records WHERE condition='dry';`
7. `SELECT city, timestamp, condition FROM weather_records WHERE condition='dry' AND icon='clear-day';`
8. `SELECT city, timestamp, icon FROM weather_records WHERE icon!='clear-night' AND icon!='clear-day';` or `SELECT city, timestamp, icon FROM weather_records WHERE icon NOT IN ('clear-night', 'clear-day');` 
9. `SELECT city, COUNT(DISTINCT DATE(timestamp)) AS num_of_cloudy_days FROM weather_records WHERE icon='cloudy' GROUP BY city;`
10. `SELECT city, MAX(wind_speed) AS max_wind_speed FROM weather_records WHERE icon='cloudy' GROUP BY city;`
11. `SELECT city, timestamp, temperature FROM weather_records ORDER BY temperature DESC;`
