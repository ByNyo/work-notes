## Tables
#### CREATE
**Create Syntax**
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
**Create Example**
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
**Create if not exists Syntax**
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
**Create if not exists Example**
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
**Create & Clone Syntax**
```mysql
CREATE TABLE NEW_TABLE_NAME AS
SELECT [column1]
FROM EXISTING_TABLE_NAME
WHERE CONDITION;
```
**Create & Clone Example**
```mysql
CREATE TABLE SALRAY AS
SELECT ID, SALARY
FROM Customers;
```
#### UPDATE
**Update Syntax**
```mysql
UPDATE table_name
SET cloumn1=value1, column2=value2, ...
WHERE condition;
```
**Update Example**
```mysql
UPDATE Customers
SET ContactName='Alfred Schmidt', City='Frankfurt'
WHERE CustomerID=1;
```
**Update multiple Example**
```mysql
UPDATE Customers
SET ContactName='Juan'
WHERE County='Mexico'
```
==!!!WARNING!!! Without the ==**`WHERE`**==clause, ALL records will be updated!==
**Update all records**
```mysql
UPDATE Customers
SET ContactName='Juan';
```
#### DELETE
==!!!WARNING!!! You should be careful when deleting records in a table! Without the ==**`WHERE`**==clause, all your recors in the table will be deleted!==
**Delete Syntax**
```mysql
DELETE FROM table_name WHERE condition;
```
**Example Syntax**
```mysql
DELETE FROM Customers WHERE CustomerName='Alfreds Futterkiste';
```
#### SELECT

#### JOIN

## Modifiers
#### MAX

#### COUNT

#### GROUP BY

#### ORDER BY (ASC | DESC)

---
### Constraints | Extra
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
3. `SELECT COUNT(*) FROM weather_records;`
5. `SELECT city FROM weather_records GROUP BY city;`
6. `SELECT city, icon FROM weather_records INNER JOIN cities ON weather_records.city = cities.name;`
7. `SELECT * FROM weather_records WHERE condition='dry';`
8. `SELECT * FROM weather_records WHERE condition='dry' AND icon='clear-day';`
9. `SELECT * FROM weather_records WHERE icon!='clear-night' AND icon!='clear-day';`
10. `SELECT city, COUNT(*) FROM weather_records WHERE icon='cloudy' GROUP BY city;`
11. `SELECT city, MAX(wind_speed) FROM weather_records WHERE icon='cloudy' GROUP BY city;`
12. `SELECT city, timestamp, temperature FROM weather_records ORDER BY temperature DESC;`
