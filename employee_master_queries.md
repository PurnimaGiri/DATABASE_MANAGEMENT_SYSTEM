\# Employee and Department SQL Queries (MySQL / XAMPP)



\## Step 1: Create DEPARTMENT Table



```sql

CREATE TABLE Department (

&nbsp;   DeptNo INT(2) PRIMARY KEY,

&nbsp;   Dname VARCHAR(15) NOT NULL

);

```



---



\## Step 2: Create EMPLOYEE Table



```sql

CREATE TABLE Employee (

&nbsp;   EmpNo INT(4) PRIMARY KEY,

&nbsp;   Ename VARCHAR(20) NOT NULL,

&nbsp;   Job VARCHAR(20),

&nbsp;   Mgr INT(4),

&nbsp;   HireDate DATE,

&nbsp;   Sal DECIMAL(10,2),

&nbsp;   Comm DECIMAL(7,2),

&nbsp;   DeptNo INT(2),

&nbsp;   FOREIGN KEY (DeptNo) REFERENCES Department(DeptNo)

);

```



---



\## Step 3: Insert values into DEPARTMENT Table



```sql

INSERT INTO Department VALUES (10, 'RESEARCH');

INSERT INTO Department VALUES (20, 'ACCOUNTING');

INSERT INTO Department VALUES (30, 'SALES');

INSERT INTO Department VALUES (40, 'OPERATIONS');

```



---



\## Step 4: Insert values into EMPLOYEE Table



(MySQL date format must be YYYY-MM-DD)



```sql

INSERT INTO Employee VALUES (7369, 'SMITH', 'CLERK', 7902, '1980-12-17', 800, NULL, 20);

INSERT INTO Employee VALUES (7499, 'ALLEN', 'SALESMAN', 7698, '1981-02-20', 1600, 300, 30);

INSERT INTO Employee VALUES (7521, 'WARD', 'SALESMAN', 7698, '1981-02-22', 1250, 300, 30);

INSERT INTO Employee VALUES (7566, 'JONES', 'MANAGER', 7839, '1981-04-02', 2975, NULL, 20);

INSERT INTO Employee VALUES (7654, 'MARTIN', 'SALESMAN', 7698, '1981-09-28', 1250, 1400, 30);

INSERT INTO Employee VALUES (7698, 'BLAKE', 'MANAGER', 7839, '1981-05-01', 2850, NULL, 30);

INSERT INTO Employee VALUES (7782, 'CLARK', 'MANAGER', 7839, '1981-06-09', 2450, NULL, 20);

INSERT INTO Employee VALUES (7788, 'SCOTT', 'ANALYST', 7566, '1982-12-09', 3000, NULL, 40);

INSERT INTO Employee VALUES (7839, 'KING', 'PRESIDENT', NULL, '1981-11-17', 5000, NULL, 20);

INSERT INTO Employee VALUES (7844, 'TURNER', 'SALESMAN', 7698, '1981-09-08', 1500, 0, 30);

INSERT INTO Employee VALUES (7876, 'ADAMS', 'CLERK', 7788, '1983-01-12', 1100, NULL, 20);

INSERT INTO Employee VALUES (7900, 'JAMES', 'CLERK', 7698, '1981-12-03', 950, NULL, 30);

INSERT INTO Employee VALUES (7902, 'FORD', 'ANALYST', 7566, '1981-12-03', 3000, NULL, 20);

INSERT INTO Employee VALUES (7934, 'MILLER', 'CLERK', 7782, '1982-01-23', 1300, NULL, 10);

```



---



\## Step 5: Create Employee\_Master table from Employee



```sql

CREATE TABLE Employee\_Master AS

SELECT \*

FROM Employee;

```



---



\## Step 6: Delete records from Employee\_Master where DeptNo = 10



```sql

DELETE FROM Employee\_Master

WHERE DeptNo = 10;

```



---



\## Step 7: Increase salary by 10% for DeptNo = 20



```sql

UPDATE Employee\_Master

SET Sal = Sal + (Sal \* 0.10)

WHERE DeptNo = 20;

```



---



\## Step 8: Alter SAL column to DECIMAL(10,2)



```sql

ALTER TABLE Employee\_Master

MODIFY Sal DECIMAL(10,2);

```



---



\## Step 9: Drop Employee\_Master table



```sql

DROP TABLE Employee\_Master;

```



---



\## Compatible with:

\- XAMPP

\- MySQL

\- MariaDB

