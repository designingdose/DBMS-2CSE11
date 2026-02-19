<h1 align="center">Experiment 5</h1>

## AIM
To perform SQL aggregate operations on the EMPLOYEE table using functions such as COUNT, SUM, MAX, MIN, and AVG, and to apply string manipulation functions including UPPER, LOWER, INITCAP, and LENGTH for data transformation and analysis.

---

## Queries:

### Question 1
Display the total number of employee working in the
company.

```sql
SELECT COUNT(*) AS TOTAL_EMPLOYEES FROM EMPLOYEE;
```

---

### Question 2
Display the total salary of all employees working in the
company.

```sql
SELECT SUM(SAL) AS TOTAL_SALARY FROM EMPLOYEE;
```

---

### Question 3
Display the highest salary drawn by any employee in the
company.

```sql
SELECT MAX(SAL) AS HIGHEST_SALARY FROM EMPLOYEE;
```

---

### Question 4
Display the lowest salary drawn by any employee in the
company.

```sql
SELECT MIN(SAL) AS LOWEST_SALARY FROM EMPLOYEE;
```

---

### Question 5
Display the average salary from employee table

```sql
SELECT AVG(SAL) AS AVERAGE_SALARY FROM EMPLOYEE;
```

---

### Question 6
Display the maximum salary being paid to clerk.

```sql
SELECT MAX(SAL) AS MAX_SALARY FROM EMPLOYEE WHERE JOB = 'CLERK';
```

---

### Question 7
Display the maximum salary being paid in dept no 20.

```sql
SELECT MAX(SAL) AS MAX_SALARY FROM EMPLOYEE WHERE DEPTNO = 20;
```

---

### Question 8
Display the minimum salary paid to any salesman.

```sql
SELECT MIN(SAL) AS MIN_SALARY FROM EMPLOYEE WHERE JOB = 'SALESMAN';
```

---

### Question 9
Display the average salary drawn by managers.

```sql
SELECT AVG(SAL) AS AVERAGE_SALARY FROM EMPLOYEE WHERE JOB = 'MANAGER';
```

---

### Question 10
Display the total salary drawn by analyst working in dept no
40.

```sql
SELECT SUM(SAL) AS TOTAL_SALARY FROM EMPLOYEE WHERE JOB = 'ANALYST' AND DEPTNO = 40;
```

---

### Question 11
Display the names of the employee in Uppercase.
```sql
SELECT UPPER(ename) AS UPPERCASE_NAMES FROM EMPLOYEE;
```
### Question 12
Display the names of the employee in Lowercase.

```sql
SELECT LOWER(ename) AS LOWERCASE_NAMES FROM EMPLOYEE;
```
### Question 13
Display the names of the employee in Proper case.

```sql
SELECT CONCAT(UCASE(LEFT(ENAME,1)), LCASE(SUBSTRING(ENAME,2))) AS EMPLOYEE_NAME FROM EMPLOYEE;

```
### Question 14
Display the length of Your name using appropriate function.

```sql
SELECT LENGTH('Khushi') AS NAME_LENGTH FROM DUAL;
```
### Question 15
 Display the length of all the employee names.

```sql
SELECT ename, LENGTH(ename) AS name_length FROM employee;
```

