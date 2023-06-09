## experiment no 8

- Aim: Study of AGGREGATE FUNCTIONS.
```sql
CREATE TABLE Employee1(
Emp_no NUMBER PRIMARY KEY,
Emp_name VARCHAR(10),
Job VARCHAR2(10),
Salary NUMBER,
Dept_no NUMBER
);

SELECT * FROM Employee1;

INSERT INTO Employee1 VALUES(1365,'Smith','Clerk',8000,10);
INSERT INTO Employee1 VALUES(2110,'John','Manager',45000,20);
INSERT INTO Employee1 VALUES(2567,'Harry','Salesman',4500,20);
INSERT INTO Employee1 VALUES(2890,'Johnson','Salesman',15000,10);
INSERT INTO Employee1 VALUES(3454,'Turner','Analyst',25000,10);
INSERT INTO Employee1 VALUES(5678,'James','Clerk',8500,30);
INSERT INTO Employee1 VALUES(5999,'Miller','Salesman',13500,30);
INSERT INTO Employee1 VALUES(6845,'Ford','Salesman',5000,20);
INSERT INTO Employee1 VALUES(6890,'Marin','Manager',50000,10);
INSERT INTO Employee1 VALUES(7000,'Allen','Clerk',7500,20);

SELECT COUNT(Emp_no) FROM Employee1;  //1

SELECT Dept_no,COUNT(Emp_no) FROM Employee1 GROUP BY Dept_no ORDER BY Dept_no ASC;   //2 

SELECT SUM(Salary) FROM Employee1 WHERE Job='Clerk';   //3

SELECT AVG(Salary) FROM Employee1;   //4

SELECT Dept_no,SUM(Salary) FROM Employee1 GROUP BY Dept_no ORDER BY Dept_no ASC;   //5 

SELECT Dept_no,AVG(Salary) FROM Employee1 GROUP BY Dept_no HAVING COUNT(Emp_no)>3 ORDER BY Dept_no ASC; //6

SELECT Job,COUNT(Emp_no) FROM Employee1 GROUP BY Job ORDER BY COUNT(Emp_no) DESC;   //7 

SELECT * FROM Employee1 WHERE Salary>=25000;    //8

SELECT AVG(Salary),Job FROM Employee1 GROUP BY Job HAVING Job<>'Manager';    //9

SELECT Job,SUM(Salary),MAX(Salary),MIN(Salary),AVG(Salary) FROM Employee1 GROUP BY Job;   //10

//SELECT Job,SUM(Salary),MAX(Salary),MIN(Salary),AVG(Salary) FROM Employee1 GROUP BY Job;   //11

//SELECT Job,SUM(Salary),MAX(Salary),MIN(Salary),AVG(Salary) FROM Employee1 GROUP BY Job;   //12
```

### updated codes
```sql
CREATE TABLE Employee1(
Emp_no INT PRIMARY KEY,
Emp_name VARCHAR(10),
Job VARCHAR(10),
Salary DECIMAL(10,2),
Dept_no INT
);

SELECT * FROM Employee1;

INSERT INTO Employee1 VALUES(1365,'Smith','Clerk',8000,10);
INSERT INTO Employee1 VALUES(2110,'John','Manager',45000,20);
INSERT INTO Employee1 VALUES(2567,'Harry','Salesman',4500,20);
INSERT INTO Employee1 VALUES(2890,'Johnson','Salesman',15000,10);
INSERT INTO Employee1 VALUES(3454,'Turner','Analyst',25000,10);
INSERT INTO Employee1 VALUES(5678,'James','Clerk',8500,30);
INSERT INTO Employee1 VALUES(5999,'Miller','Salesman',13500,30);
INSERT INTO Employee1 VALUES(6845,'Ford','Salesman',5000,20);
INSERT INTO Employee1 VALUES(6890,'Marin','Manager',50000,10);
INSERT INTO Employee1 VALUES(7000,'Allen','Clerk',7500,20);

SELECT COUNT(Emp_no) FROM Employee1;  -- 1

SELECT Dept_no,COUNT(Emp_no) FROM Employee1 GROUP BY Dept_no ORDER BY Dept_no ASC;   -- 2 

SELECT SUM(Salary) FROM Employee1 WHERE Job='Clerk';   -- 3

SELECT AVG(Salary) FROM Employee1;   -- 4

SELECT Dept_no,SUM(Salary) FROM Employee1 GROUP BY Dept_no ORDER BY Dept_no ASC;   -- 5 

SELECT Dept_no,AVG(Salary) FROM Employee1 GROUP BY Dept_no HAVING COUNT(Emp_no)>3 ORDER BY Dept_no ASC; -- 6

SELECT Job,COUNT(Emp_no) FROM Employee1 GROUP BY Job ORDER BY COUNT(Emp_no) DESC;   -- 7 

SELECT * FROM Employee1 WHERE Salary>=25000;    -- 8

SELECT AVG(Salary),Job FROM Employee1 GROUP BY Job HAVING Job<>'Manager';    -- 9

SELECT Job,SUM(Salary),MAX(Salary),MIN(Salary),AVG(Salary) FROM Employee1 GROUP BY Job;   -- 10

-- SELECT Job,SUM(Salary),MAX(Salary),MIN(Salary),AVG(Salary) FROM Employee1 GROUP BY Job;   -- 11

-- SELECT Job,SUM(Salary),MAX(Salary),MIN(Salary),AVG(Salary) FROM Employee1 GROUP BY Job;   -- 12
```
