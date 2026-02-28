<h1 align="center">Experiment 7</h1>

## AIM 

To perform SQL queries using aggregate functions, date functions, grouping, formatting, and matrix (pivot-style) queries on the EMP table
---

## Queries:

### Question 1
Compute the number of days remaining in this year

```sql
SELECT 
DATEDIFF(LAST_DAY(CONCAT(YEAR(CURDATE()),'-12-01')), CURDATE()) 
AS Days_Remaining;
```

---

### Question 2
Find the highest and lowest salaries and the difference between them

```sql
SELECT 
MAX(sal) AS Highest_Salary,
MIN(sal) AS Lowest_Salary,
MAX(sal) - MIN(sal) AS Salary_Difference
FROM emp;
```

---

### Question 3
List employees whose commission is greater than 25% of their salary

```sql
SELECT empno, ename, sal, comm
FROM emp
WHERE comm > 0.25 * sal;
```

---

### Question 4
Display salary in dollar format

```sql
SELECT ename, 
CONCAT('$', FORMAT(sal,2)) AS Salary_In_Dollar
FROM emp;
```

---

### Question 5
Matrix query to display job, salary based on department number, and total salary

```sql
SELECT job,
SUM(CASE WHEN deptno = 10 THEN sal ELSE 0 END) AS Dept10,
SUM(CASE WHEN deptno = 20 THEN sal ELSE 0 END) AS Dept20,
SUM(CASE WHEN deptno = 30 THEN sal ELSE 0 END) AS Dept30,
SUM(sal) AS Total_Salary
FROM emp
GROUP BY job;
```

---

### Question 6
Display total employees and number hired in 1980, 1981, 1982, 1983

```sql
SELECT 
COUNT(*) AS Total_Employees,
SUM(YEAR(hiredate)=1980) AS Hired_1980,
SUM(YEAR(hiredate)=1981) AS Hired_1981,
SUM(YEAR(hiredate)=1982) AS Hired_1982,
SUM(YEAR(hiredate)=1983) AS Hired_1983
FROM emp;
```

---

### Question 7
Query to get the last Sunday of any month

```sql
SELECT 
DATE_SUB(LAST_DAY(CURDATE()), 
INTERVAL (DAYOFWEEK(LAST_DAY(CURDATE())) - 1) DAY) 
AS Last_Sunday;
```

---

### Question 8
Display department numbers and total number of employees in each department

```sql
SELECT deptno, 
COUNT(*) AS Total_Employees
FROM emp
GROUP BY deptno;
```

---

### Question 9
Display various jobs and total number of employees within each job group

```sql
SELECT job, 
COUNT(*) AS Total_Employees
FROM emp
GROUP BY job;
```

---

### Question 10
Display department numbers and total salary for each department

```sql
SELECT deptno, 
SUM(sal) AS Total_Salary
FROM emp
GROUP BY deptno;
```

