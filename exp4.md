# Employee Table Queries – Experiment 4 (Conditions & Expressions)

-- Question 1: Display employees who joined before 30-June-1980 or after 31-Dec-1981
SELECT ename, hiredate 
FROM Employee 
WHERE hiredate < '1980-06-30' 
OR hiredate > '1981-12-31';

-- Question 2: Display names of employees whose second letter is 'A'
SELECT ename 
FROM Employee 
WHERE ename LIKE '_A%';

-- Question 3: Display names of employees whose name is exactly five characters long
SELECT ename 
FROM Employee 
WHERE LENGTH(ename) = 5;

-- Question 4: Display names of employees whose second letter is 'A'
SELECT ename 
FROM Employee 
WHERE ename LIKE '_A%';

-- Question 5: Display names of employees who are not salesman, clerk or analyst
SELECT ename 
FROM Employee 
WHERE job NOT IN ('SALESMAN','CLERK','ANALYST');

-- Question 6: Display employee name with annual salary (highest first)
SELECT ename, (sal*12) AS annual_salary 
FROM Employee 
ORDER BY annual_salary DESC;

-- Question 7: Display name, sal, hra (15%), da (10%), pf (5%), total salary
SELECT ename, 
       sal,
       sal*0.15 AS hra,
       sal*0.10 AS da,
       sal*0.05 AS pf,
       (sal + sal*0.15 + sal*0.10 - sal*0.05) AS total_salary
FROM Employee;

-- Question 8: Increase salary by 10% for employees not getting commission
UPDATE Employee 
SET sal = sal + (sal * 0.10)
WHERE comm IS NULL OR comm = 0;

-- Question 9: Display employees whose salary becomes more than 3000 after 20% increment
SELECT ename 
FROM Employee 
WHERE sal * 1.2 > 3000;

-- Question 10: Display employees whose salary has at least 3 digits
SELECT ename, sal 
FROM Employee 
WHERE sal >= 100;
