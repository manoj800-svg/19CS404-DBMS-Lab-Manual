# Experiment 6: PL/SQL – Variables, Control Structures and Loops

## AIM
To write and execute simple PL/SQL programs using variables, loops, and conditional statements.


## THEORY

PL/SQL, which stands for Procedural Language extensions to the Structured Query Language (SQL). It is a combination of SQL along with the procedural features of programming languages.

**Syntax:**
```sql
DECLARE 
   <declarations section> 
BEGIN 
   <executable command(s)>
EXCEPTION 
   <exception handling> 
END;
```

### Basic Components of PL/SQL Block:
- DECLARE: Section to declare variables and constants.
- BEGIN: The execution section that contains PL/SQL statements.
- EXCEPTION: Handles errors or exceptions that occur in the program.
- END: Marks the end of the PL/SQL block.

# PL/SQL Programs – Steps and Expected Output

## 1. Write a PL/SQL program to find the Greatest of Two Numbers

### Steps:
- Declare two numeric variables and initialize them.
- Use an `IF` statement to compare the values.
- Display the greater number using `DBMS_OUTPUT.PUT_LINE`.
### Program: 
![Screenshot 2025-05-19 143741](https://github.com/user-attachments/assets/4a3fc35b-8796-48c9-ba13-4c3e380bff57)


**Expected Output:**  
Greater number is: 80

---

## 2. Write a PL/SQL program to Calculate Sum of First N Natural Numbers

### Steps:
- Declare a variable `n` and assign a value (e.g., 10).
- Initialize a `sum` variable to 0.
- Use a `WHILE` loop to iterate from 1 to `n`, adding each number to the sum.
- Display the result using `DBMS_OUTPUT.PUT_LINE`.
### Program: 
![Screenshot 2025-05-19 143820](https://github.com/user-attachments/assets/b98231b8-a471-4deb-bbcc-392c99274180)


**Expected Output:**  
Sum of first 10 natural numbers is: 55

---

## 3. Write a PL/SQL program to generate Fibonacci series

### Steps:
- Declare the variable `n` to indicate how many terms to generate.
- Initialize the first two Fibonacci numbers (0 and 1).
- Use a loop to generate the next terms using the formula `c = a + b`.
- Print each term in the series.
  
### Program: 
![Screenshot 2025-05-19 143920](https://github.com/user-attachments/assets/c6d77a45-522f-44fe-804a-a26e7db8ea51)
![Screenshot 2025-05-19 143940](https://github.com/user-attachments/assets/0114f208-a80e-43d1-96bd-70994b6b1355)



**Expected Output:**  
n = 7  
Fibonacci sequence: 0, 1, 1, 2, 3, 5, 8

---

## 4. Write a PL/SQL Program to display the number in Reverse Order

### Steps:
- Declare a variable `n` and assign a value (e.g., 1535).
- Use a loop to extract each digit using modulo and reverse the number.
- Display the reversed number.

### Program: 
![Screenshot 2025-05-19 144029](https://github.com/user-attachments/assets/af1d4508-8f9e-4e8b-b0c1-b95af0b77267)
![Screenshot 2025-05-19 144042](https://github.com/user-attachments/assets/08588fb1-a4a5-431f-90ea-d7949147121b)



**Expected Output:**  
n = 1535  
Reversed number is 5351

---

## 5. Write a PL/SQL program to find the largest of three numbers

### Steps:
- Declare three numeric variables `a`, `b`, and `c`.
- Use nested `IF-ELSIF-ELSE` conditions to find the largest among the three.
- Display the largest number.
  
### Program: 
![Screenshot 2025-05-19 144112](https://github.com/user-attachments/assets/eb34cd1c-b5af-4163-9ed0-506c8a5a8797)
![Screenshot 2025-05-19 144125](https://github.com/user-attachments/assets/268facae-ed20-4d6e-9a8f-d70660b7bd19)



**Expected Output:**  
a = 10, b = 9, c = 15  
Largest of three number is 15

## RESULT
Thus, the PL/SQL programs using variables, conditionals, and loops were executed successfully.
