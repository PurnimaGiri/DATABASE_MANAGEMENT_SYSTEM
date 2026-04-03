# Employee Table Queries – Experiment 6 (Date & Special Functions)

-- Question 1: Display empno, ename, deptno with department name instead of number
SELECT e.empno, e.ename, d.dname 
FROM Employee e
JOIN Department d ON e.DeptNo = d.DeptNo;

-- Question 2: Display your age in days
SELECT DATEDIFF(CURDATE(), '2005-01-01') AS age_in_days;

-- Question 3: Display your age in months
SELECT TIMESTAMPDIFF(MONTH, '2005-01-01', CURDATE()) AS age_in_months;

-- Question 4: Display current date in format (15th August Friday 1997 style)
SELECT DATE_FORMAT(CURDATE(), '%D %M %W %Y') AS formatted_date;

-- Question 5: Display employee name with joining details
SELECT CONCAT(ename, ' has joined the company on ', 
              DATE_FORMAT(hiredate, '%W %D %M %Y')) AS joining_info
FROM Employee;

-- Question 6: Example: Scott joining format
SELECT CONCAT('Scott has joined the company on ', 
              DATE_FORMAT(hiredate, '%W %D %M %Y')) 
FROM Employee 
WHERE ename = 'SCOTT';

-- Question 7: Find nearest Saturday after current date
SELECT DATE_ADD(CURDATE(), INTERVAL (7 - DAYOFWEEK(CURDATE())) DAY) AS next_saturday;

-- Question 8: Display current time
SELECT CURTIME() AS current_time;

-- Question 9: Display date three months before current date
SELECT DATE_SUB(CURDATE(), INTERVAL 3 MONTH) AS three_months_before;

-- Question 10: Display employees who joined in December
SELECT ename, hiredate 
FROM Employee 
WHERE MONTH(hiredate) = 12;

-- Question 11: Display employees where first 2 digits of hiredate equals last 2 digits of salary
SELECT ename, hiredate, sal
FROM Employee
WHERE LEFT(YEAR(hiredate),2) = RIGHT(sal,2);

-- Question 12: Display employees where 10% of salary equals year of joining (last 2 digits)
SELECT ename, sal, hiredate
FROM Employee
WHERE (sal * 0.10) = RIGHT(YEAR(hiredate),2);

-- Question 13: Display employees who joined before 15th of any month
SELECT ename, hiredate
FROM Employee
WHERE DAY(hiredate) < 15;

-- Question 14: Display employees who joined before 15th day of month
SELECT ename, hiredate
FROM Employee
WHERE DAY(hiredate) < 15;

-- Question 15: Display employees whose joining date day equals deptno
SELECT ename, hiredate, deptno
FROM Employee
WHERE DAY(hiredate) = deptno;
