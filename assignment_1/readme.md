# Database Management System Lab

## Concepts and Lessons:



## Assignment 1:

### Create the following tables:

#### EMP
| Column name | Data type | Description              |
|-------------|------------|--------------------------|
| EMPNO       | Number     | Employee number          |
| ENAME       | Varchar    | Employee name            |
| JOB         | Char       | Designation              |
| MGR         | Number     | Manager’s Emp. Number    |
| HIREDATE    | Date       | Date of joining          |
| SAL         | Number     | Basic Salary             |
| COMM        | Number     | Commission               |
| DEPTNO      | Number     | Department Number        |

#### DEPT
| Column name | Data type | Description              |
|-------------|------------|--------------------------|
| DEPTNO      | Number     | Department number        |
| DNAME       | Varchar    | Department name          |
| LOC         | Varchar    | Location of department   |

### Data for EMP
| EMPNO | ENAME  | JOB      | MGR  | HIREDATE  | SAL  | COMM | DEPTNO |
|-------|--------|----------|------|-----------|------|------|--------|
| 7369  | Smith  | Clerk    | 7902 | 17/12/80  | 800  | NULL | 20     |
| 7499  | Allen  | Salesman | 7698 | 20/2/81   | 1600 | 300  | 30     |
| 7521  | Ward   | Salesman | 7698 | 22/2/81   | 1250 | 500  | 30     |
| 7566  | Jones  | Manager  | 7839 | 2/4/81    | 2975 | NULL | 20     |
| 7654  | Martin | Salesman | 7698 | 28/9/81   | 1250 | 1400 | 30     |
| 7698  | Blake  | Manager  | 7839 | 1/5/81    | 2850 | NULL | 30     |
| 7782  | Clark  | Manager  | 7839 | 9/6/81    | 2450 | NULL | 10     |
| 7788  | Scott  | Analyst  | 7566 | 9/12/82   | 3000 | NULL | 20     |
| 7839  | King   | President| NULL | 17/11/81  | 5000 | NULL | 10     |
| 7844  | Turner | Salesman | 7698 | 8/9/81    | 1500 | 0    | 30     |
| 7876  | Adams  | Clerk    | 7788 | 12/1/83   | 1100 | NULL | 20     |
| 7900  | James  | Clerk    | 7698 | 3/12/81   | 950  | NULL | 30     |
| 7902  | Ford   | Analyst  | 7566 | 4/12/81   | 3000 | NULL | 20     |
| 7934  | Miller | Clerk    | 7782 | 23/1/82   | 1300 | NULL | 10     |

### Data for DEPT table
| DEPTNO | DNAME       | LOC      |
|--------|-------------|----------|
| 10     | Accounting  | New York |
| 20     | Research    | Dallas   |
| 30     | Sales       | Chicago  |
| 40     | Operations  | Boston   |

### Table Creation Commands:

1. Create EMP table:
    ```sql
    CREATE TABLE EMP (
        EMPNO NUMBER PRIMARY KEY,
        ENAME VARCHAR2(50),
        JOB CHAR(10),
        MGR NUMBER,
        HIREDATE DATE,
        SAL NUMBER,
        COMM NUMBER,
        DEPTNO NUMBER
    );
    ```

2. Create DEPT table:
    ```sql
    CREATE TABLE DEPT (
        DEPTNO NUMBER PRIMARY KEY,
        DNAME VARCHAR2(50),
        LOC VARCHAR2(50)
    );
    ```

### Table Deletion Commands:

1. Drop EMP table:
    ```sql
    DROP TABLE EMP;
    ```

2. Drop DEPT table:
    ```sql
    DROP TABLE DEPT;
    ```

### Write SQL queries for the following questions:

1. Display all records in the EMP table.
    ```sql
    SELECT * FROM EMP;
    ```

2. Display all employees who are working as managers.
    ```sql
    SELECT * FROM EMP WHERE JOB = 'Manager';
    ```

3. Display the detail of employee with employee no. 7369.
    ```sql
    SELECT * FROM EMP WHERE EMPNO = 7369;
    ```

4. Display all employees who joined on 1st May, 1981.
    ```sql
    SELECT * FROM EMP WHERE HIREDATE = '01-MAY-1981';
    ```

5. Display all employees with salary greater than Rs.1500/-.
    ```sql
    SELECT * FROM EMP WHERE SAL > 1500;
    ```

6. Display all employees who are not getting any commission.
    ```sql
    SELECT * FROM EMP WHERE COMM IS NULL;
    ```

7. Display all employees whose names are starting with “A”.
    ```sql
    SELECT * FROM EMP WHERE ENAME LIKE 'A%';
    ```

8. Add a new attribute Phone No.
    ```sql
    ALTER TABLE EMP ADD (PHONE_NO VARCHAR2(15));
    ```

9. Change the data type of attribute Job from char to varchar2.
    ```sql
    ALTER TABLE EMP MODIFY (JOB VARCHAR2(10));
    ```

10. Remove the attribute Phone No. from the table.
    ```sql
    ALTER TABLE EMP DROP COLUMN PHONE_NO;
    ```