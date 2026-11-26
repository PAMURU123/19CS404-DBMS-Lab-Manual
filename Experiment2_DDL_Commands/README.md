# Experiment 2: DDL Commands
NAME:PAMURU VENKATESH
```
REG NO.:212224040230
```
## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
--
-- <img width="1222" height="297" alt="image" src="https://github.com/user-attachments/assets/d4f67359-78e5-4db2-9163-051a403e64bb" />


```sql
CREATE TABLE jobs(
job_id int PRIMARY KEY,
job_title varchar(225) default'',
min_salary int default 8000,
max_salary int default null
);
```

**Output:**

<img width="1231" height="407" alt="image" src="https://github.com/user-attachments/assets/4392c5e7-adba-478d-bae3-1ca5d79a8e93" />


**Question 2**
---
-- <img width="1436" height="520" alt="image" src="https://github.com/user-attachments/assets/3cc91905-972e-459c-b8d0-0271b01ba35d" />


```sql
ALTER table Companies rename column name TO first_name;
ALTER table Companies add column mobilenumber number;
ALTER table Companies add column DOB Date;
```

**Output:**

<img width="1235" height="480" alt="image" src="https://github.com/user-attachments/assets/0dbc6421-a4bb-411e-ba90-0e8ffcf1fea4" />

**Question 3**
---
-- <img width="1358" height="611" alt="image" src="https://github.com/user-attachments/assets/f8c1ac53-5de3-4289-b43e-04484f62efe1" />


```sql
ALTER TABLE customer
ADD discount DECIMAL(5,2);
```

**Output:**

<img width="1222" height="421" alt="image" src="https://github.com/user-attachments/assets/3a9e414e-c8e2-4d5e-9d1b-f1ecb4b50c45" />

**Question 4**
---
-- <img width="1402" height="425" alt="image" src="https://github.com/user-attachments/assets/9585870b-9203-472f-af15-cee9aae36716" />


```sql
CREATE TABLE Attendance(
    AttendanceID INTEGER PRIMARY KEY,
    EmployeeID INTEGER,
    AttendanceDate date,
    Status TEXT CHECK (Status IN ('Present','Absent','Leave')),
    FOREIGN KEY(EmployeeID) REFERENCES Employees(EmployeeID)
    
);
```

**Output:**

<img width="1222" height="373" alt="image" src="https://github.com/user-attachments/assets/dd6b9f8c-b5a4-4484-9de8-39db4d83fbcf" />

**Question 5**
---
-- <img width="1412" height="362" alt="image" src="https://github.com/user-attachments/assets/bde182a7-85c7-4f6e-b7b2-9f725b268cff" />


```sql
CREATE TABLE Shipments (
    ShipmentID INTEGER PRIMARY KEY,
    ShipmentDate DATE,
    SupplierID INTEGER,
    OrderID INTEGER,
    FOREIGN KEY (SupplierID) REFERENCES Suppliers(SupplierID),
    FOREIGN KEY (OrderID) REFERENCES Orders(OrderID)
);
```

**Output:**

<img width="1222" height="321" alt="image" src="https://github.com/user-attachments/assets/925a2b9e-12a2-4d30-8740-041f854943dc" />

**Question 6**
---
-- <img width="1117" height="377" alt="image" src="https://github.com/user-attachments/assets/9bf13f2e-e87d-47ca-8740-dc83a0949433" />


```sql
INSERT INTO products (productID, productName, price, stock)
SELECT productID, productName, price, stock
FROM Discontinued_products;
```

**Output:**

<img width="1217" height="357" alt="image" src="https://github.com/user-attachments/assets/c0af6a71-fe5c-4c94-aa99-52a1acbd2ae7" />

**Question 7**
---
-- <img width="1277" height="490" alt="image" src="https://github.com/user-attachments/assets/1e24afe4-28a3-4fe5-9277-ea9cfee29c75" />


```sql
INSERT INTO Books (ISBN, title, author)
VALUES ('978-6655443321', 'Big Data Analytics', 'Karen Adams');
```

**Output:**

<img width="1211" height="396" alt="image" src="https://github.com/user-attachments/assets/01c47a40-ad49-4b76-a944-39d9904a1452" />

**Question 8**
---
-- <img width="1246" height="440" alt="image" src="https://github.com/user-attachments/assets/630ca6c3-5f74-4ffd-80b9-6dba062ee612" />


```sql
create table Orders(
OrderID INTEGER,
OrderDate TEXT,
CustomerID INTEGER
);
```

**Output:**

<img width="1200" height="425" alt="image" src="https://github.com/user-attachments/assets/33bb7cbe-cdac-4a84-9422-de513cd5d16a" />

**Question 9**
---
-- <img width="1406" height="462" alt="image" src="https://github.com/user-attachments/assets/d89417e2-0ca6-4fee-a442-c0049f9c6c4b" />


```sql
CREATE TABLE Invoices(
InvoiceID INTEGER PRIMARY KEY,
InvoiceDate DATE NOT NULL,
Amount REAL CHECK (Amount>0),
DueDate DATE CHECK (DueDate>InvoiceDate),
OrderID INTEGER,
FOREIGN KEY (OrderID) REFERENCES
Orders(OrderID)
);
```

**Output:**

<img width="1195" height="351" alt="image" src="https://github.com/user-attachments/assets/8aee8270-fca1-446f-a735-17b2a47cbaa9" />

**Question 10**
---
-- <img width="920" height="455" alt="image" src="https://github.com/user-attachments/assets/e7c35171-867c-42c4-9b90-08c2a6d74d12" />


```sql
insert into Student_details(RollNo,Name,Gender,Subject,MARKS)
VALUES(202,'Ella King','F','Chemistry',87),(203,'James Bond','M','Literature',78);
```

**Output:**

<img width="1211" height="337" alt="image" src="https://github.com/user-attachments/assets/cace321b-53d9-4a62-a2d2-0e057686e366" />


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
