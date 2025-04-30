# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**
--
-- Write the SQL query that accomplishes the grouping of data by age intervals using the expression (age/5)5, calculates the minimum age for each group, and excludes groups where the minimum age is not less than 25.

```sql
-- SELECT (age/5)*5 AS age_group,MIN(age)
FROM customer1
GROUP BY age_group
HAVING MIN(age) < 25;
```

**Output:**

![image](https://github.com/user-attachments/assets/81a8bbe4-31f3-48b4-b33f-2ff09f16bc52)


**Question 2**
---
-- Write a SQL Query to find how many medications are prescribed for each patient?

```sql
-- SELECT PatientID ,count(Medications) AS  AvgMedications
FROM MedicalRecords 
group by PatientID
```

**Output:**

![image](https://github.com/user-attachments/assets/03a65203-c476-48de-9e10-793589ef3ebf)


**Question 3**
---
-- What is the average duration of insurance coverage for patients covered by each insurance company?

```sql
-- SELECT InsuranceCompany ,AVG(EndDate - StartDate) as AvgCoverageDurationDays
FROM Insurance
GROUP BY InsuranceCompany;
```

**Output:**

![image](https://github.com/user-attachments/assets/1bb9fcda-b375-4a1b-a2e1-bbd5def94ee2)


**Question 4**
---
-- Write a SQL query to determine the number of customers who received at least one grade for their activity.

```sql
-- SELECT count( customer_id) as COUNT
FROM customer
Where grade is NOT NULL AND grade>0;
```

**Output:**

![image](https://github.com/user-attachments/assets/9a0017ec-3ece-4138-9847-620b20e23a74)

**Question 5**
---
-- Write a SQL query to find the average length of email addresses (in characters):
```sql
-- SELECT AVG(Length(email)) as avg_email_length
FROM customer
```

**Output:**

![image](https://github.com/user-attachments/assets/76cfc29c-c4d1-4774-be74-9c3111e1eae7)


**Question 6**
---
-- Write a SQL query to calculate total purchase amount of all orders. Return total purchase amount.

```sql
-- SELECT sum(purch_amt) AS TOTAL
FROM orders
```

**Output:**

![image](https://github.com/user-attachments/assets/52c8e0c5-5287-4fd2-9e5a-78b4dcd0a06d)


**Question 7**
---
-- Write a SQL query to find how many employees have an income greater than 50K?

```sql
-- SELECT count(id) AS employees_count
FROM employee
where income > 50000
```

**Output:**

![image](https://github.com/user-attachments/assets/d14b4114-50ac-4223-a81c-51dbbccc8f77)


**Question 8**
---
-- Write the SQL query that achieves the grouping of data by occupation, calculates the minimum work hours for each occupation, and excludes occupations where the minimum work hour is not greater than 8.

```sql
-- SELECT occupation ,MIN(workhour)
FROM employee1
GROUP BY occupation
HAVING MIN(workhour)>8
```

**Output:**

![image](https://github.com/user-attachments/assets/7b6cf3c5-5727-4903-a2d7-9b13ac0293ac)


**Question 9**
---
-- Write the SQL query that accomplishes the grouping of data by age intervals using the expression (age/5)5, calculates the minimum age for each group, and excludes groups where the minimum age is not less than 25.

```sql
-- SELECT (age/5)*5 AS age_group,MIN(age)
FROM customer1
GROUP BY age_group
HAVING MIN(age) < 25;
```

**Output:**

![image](https://github.com/user-attachments/assets/dc20456f-6a44-4108-8ad7-7132a544baba)


**Question 10**
---
-- Write the SQL query that achieves the grouping of data by city, calculates the average income for each city, and includes only those cities where the average income is greater than 500,000.

```sql
-- SELECT city,AVG(income) 
FROM employee
GROUP BY city
HAVING AVG(income) > 500000;
```

**Output:**

![image](https://github.com/user-attachments/assets/463d7330-fbf5-43aa-9e1c-71478211efd0)



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
