<h1 align="center"> Experiment 0</h1>

## Aim
To create the EMPLOYEE and DEPARTMENT tables as per the given constraints

---

## Question 1
Create a `Department` table and display all records from it.

---

### Query

Creating a table named `DEPARTMENT`.

```sql
CREATE TABLE DEPARTMENT (
    DEPTNO NUMBER(2) PRIMARY KEY,
    DNAME VARCHAR2(15) NOT NULL
);
```

### Query


Inserting values in Departmennt table.

```sql
INSERT INTO DEPARTMENT VALUES(10,"RESEARCH"),
(20,"ACCOUNTING"),
(30,"SALES"),
(40,"OPERATIONS");
```

### Query 

Display all records from the `DEPARTMENT` table.

```sql
SELECT * FROM DEPARTMENT;
```

## Question 2

Creating a table named `EMPLOYEE`.

 
 ---
```sql 
Create a table `EMPLOYEE` with the following attributes:
- `EMPNO` (integer, primary key)
- `ENAME` (string, not null)
- `JOB` (string)
- `MGR` (integer)
- `HIREDATE` (date)
- `SAL` (integer)
- `COMM` (integer)
- `DEPTNO` (integer, foreign key referencing `DEPARTMENT.DEPTNO`);
```


---

### Query

Inserting values into the `EMPLOYEE` table.

```sql
INSERT INTO EMPLOYEE VALUES
    -> (7369,'SMITH','CLERK',7902,'1980-12-17',800,NULL,20),
    -> (7499,'ALLEN','SALESMAN',7698,'1981-02-20',1600,300,30),
    -> (7521,'WARD','SALESMAN',7698,'1981-02-22',1250,300,30),
    -> (7566,'JONES','MANAGER',7839,'1981-04-02',2975,NULL,20),
    -> (7654,'MARTIN','SALESMAN',7698,'1981-09-28',1250,1400,30),
    -> (7698,'BLAKE','MANAGER',7839,'1981-05-01',2850,NULL,30),
    -> (7782,'CLARK','MANAGER',7839,'1981-06-09',2450,NULL,20),
    -> (7788,'SCOTT','ANALYST',7566,'1982-12-09',3000,NULL,40),
    -> (7839,'KING','PRESIDENT',NULL,'1981-11-17',5000,NULL,20),
    -> (7844,'TURNER','SALESMAN',7698,'1981-09-08',1500,0,30),
    -> (7876,'ADAMS','CLERK',7788,'1983-01-12',1100,NULL,20),
    -> (7900,'JAMES','CLERK',7698,'1981-12-03',950,NULL,30),
    -> (7902,'FORD','ANALYST',7566,'1981-12-03',3000,NULL,20),
    -> (7934,'MILLER','CLERK',7782,'1982-01-23',1300,NULL,10);
```

---

### Query

Display all records from the `EMPLOYEE` table.

```sql
SELECT * FROM EMPLOYEE;
```
