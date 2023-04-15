## experiment no 4

- Aim: Apply integrity constraints for the specified system.
```sql
CREATE TABLE customers
( customer_name char(50) NOT NULL,
  customer_street char(50),
  customer_city char(50),
  CONSTRAINT customers_pk PRIMARY KEY (customer_name)
);

DESC customers;

CREATE TABLE branch
( branch_name char(50) NOT NULL,
  branch_city char(50),
  branch_asset NUMBER(10) CHECK (branch_asset>0),
  CONSTRAINT branch_pk PRIMARY KEY (branch_name)
);

DESC branch;
```
