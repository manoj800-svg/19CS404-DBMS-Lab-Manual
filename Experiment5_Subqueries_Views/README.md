# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**
--
-- From the following tables write a SQL query to find the order values greater than the average order value of 10th October 2012. Return ord_no, purch_amt, ord_date, customer_id, salesman_id.

Note: date should be yyyy-mm-dd format

```sql
SELECT ord_no, purch_amt, ord_date, customer_id, salesman_id
FROM orders
WHERE purch_amt > (
    SELECT AVG(purch_amt)
    FROM orders
    WHERE ord_date = '2012-10-10'
);

```

**Output:**

![image](https://github.com/user-attachments/assets/c4fe8e8c-5bff-4af2-81df-18058c70008a)


**Question 2**
---
-- Write a SQL query to retrieve all columns from the CUSTOMERS table for customers whose Address as Delhi and age below 30

Sample table: CUSTOMERS

```sql
SELECT *FROM CUSTOMERS
GROUP BY ID
HAVING ADDRESS= 'Delhi' and AGE < 30 ;
```

**Output:**

![image](https://github.com/user-attachments/assets/9f908671-1ed0-4d27-b539-1604114dc2d8)


**Question 3**
---
Write a SQL query to Retrieve the names of customers who have a phone number that is not shared with any other customer.

SAMPLE TABLE: customer

```sql
SELECT name
FROM customer
WHERE phone IN (
    SELECT phone
    FROM customer
    GROUP BY phone
    HAVING COUNT(*) = 1
);

```

**Output:**

![image](https://github.com/user-attachments/assets/e0f632e9-d1b9-4b3a-9439-72993d10953c)


**Question 4**
---
From the following tables, write a SQL query to find all the orders generated in New York city. Return ord_no, purch_amt, ord_date, customer_id and salesman_id.

```sql
SELECT o.ord_no, o.purch_amt, o.ord_date, o.customer_id, o.salesman_id
FROM orders o
JOIN salesman s ON o.salesman_id = s.salesman_id
WHERE s.city = 'New York';

```

**Output:**
![image](https://github.com/user-attachments/assets/3d8a5da5-2d68-4c72-85f2-3678fde1cd4b)


**Question 5**
---
Write a SQL query to retrieve all columns from the CUSTOMERS table for customers whose Address as Delhi

Sample table: CUSTOMERS

```sql
SELECT * FROM CUSTOMERS
GROUP BY ID
HAVING ADDRESS='Delhi'
```

**Output:**
![image](https://github.com/user-attachments/assets/2f35f3c6-f25c-46ab-b763-3cf1432017f9)


**Question 6**
---
Write a SQL query to Retrieve the medications with dosages equal to the lowest dosage

Table Name: Medications (attributes: medication_id, medication_name, dosage)

```sql
SELECT medication_id as medic ,medication_name,dosage
FROM Medications
WHERE dosage= (
SELECT min(dosage)
FROM Medications);
```

**Output:**

![image](https://github.com/user-attachments/assets/4dc1c8d8-eba9-4c53-addc-b3e70b491322)


**Question 7**
---
Write a query to display all the customers whose ID is the difference between the salesperson ID of Mc Lyon and 2001.
```sql
SELECT *FROM customer
WHERE customer_id = (
    SELECT salesman_id - 2001
    FROM salesman
    WHERE name = 'Mc Lyon'
);

```

**Output:**

![image](https://github.com/user-attachments/assets/9f54a436-66b6-4dcf-b4a7-e4605d2af36f)


**Question 8**
---
From the following tables, write a SQL query to determine the commission of the salespeople in Paris. Return commission.
```sql
SELECT commission from salesman
WHERE salesman_id IN(
SELECT salesman_id
from customer
where city = 'Paris');


**Output:**
![image](https://github.com/user-attachments/assets/cd862613-1971-4ef8-b20a-b6201ffb0acb)


**Question 9**
---
Write a SQL query to Find employees who have an age less than the average age of employees with incomes over 1 million

```sql
SELECT *from Employee
WHERE age < (
SELECT avg(age) from Employee 
WHERE income > 1000000);
```

**Output:**

![image](https://github.com/user-attachments/assets/3588d5da-cbc1-4381-a5a5-d93609340797)


**Question 10**
---
Write a SQL query that retrieves the names of students and their corresponding grades, where the grade is equal to the minimum grade achieved in each subject.

```sql
SELECT student_name,grade
from GRADES
WHERE grade = (
select min(grade) 
from GRADES as g 
where g.subject = GRADES.subject);
```

**Output:**

![image](https://github.com/user-attachments/assets/5fccc365-32fd-40d8-a8e4-1807075c6269)



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
