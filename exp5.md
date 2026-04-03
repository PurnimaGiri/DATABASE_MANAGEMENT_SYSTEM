# Employee Table Queries – Experiment 5 (Aggregate Functions)

-- Question 1: Display total number of employees working in the company
SELECT COUNT(*) AS total_employees 
FROM Employee;

-- Question 2: Display total salary being paid to all employees
SELECT SUM(sal) AS total_salary 
FROM Employee;

-- Question 3: Display maximum salary from employee table
SELECT MAX(sal) AS max_salary 
FROM Employee;

-- Question 4: Display minimum salary from employee table
SELECT MIN(sal) AS min_salary 
FROM Employee;

-- Question 5: Display average salary from employee table
SELECT AVG(sal) AS avg_salary 
FROM Employee;

-- Question 6: Display maximum salary being paid to clerk
SELECT MAX(sal) AS max_clerk_salary 
FROM Employee 
WHERE job = 'CLERK';

-- Question 7: Display maximum salary being paid in dept no 20
SELECT MAX(sal) AS max_salary_dept20 
FROM Employee 
WHERE DeptNo = 20;

-- Question 8: Display minimum salary paid to any salesman
SELECT MIN(sal) AS min_salesman_salary 
FROM Employee 
WHERE job = 'SALESMAN';

-- Question 9: Display average salary drawn by managers
SELECT AVG(sal) AS avg_manager_salary 
FROM Employee 
WHERE job = 'MANAGER';

-- Question 10: Display total salary drawn by analyst working in dept no 40
SELECT SUM(sal) AS total_analyst_salary 
FROM Employee 
WHERE job = 'ANALYST' AND DeptNo = 40;

-- Question 11: Display employee names in uppercase
SELECT UPPER(ename) AS upper_name 
FROM Employee;

-- Question 12: Display employee names in lowercase
SELECT LOWER(ename) AS lower_name 
FROM Employee;

-- Question 13: Display employee names in proper case
SELECT CONCAT(UPPER(LEFT(ename,1)), LOWER(SUBSTRING(ename,2))) AS proper_name 
FROM Employee;

-- Question 14: Display length of your name
SELECT LENGTH('Purnima') AS name_length;

-- Question 15: Display length of all employee names
SELECT ename, LENGTH(ename) AS name_length 
FROM Employee;
