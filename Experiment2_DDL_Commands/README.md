# Experiment 2: DDL Commands

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
<img width="537" height="302" alt="image" src="https://github.com/user-attachments/assets/a831dad7-c544-43be-838f-05777f251c1f" />

```sql
alter table Student_details ADD Mobilenumber number;
```

**Output:**

<img width="931" height="178" alt="image" src="https://github.com/user-attachments/assets/caaa8f7c-84f7-487e-b602-25f405c44c0d" />


**Question 2**
---
<img width="720" height="134" alt="image" src="https://github.com/user-attachments/assets/b680639a-57a8-46cf-a32b-a20a0bb0579e" />

```sql
Insert into Customers values(301,'Michael Jordan','123 Maple St','Chicago',60616);
```

**Output:**

<img width="905" height="124" alt="image" src="https://github.com/user-attachments/assets/3cfb61e3-bb7a-4f3a-8954-2840ee698391" />

**Question 3**
---
<img width="414" height="205" alt="image" src="https://github.com/user-attachments/assets/57905eb4-3836-4bfb-8142-dee41a6885b5" />

```sql
Insert into Employee values(2,'John Smith','Developer','IT',75000);
Insert into Employee values(3,'Anna Bell','Designer','Marketing',68000);
```

**Output:**

<img width="952" height="163" alt="image" src="https://github.com/user-attachments/assets/c69eb905-1d58-4ddc-a8e5-3bd60fc51a8f" />

**Question 4**
---
<img width="691" height="171" alt="image" src="https://github.com/user-attachments/assets/fe8032b2-f19d-40d4-b14b-3b49086554d9" />

```sql
Create table Department (DepartmentID integer,DepartmentName text Unique NOT NULL,Location text);
```

**Output:**

<img width="999" height="118" alt="image" src="https://github.com/user-attachments/assets/ad7442e0-f01b-4922-a58e-ddc26cc07093" />

**Question 5**
---
<img width="602" height="140" alt="image" src="https://github.com/user-attachments/assets/3d11fd59-f4d4-4f88-bab9-f31c72ba8af4" />

```sql
Create table ProjectAssignments (AssignmentID integer Primary key, EmployeeID integer, 
ProjectID integer, AssignmentDate date not null,
foreign key (EmployeeID) references Employees(EmployeeID), 
foreign key (ProjectID) references Projects(ProjectID));
```

**Output:**

<img width="1068" height="130" alt="image" src="https://github.com/user-attachments/assets/c4b23e83-ece9-46ee-bcdc-55cb6e8645f0" />

**Question 6**
---
<img width="666" height="228" alt="image" src="https://github.com/user-attachments/assets/2d450718-0ed2-4841-8139-55e281bf4431" />

```sql
alter table Companies rename column name to first_name;
alter table Companies add mobilenumber number;
alter table Companies add DOB Date;
```

**Output:**

<img width="1065" height="216" alt="image" src="https://github.com/user-attachments/assets/450be3f2-4988-421e-9c9c-e09a90a82820" />

**Question 7**
---
<img width="942" height="235" alt="image" src="https://github.com/user-attachments/assets/2ce98373-48b0-4bb1-86d9-1026d378a533" />

```sql
Create table Products(ProductID INTEGER primary key,
ProductName TEXT unique not NULL,
Price REAL Check (Price>0),
StockQuantity INTEGER Check (StockQuantity>0));
```

**Output:**

<img width="1049" height="128" alt="image" src="https://github.com/user-attachments/assets/4905485b-f273-49d5-8006-35284713bc1a" />

**Question 8**
---
<img width="802" height="392" alt="image" src="https://github.com/user-attachments/assets/12b3ce95-0510-4ce3-842e-0625d393a41c" />

```sql
insert into Student_details Select * from Archived_students;
```

**Output:**

<img width="960" height="164" alt="image" src="https://github.com/user-attachments/assets/280f194f-9302-42f2-a81a-1a7ea4088ba2" />

**Question 9**
---
<img width="1010" height="243" alt="image" src="https://github.com/user-attachments/assets/e073c75c-5d6c-4ca0-b2af-8d8f5f96689a" />

```sql
Create table Invoices(InvoiceID INTEGER primary key,
InvoiceDate DATE,
Amount REAL Check(Amount>0),
DueDate DATE check(DueDate>InvoiceDate),
OrderID INTEGER references Orders(OrderID));
```

**Output:**

<img width="1107" height="126" alt="image" src="https://github.com/user-attachments/assets/973ddebc-15b0-404f-80cd-fea576eb0cf8" />

**Question 10**
---
<img width="666" height="273" alt="image" src="https://github.com/user-attachments/assets/9c2b1508-d79e-4d24-b057-e8a3036f7338" />

```sql
Create table Products(ProductID INTEGER,
ProductName TEXT,
Price REAL,
Stock INTEGER);
```

**Output:**
<img width="982" height="184" alt="image" src="https://github.com/user-attachments/assets/9bcbf7e2-110c-42a4-943f-7e860e75e18e" />

## Screenshot of Module 1 SEB Completion Grades
<img width="982" height="49" alt="image" src="https://github.com/user-attachments/assets/d266115e-190a-490d-9a57-f84fc42567fa" />


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
