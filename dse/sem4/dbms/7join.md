## experiment no 7

- Aim: Study of set operations and join operations of SQL.
```sql
CREATE TABLE Test(
Name VARCHAR2(15),
Matches INTEGER,
Runs INTEGER,
Wickets INTEGER,
Centuries INTEGER,
Batting_Avg NUMBER
);


CREATE TABLE Odi(
Name VARCHAR2(15),
Matches INTEGER,
Runs INTEGER,
Wickets INTEGER,
Centuries INTEGER,
Strike_Rate NUMBER
);


INSERT INTO Test VALUES('Sehwag',83,6367,47,19,39);
INSERT INTO Test VALUES('Gambhir',39,3249,2,10,38);
INSERT INTO Test VALUES('Tendulkar',163,17439,15,47,55);
INSERT INTO Test VALUES('Kohli',34,2879,1,8,42);
INSERT INTO Test VALUES('Dravid',135,11279,23,28,55);


SELECT * FROM Test;


INSERT INTO Odi VALUES('Sehwag',179,6254,82,14,108.14);
INSERT INTO Odi VALUES('Gambhir',122,4234,4,8,84.47);
INSERT INTO Odi VALUES('Tendulkar',442,13593,128,46,86.57);
INSERT INTO Odi VALUES('Dravid',381,10768,17,21,78.32);
INSERT INTO Odi VALUES('Raina',97,3572,39,5,82.73);


SELECT * FROM Odi;


SELECT Name FROM Test 
UNION
SELECT Name FROM Odi;   //1

SELECT Name FROM Test 
INTERSECT
SELECT Name FROM Odi;    //2

SELECT Name FROM Test 
MINUS
SELECT Name FROM Odi;    //3

SELECT Name FROM Test WHERE Wickets>10
UNION
SELECT Name FROM Odi WHERE Runs>7000;

SELECT Name FROM Test WHERE Wickets>10
INTERSECT
SELECT Name FROM Odi WHERE Runs>7000;   //4


SELECT Name FROM Test WHERE Batting_avg<40
INTERSECT
SELECT Name FROM Odi WHERE Strike_Rate>80;   //5


SELECT Name FROM Test WHERE Runs<10000
UNION
SELECT Name FROM Odi WHERE Wickets>25 AND Runs<10000;   //6

SELECT Name FROM Test WHERE Centuries>20
INTERSECT
SELECT Name FROM Odi WHERE Centuries<40;   //7

SELECT Name FROM Test WHERE Matches>100
UNION 
SELECT Name FROM Odi WHERE Matches<200;   //8




CREATE TABLE Employees(
Employee_Id INTEGER PRIMARY KEY,
Name VARCHAR(10)
);

CREATE TABLE Orders(
Prod_ID INTEGER PRIMARY KEY,
Product VARCHAR(10),
Employee_ID CONSTRAINT Orders_Eid_FK1 REFERENCES Employees(Employee_ID)
);


INSERT INTO Employees VALUES(1,'Hansen');
INSERT INTO Employees VALUES(2,'Svendson');
INSERT INTO Employees VALUES(3,'Stephen');
INSERT INTO Employees VALUES(4,'Pettersen');

SELECT * FROM Employees;

INSERT INTO Orders VALUES (234,'Printer',1);
INSERT INTO Orders VALUES (657,'Table',3);
INSERT INTO Orders VALUES (865,'Chair',3);

SELECT * FROM Orders;

SELECT E.Employee_ID,E.Name,O.Prod_ID,O.Product FROM Employees E INNER JOIN Orders O ON E.Employee_ID=O.Employee_ID;   //1

SELECT E.Employee_ID,E.Name,O.Prod_ID,O.Product FROM Employees E LEFT JOIN Orders O ON E.Employee_ID=O.Employee_ID ORDER BY E.Employee_ID ASC;   //2

SELECT E.Employee_ID,E.Name,O.Prod_ID,O.Product FROM Employees E RIGHT JOIN Orders O ON E.Employee_ID=O.Employee_ID ORDER BY E.Employee_ID ASC;   //3
```
