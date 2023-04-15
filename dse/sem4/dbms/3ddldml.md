## experiment no 3

- Aim: Study of Data Definition Language (DDL) & Data Manipulation Language (DML).
```sql
CREATE TABLE Employee(Emp_Id INTEGER,Emp_Name VARCHAR2(10),Emp_City VARCHAR2(10),Emp_Salary INTEGER);

DESC Employee;

INSERT INTO Employee VALUES(7345,'Smith','Mumbai',20000);
INSERT INTO Employee VALUES(7561,'Jones','Pune',35000);
INSERT INTO Employee VALUES(8111,'Johnson','Pune',82000);
INSERT INTO Employee VALUES(9012,'Marin','Kankavli',45000);
INSERT INTO Employee VALUES(9877,'Ward','Kolhapur',7000);
INSERT INTO Employee VALUES(9975,'Allen','Mumbai',15000);

Select * FROM Employee;

ALTER TABLE Employee MODIFY Emp_Name VARCHAR(20);

DESC Employee;

SELECT Emp_Name,Emp_City FROM Employee;

SELECT Emp_Name,Emp_Salary FROM Employee WHERE Emp_Salary>10000;

SELECT * FROM Employee WHERE Emp_City='Pune';

UPDATE Employee SET Emp_City='Delhi' WHERE Emp_ID=9877;

SELECT * FROM Employee;

UPDATE Employee SET Emp_City='Banglore',Emp_Salary=50000 WHERE Emp_Name='Jones';

SELECT * FROM Employee;



UPDATE Employee SET Emp_Salary = 50000

```
