# Experiment 2: DDL Commands
 ## NAME : ASIN RENIX V
 ## REG NO : 212224040036

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

<img width="808" height="381" alt="image" src="https://github.com/user-attachments/assets/8d9ad1f2-43e4-4423-9139-a7560cd5d1fe" />


```sql
INSERT INTO Student_details(RollNo,Name,Gender,Subject,MARKS)VALUES(202,'Ella King','F','Chemistry',87);
INSERT INTO Student_details(RollNo,Name,Gender,Subject,MARKS)VALUES(203,'James Bond','M','Literature',78)
```

**Output:**

<img width="1271" height="251" alt="image" src="https://github.com/user-attachments/assets/928fe367-f699-4f64-bfd9-01d4cf7719bb" />


**Question 2**

<img width="850" height="378" alt="image" src="https://github.com/user-attachments/assets/d99a7108-a338-4508-908e-476e996d318e" />


```sql
CREATE TABLE item(
item_id INT PRIMARY KEY,
item_desc TEXT NOT NULL,
rate INT NOT NULL,
icom_id TEXT(4),
CONSTRAINT fk_company
    FOREIGN KEY(icom_id)
    REFERENCES Company(com_id)
    ON UPDATE CASCADE
    ON DELETE CASCADE
);

```

**Output:**

<img width="1283" height="323" alt="image" src="https://github.com/user-attachments/assets/d67abc1f-10ff-4f97-b91f-84623f352f3a" />


**Question 3**

<img width="935" height="302" alt="image" src="https://github.com/user-attachments/assets/3221ff9e-65ab-44f2-82cd-1d0f2a9705ce" />


```sql
ALTER TABLE EMPLOYEES ADD COLUMN Date_of_joining Date;
ALTER TABLE EMPLOYEES RENAME COLUMN job_title TO Designation;

```

**Output:**

<img width="1275" height="351" alt="image" src="https://github.com/user-attachments/assets/e1b56d9d-2b6e-4476-946c-a85b802d973a" />


**Question 4**

<img width="745" height="292" alt="image" src="https://github.com/user-attachments/assets/fac9bf9c-a936-4805-95ef-42ffc87fb433" />


```sql
INSERT INTO Customers(CustomerID,Name,Address,Email)
SELECT CustomerID,Name,Address,Email FROM Old_Customers;
```

**Output:**

<img width="1268" height="281" alt="image" src="https://github.com/user-attachments/assets/fde88d02-b483-4697-89fd-9652fdc00f5b" />


**Question 5**

<img width="839" height="343" alt="image" src="https://github.com/user-attachments/assets/5c50a2b4-6fd0-4662-b5ce-1eb0a75bfb74" />


```sql
CREATE TABLE Members(
MemberID INTEGER,
MemberName TEXT,
JoinDate DATE);
```

**Output:**

<img width="1323" height="311" alt="image" src="https://github.com/user-attachments/assets/7075763e-c1dd-47f9-ba1a-72442600969a" />


**Question 6**

<img width="1320" height="194" alt="image" src="https://github.com/user-attachments/assets/31f5f166-1139-436d-835a-e8903c1d07f1" />


```sql
CREATE TABLE jobs(
job_id INT,
job_title VARCHAR(100)DEFAULT '',
min_salary INT DEFAULT 8000,
max_salary INT DEFAULT NULL);
```

**Output:**

<img width="1325" height="284" alt="image" src="https://github.com/user-attachments/assets/2261de91-714f-48ed-b160-68acc967c647" />


**Question 7**

<img width="858" height="332" alt="image" src="https://github.com/user-attachments/assets/b9e8af68-5258-4ba1-9ef7-a273a9754b38" />


```sql
INSERT INTO Employee(EmployeeID,Name,Position)
VALUES(4,'Emily White','Analyst');
```

**Output:**

<img width="965" height="306" alt="image" src="https://github.com/user-attachments/assets/41d58bfb-dbc9-45b8-a8e5-1b505db54a8c" />


**Question 8**

<img width="1207" height="599" alt="image" src="https://github.com/user-attachments/assets/cfb5f456-4737-4193-a48c-a323d79dcf47" />


```sql
ALTER TABLE customer
ADD discount DECIMAL(5,2);
```

**Output:**

<img width="1280" height="246" alt="image" src="https://github.com/user-attachments/assets/ee4d14a3-f65c-425d-bccb-bcf858c00c8f" />


**Question 9**

<img width="1252" height="393" alt="image" src="https://github.com/user-attachments/assets/265afe62-eeec-4768-85f6-c1a295d758c6" />


```sql
ALTER TABLE Employee ADD COLUMN department_id INTEGER ;
ALTER TABLE Employee ADD COLUMN manager_id INTEGER DEFAULT NULL ; 
```

**Output:**

<img width="1278" height="286" alt="image" src="https://github.com/user-attachments/assets/a3c940e2-aed0-4ba6-98cc-5a4ea1449f40" />


**Question 10**

<img width="1316" height="275" alt="image" src="https://github.com/user-attachments/assets/a01617e9-e95c-4d5f-9c19-c8db77d82f02" />


```sql
CREATE TABLE Bonuses(
BonusID INTEGER PRIMARY KEY,
EmployeeID INTEGER,
BonusAmount REAL CHECK(BonusAmount>0),
BonusDate DATE,
Reason TEXT NOT NULL,
CONSTRAINT fk_employee
    FOREIGN KEY(EmployeeID)
    REFERENCES Employees(EmployeeID))
```

**Output:**

<img width="1334" height="259" alt="image" src="https://github.com/user-attachments/assets/aa759a82-3083-413a-852f-c31c968efb14" />

## RESULT:
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
