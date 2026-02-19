<h1 align="center"> Experiment 2 </h1>
## Aim
To retrieve data from relational tables using various SQL SELECT statements and apply different filtering, sorting, and expression techniques.

---

## Queries:

---


## Question 1
List all distinct job in Employee.



```sql
SELECT DISTINCT JOB FROM EMPLOYEE;
```

---

## Question 2
List all information about `Employee` in Department Number 30.



```sql
SELECT * FROM EMPLOYEE WHERE DEPTNO = 30;
```

---

## Question 3
Find all department number with department names greater
than 20.


```sql
SELECT deptno,dname FROM department WHERE deptno >20;
```

---

## Question 4
Find all information about all the managers as well as the
clerks in department 30.    



```sql
SELECT * FROM EMPLOYEE WHERE JOB IN ('MANAGER','CLERK') AND DEPTNO = 30;
```

---

## Question 5
List the Employee name, Employee numbers and department
of all clerks.



```sql
SELECT ename,empno,deptno FROM EMPLOYEE WHERE JOB = 'CLERK';
```

---

## Question 6
Find all managers not in department 30.



```sql
SELECT * FROM EMPLOYEE WHERE JOB = 'MANAGER' AND DEPTNO != 30;
```

---

## Question 7
List information about all Employees in department 10 who
are not manager or clerks.



```sql
SELECT * FROM EMPLOYEE WHERE DEPTNO = 10 AND JOB NOT IN ('MANAGER','CLERK');
```

---

## Question 8
Find Employees and jobs earning between 1200 and 1400.



```sql
SELECT * FROM employee WHERE sal>1200 AND sal<1400;
```

---

## Question 9
List Name and Department Number of employee who are
clerks, analyst or salesman.



```sql
SELECT ename,deptno FROM EMPLOYEE WHERE JOB IN ('CLERK','ANALYST','SALESMAN');
```

---

## Question 10
List Name and Department Number of employee whose names
began with M.


```sql
SELECT ename,deptno FROM EMPLOYEE WHERE ename LIKE 'M%';
```

---
