<h1 align="center">Experiment 6</h1>

## AIM
To study and apply SQL single-row, character, and date functions to retrieve, format, and manipulate employee data effectively.


---

### Question 1  
Display empno, ename, deptno from employee table. Instead of display department numbers display the related department name (Use decode function).

```sql
SELECT empno, ename,
DECODE(deptno, 10, 'ACCOUNTING', 20, 'RESEARCH', 30, 'SALES', 40, 'OPERATIONS') AS dept_name
FROM emp;
```

---

### Question 2  
Display your age in days.

```sql
SELECT TRUNC(SYSDATE - TO_DATE('01-01-2004','%d-%m-%Y')) AS age_in_days
FROM dual;
```

---

### Question 3  
Display your age in months.

```sql
SELECT TRUNC(MONTHS_BETWEEN(SYSDATE, TO_DATE('01-01-2004','%d-%m-%Y'))) AS age_in_months
FROM dual;
```

---

### Question 4  
Display the current date as 15th August Friday Nineteen Ninety-Seven.

```sql
SELECT TO_CHAR(SYSDATE, 'DDth Month Day YYYY') FROM dual;
```

---

### Question 5  
Display the following output for each row from employee table.

```sql
SELECT ename ' earns ' sal ' per month' AS output
FROM emp;
```

---

### Question 6  
Scott has joined the company on Wednesday 13th August Nineteen Ninety.

```sql
SELECT ename || ' has joined the company on ' ||
TO_CHAR(hiredate, 'Day DDth Month YYYY') AS joining_info
FROM emp
WHERE ename = 'SCOTT';
```

---

### Question 7  
Find the date for nearest Saturday after current date.

```sql
SELECT NEXT_DAY(SYSDATE, 'SATURDAY') FROM dual;
```

---

### Question 8  
Display current time.

```sql
SELECT TO_CHAR(SYSDATE, 'HH:MI:SS') FROM dual;
```

---

### Question 9  
Display the date three months before the current date.

```sql
SELECT ADD_MONTHS(SYSDATE, -3) FROM dual;
```

---

### Question 10  
Display those employees who joined in the company in the month of Dec.

```sql
SELECT * FROM emp
WHERE TO_CHAR(hiredate, '%m') = '12';
```

---

### Question 11  
Display those employees whose first 2 characters from hire date = last 2 characters of salary.

```sql
SELECT * FROM emp
WHERE SUBSTR(TO_CHAR(hiredate,'%d'),1,2) = SUBSTR(sal,-2);
```

---

### Question 12  
Display those employees whose 10% of salary is equal to the year of joining.

```sql
SELECT * FROM emp
WHERE (sal * 0.10) = TO_CHAR(hiredate,'%Y');
```

---

### Question 13  
Display those employees who joined the company before 15 of the month.

```sql
SELECT * FROM emp
WHERE TO_CHAR(hiredate,'%d') < 15;
```

---

### Question 14  
Display those employees who has joined before 15th of the month.

```sql
SELECT * FROM emp
WHERE TO_CHAR(hiredate,'%d') < '15';
```

---

### Question 15  
Display those employees whose joining DATE is available in deptno.

```sql
SELECT * FROM emp
WHERE TO_CHAR(hiredate,'%d') = deptno;
```

---