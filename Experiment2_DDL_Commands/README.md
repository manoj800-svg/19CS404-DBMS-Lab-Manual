# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
--
-- Insert the below data into the Employee table, allowing the Department and Salary columns to take their default values.

```sql
-- INSERT into Employee(EmployeeID, Name, Position)
VALUES(4,"Emily White","Analyst");
```

**Output:**

![image](https://github.com/user-attachments/assets/bd08beb9-9dcf-486a-aef0-01b9071d2291)


**Question 2**
---
-- Insert all products from Discontinued_products into Products.

Table attributes are ProductID, ProductName, Price, Stock

```sql
-- INSERT into products(productid,productname,price,stock)
SELECT productid,productname,price,stock from discontinued_products;
```

**Output:**

![image](https://github.com/user-attachments/assets/5e7628fe-f162-4deb-8731-fde92b089501)


**Question 3**
---
-- Create a table named Locations with the following columns:

LocationID as INTEGER
LocationName as TEXT
Address as TEXT

```sql
-- CREATE TABLE Locations(
LocationID INTEGER,
LocationName TEXT,
Address TEXT); 
```

**Output:**

![image](https://github.com/user-attachments/assets/d6d07ec5-9c71-4ebe-a2b2-3528ff690790)


**Question 4**
---
-- Write a SQL Query  to Rename attribute "name" to "first_name"  and add mobilenumber as number ,DOB as Date,State as varchar(30) in the table Companies. 

```sql
--ALTER TABLE Companies
RENAME name TO first_name;
ALTER TABLE Companies
ADD mobilenumber number;
ALTER TABLE Companies
ADD DOB Date; 
ALTER TABLE Companies
ADD State varchar(30);
```

**Output:**

![image](https://github.com/user-attachments/assets/3b3114e9-606f-498b-8356-537eb85eee66)


**Question 5**
---
-- Create a table named Bonuses with the following constraints:
BonusID as INTEGER should be the primary key.
EmployeeID as INTEGER should be a foreign key referencing Employees(EmployeeID).
BonusAmount as REAL should be greater than 0.
BonusDate as DATE.
Reason as TEXT should not be NULL.
```sql
-- CREATE TABLE Bonuses(
BonusID INTEGER PRIMARY KEY,
EmployeeID INTERGER,
BonusAmount REAL CHECK(BonusAmount > 0),
BonusDate DATE, 
Reason TEXT NOT NULL,
FOREIGN KEY(EmployeeID) REFERENCES Employees(EmployeeID)); 
```

**Output:**
![image](https://github.com/user-attachments/assets/0417b2be-f456-44ce-9623-941c65fd2fc4)


**Question 6**
---
--Insert the following employees into the Employee table:

```sql
-- INSERT INTO Employee(EmployeeID, Name, Position, Department, Salary)
VALUES(2,"John Smith", "Developer", "IT", 75000),(3,"Anna Bell","Designer","Marketing",68000);
```

**Output:**
![image](https://github.com/user-attachments/assets/c379535a-742d-4e78-bb59-03c7bdcbe630)


**Question 7**
---
-- Create a table named ProjectAssignments with the following constraints:
AssignmentID as INTEGER should be the primary key.
EmployeeID as INTEGER should be a foreign key referencing Employees(EmployeeID).
ProjectID as INTEGER should be a foreign key referencing Projects(ProjectID).
AssignmentDate as DATE should be NOT NULL.

```sql
-- CREATE TABLE ProjectAssignments(
AssignmentID INTEGER PRIMARY KEY,
EmployeeID INTEGER,
ProjectID INTEGER,
AssignmentDate DATE NOT NULL,
FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID),
FOREIGN KEY (ProjectID) REFERENCES Projects(ProjectID));
```

**Output:**
![image](https://github.com/user-attachments/assets/6b8ce0f9-ec43-417c-94a5-71f46ca889d5)


**Question 8**
---
-- Create a new table named item with the following specifications and constraints:
item_id as TEXT and as primary key.
item_desc as TEXT.
rate as INTEGER.
icom_id as TEXT with a length of 4.
icom_id is a foreign key referencing com_id in the company table.
The foreign key should set NULL on updates and deletes.
item_desc and rate should not accept NULL.

```sql
-- CREATE TABLE item(
item_id TEXT PRIMARY KEY ,
item_desc TEXT NOT NULL ,
rate INTEGER NOT NULL,
icom_id TEXT CHECK(LENGTH(icom_id) = 4),
FOREIGN KEY (icom_id) REFERENCES company(com_id)
ON UPDATE SET NULL
ON DELETE SET NULL);
```

**Output:**
![image](https://github.com/user-attachments/assets/afa6297a-6262-4743-a25a-57bf4e0b06e2)


**Question 9**
---
-- Create a new table named contacts with the following specifications:
contact_id as INTEGER and primary key.
first_name as TEXT and not NULL.
last_name as TEXT and not NULL.
email as TEXT.
phone as TEXT and not NULL with a check constraint to ensure the length of phone is at least 10 characters.

```sql
-- CREATE TABLE contacts( 
contact_id INTEGER PRIMARY KEY,
first_name TEXT NOT NULL,
last_name TEXT NOT NULL,
email TEXT,
phone TEXT NOT NULL CHECK(LENGTH(phone) >=10));
```

**Output:**

![image](https://github.com/user-attachments/assets/faec38b6-2085-4cd5-85a8-ea3c65ca2f50)


**Question 10**
---
--Create a table named Orders with the following columns:

OrderID as INTEGER
OrderDate as TEXT
CustomerID as INTEGER
```sql
-- CREATE TABLE Orders(
OrderID INTEGER,
OrderDate TEXT,
CustomerID INTEGER);
```

**Output:**

![image](https://github.com/user-attachments/assets/749f30bc-ec11-4b57-9312-60431b85a1da)



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
