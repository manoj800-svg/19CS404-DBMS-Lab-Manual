# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
--
--Write a SQL statement to Update the reorder level to 20 where the quantity in stock is less than 10 and product category is 'Snacks' in the products table.

Products table

---------------
product_id
product_name
category
cost_price
sell_price
reorder_lvl
quantity
supplier_id


```sql
-- UPDATE Products
SET reorder_lvl = 20 
WHERE quantity < 10 and category='Snacks'
```

**Output:**
![image](https://github.com/user-attachments/assets/107600e5-a8a8-4360-b77d-113141e67e54)


**Question 2**
---
--Update the 'Selling_Price' to add 10% extra margin for all products supplied by the supplier with id 6.

PRODUCTS TABLE

name               type
-----------------  ---------------
product_id         INT
product_name       VARCHAR(100)
category           VARCHAR(50)
cost_price         DECIMAL(10,2)
sell_price         DECIMAL(10,2)
reorder_lvl        INT
quantity           INT
supplier_id        INT

```sql
-- UPDATE products
SET sell_Price =CAST((sell_price * 1.10)as int)
where supplier_id= 6;
```

**Output:**
![image](https://github.com/user-attachments/assets/3529a1e7-002b-4ead-a8d6-96f0735bd4a0)

**Question 3**
---
--Write a SQL statement to Increase the salary by 500 and email as 'updated' for employees with job ID 'SA_REP' and commission percentage greater than 0.15

Employees table

---------------
employee_id
first_name
last_name
email
phone_number
hire_date
job_id
salary
commission_pct
manager_id
department_id

```sql
-- UPDATE Employees
SET salary=salary+500 , email ='updated' 
WHERE job_id ='SA_REP' and commission_pct>0.15;
```

**Output:**
![image](https://github.com/user-attachments/assets/8f12e5a2-0cfa-45fa-9b3a-ad5d728a7627)


**Question 4**
---
-- Write a SQL statement to Change the category to 'Household' where product name contains 'Detergent' in the products table.

Products Table 

name          type       
----------    ---------- 
product_id     INT PRIMARY KEY        
product_name   VARCHAR(10) 
category       VARCHAR(50) 
cost_price     DECIMAL(10) 
sell_price     DECIMAL(10) 
reorder_lvl    INT        
quantity       INT        
supplier_id    INT         
```sql
-- UPDATE products
set category ='Household'
WHERE product_name LIKE '%Detergent%';
```

**Output:**

![image](https://github.com/user-attachments/assets/3bfa1a7f-f617-414b-ae6f-8a85014f5a9c)


**Question 5**
---
-- Write a SQL statement to Increase the selling price by 15% in the products table where quantity in stock is less than 50 and supplier ID is 10.

```sql
-- UPDATE Products
SET sell_price = sell_price*1.15
WHERE quantity < 50 and supplier_id =10
```

**Output:**

![image](https://github.com/user-attachments/assets/7e3b2a52-c704-4e1c-aadd-a265e7871c01)


**Question 6**
---
-- Write a SQL query to Delete customers from 'customer' table where 'OPENING_AMT' is between 4000 and 6000.

```sql
-- DELETE FROM Customer
WHERE OPENING_AMT between 4000 and 6000;
```

**Output:**

![image](https://github.com/user-attachments/assets/64fba8a1-369b-45cc-9faa-caf48108e4af)


**Question 7**
---
-- Write a SQL query to Delete customers from 'customer' table where 'GRADE' is exactly 2.

```sql
-- DELETE FROM customer 
Where GRADE = 2;
```

**Output:**

![image](https://github.com/user-attachments/assets/3cf68a31-ac8e-4e1a-8387-39d848a7e61f)


**Question 8**
---
-- Write a SQL query to Delete a Specific Surgery whose ID is 3 or surgeon ID is 4.

```sql
-- DELETE FROM Surgeries
WHERE surgery_id =3 or surgeon_id=4;
```

**Output:**

![image](https://github.com/user-attachments/assets/59baee7f-fd94-4ebf-8d31-ba08f0b40146)


**Question 9**
---
-- Write a SQL query to Delete a Specific Surgery whose ID is 3

```sql
-- DELETE FROM Surgeries
WHERE surgery_id =3;
```

**Output:**

![image](https://github.com/user-attachments/assets/64f63b6f-de3e-4b23-ba51-d6ce8f71ceac)


**Question 10**
---
-- Write a SQL query to Delete customers from 'customer' table where 'CUST_NAME' has exactly 6 characters.

```sql
-- DELETE FROM Customer
WHERE length(CUST_NAME )=6;
```

**Output:**

![image](https://github.com/user-attachments/assets/8bdc9392-a659-437b-9e14-033f0dec011f)


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
