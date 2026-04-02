<h1 align="center">Experiment 8</h1>

## AIM
To perform SQL queries using joins, conditions, and aggregate functions on employee and department tables to retrieve meaningful information such as employee details, manager relationships, department data, and salary grades.

### CREATE TABLE salgrade 
```sql
CREATE TABLE SALGRADE (
 GRADE CHAR(1),
LOSAL INT,
HISAL INT
);
 
INSERT INTO SALGRADE VALUES
    -> ('A', 700, 1200),
    -> ('B', 1201, 1400),
    -> ('C', 1401, 2000),
    -> ('D', 2001, 3000),
    -> ('E', 3001, 9999);
```

### UPDATE department table

```sql
ALTER TABLE department
ADD LOCATION VARCHAR(20);

UPDATE department SET LOCATION = 'MUMBAI' WHERE deptno = 10;
UPDATE department SET LOCATION = 'CHENNAI' WHERE deptno = 20;
UPDATE department SET LOCATION = 'HYDERABAD' WHERE deptno = 30;
UPDATE department SET LOCATION = 'DELHI' WHERE deptno = 40;
```

### Question 1  
Display all employees with their dept name.

```sql
 SELECT e.ename, d.dname
 FROM employee e
 JOIN department d ON e.deptno = d.deptno;
 ```

### Question 2
Display those employees whose manager names is jones, and
also display their manager name.

```sql
SELECT e.ename AS employee, m.ename AS manager
FROM employee e
JOIN employee m ON e.mgr = m.empno
WHERE m.ename = 'JONES';
```

### Question 3
Display employee name, his job, his dept name, his manager
name, his grade and make out of an under department wise.

```sql
SELECT e.ename, e.job, d.dname, m.ename AS manager, s.grade
FROM employee e
JOIN department d ON e.deptno = d.deptno
LEFT JOIN employee m ON e.mgr = m.empno
JOIN salgrade s ON e.sal BETWEEN s.losal AND s.hisal
ORDER BY d.dname;
```


### Question 4
List out all the employees name, job, and salary grade and
department name for everyone in the company except ‘clerk’.
Sort on salary display the highest salary.

```sql
SELECT e.ename, e.job, s.grade, d.dname
FROM employee e
JOIN department d ON e.deptno = d.deptno
JOIN salgrade s ON e.sal BETWEEN s.losal AND s.hisal
WHERE e.job != 'CLERK'
ORDER BY e.sal DESC;
```


### Question 5
Display employee name, his job and his manager. Display also
employees who are without manager

```sql
SELECT e.ename, e.job, IFNULL(m.ename, 'No Manager') AS manager
FROM employee e
LEFT JOIN employee m ON e.mgr = m.empno;
```

### Question 6
List the employee name, job, annual salary, deptno, dept name
and grade who earn 36000 a year or who are not clerks.

```sql
SELECT e.ename, e.job, (e.sal*12) AS annual_sal, e.deptno, d.dname, s.grade
FROM employee e
JOIN department d ON e.deptno = d.deptno
JOIN salgrade s ON e.sal BETWEEN s.losal AND s.hisal
WHERE (e.sal*12) > 36000 OR e.job != 'CLERK';
```


### Question 7
List ename, job, annual sal, deptno, dname and grade who earn
30000 per year and who are not clerks.

```sql
SELECT e.ename, e.job, (e.sal*12) AS annual_sal, e.deptno, d.dname, s.grade
FROM employee e
JOIN department d ON e.deptno = d.deptno
JOIN salgrade s ON e.sal BETWEEN s.losal AND s.hisal
WHERE (e.sal*12) > 30000 AND e.job != 'CLERK';
```

### Question 8
List out all employees by name and number along with their
manager’s name and number also display ‘no manager’ who
has no manager.

```sql
MSELECT e.empno, e.ename,
IFNULL(m.empno, 'No Manager') AS mgr_no,
IFNULL(m.ename, 'No Manager') AS mgr_name
FROM employee e
LEFT JOIN employee m ON e.mgr = m.empno;
```


### Question 9
Select dept name, dept no and sum of sal

```sql
SELECT d.deptno, d.dname, SUM(e.sal) AS total_salary
FROM department d
JOIN employee e ON d.deptno = e.deptno
GROUP BY d.deptno, d.dname;
```
#
### Question 10
Display employee number, name and location of the
department in which he is working

```sql
SELECT e.empno, e.ename, d.location
FROM employee e
JOIN department d ON e.deptno = d.deptno;
```

### Question 11
Display employee name and department name for each
employee.

```sql
SELECT e.ename, d.dname
FROM employee e
JOIN department d ON e.deptno = d.deptno;
```
