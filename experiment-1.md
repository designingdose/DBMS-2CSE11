<h1 align="center"> Experiment 1 </h1>

## Aim
To create table Employee_Master from Employee table and perform basic SQL operations such as INSERT, SELECT, UPDATE, and DELETE.

---

## Question 1
Create a `Employee_Master` table and display all records from it.

---

### Query

```sql
CREATE TABLE EMPLOYEE_MASTER AS
SELECT * FROM EMPLOYEE;
```

### Query

```sql
SELECT * FROM EMPLOYEE_MASTER;
```

## Question 2
Delete all records from `EMPLOYEE_MASTER` table WHERE deptno = 10. 

```sql
DELETE FROM EMPLOYEE_MASTER WHERE deptno = 10;
```

## Question 3
Update 10% Salary Increase for DEPTNO = 20.

---

### Query

```sql
UPDATE EMPLOYEE_MASTER SET SAL = SAL * 1.1 WHERE deptno = 20;
```

----


## Question 4
Alter SAL column to NUMBER(10,2).

### Query

```sql
ALTER TABLE EMPLOYEE_MASTER MODIFY SAL NUMBER(10,2);
```
----


## Question 5
Drop EMPLOYEE_MASTER Table.

### Query

```sql
DROP TABLE EMPLOYEE_MASTER;
```

