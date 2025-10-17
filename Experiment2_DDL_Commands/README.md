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

<img width="808" height="381" alt="image" src="https://github.com/user-attachments/assets/9bcb030e-8595-4a79-8678-e90fbc2a3f5f" />


```
INSERT INTO Student_details(RollNo,Name,Gender,Subject,MARKS)VALUES(202,'Ella King','F','Chemistry',87);
INSERT INTO Student_details(RollNo,Name,Gender,Subject,MARKS)VALUES(203,'James Bond','M','Literature',78)
```

**Output:**

<img width="850" height="378" alt="image" src="https://github.com/user-attachments/assets/35587560-2be2-42d0-a209-0a91328e061d" />


**Question 2**

<img width="1271" height="251" alt="image" src="https://github.com/user-attachments/assets/03e4c6e1-5b91-460c-92b2-4ff2feafaebb" />


```
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

<img width="1283" height="323" alt="image" src="https://github.com/user-attachments/assets/30ed5d59-c4ec-4528-bad0-43eb9e0b7c6a" />


**Question 3**

<img width="935" height="302" alt="image" src="https://github.com/user-attachments/assets/7f373d04-574a-4e91-baf8-344c5101dbd9" />


```
ALTER TABLE EMPLOYEES ADD COLUMN Date_of_joining Date;
ALTER TABLE EMPLOYEES RENAME COLUMN job_title TO Designation;
```

**Output:**

<img width="1275" height="351" alt="image" src="https://github.com/user-attachments/assets/c37de6d3-d954-4093-81aa-03b5bdbaf243" />


**Question 4**

<img width="745" height="292" alt="image" src="https://github.com/user-attachments/assets/c9d66e86-a72d-43e6-945b-230ca6cca376" />


```
INSERT INTO Customers(CustomerID,Name,Address,Email)
SELECT CustomerID,Name,Address,Email FROM Old_Customers;
```

**Output:**

<img width="1268" height="281" alt="image" src="https://github.com/user-attachments/assets/b4bd95c7-b3d0-42db-9729-e9517a5c0567" />


**Question 5**

<img width="839" height="343" alt="image" src="https://github.com/user-attachments/assets/798ff4d7-de0a-45ab-b1ca-a38739cfb904" />


```
CREATE TABLE Members(
MemberID INTEGER,
MemberName TEXT,
JoinDate DATE);
```

**Output:**

<img width="1323" height="311" alt="image" src="https://github.com/user-attachments/assets/0cbb9767-ece6-44c9-8aac-f6c3ff417cba" />


**Question 6**

<img width="1320" height="194" alt="image" src="https://github.com/user-attachments/assets/6f35a22e-7c82-4cb0-bbb4-87747f124530" />


```
CREATE TABLE jobs(
job_id INT,
job_title VARCHAR(100)DEFAULT '',
min_salary INT DEFAULT 8000,
max_salary INT DEFAULT NULL);
```

**Output:**

<img width="1325" height="284" alt="image" src="https://github.com/user-attachments/assets/f367fef1-e360-4387-a372-5b8d76efab03" />


**Question 7**

<img width="858" height="332" alt="image" src="https://github.com/user-attachments/assets/5c2db99e-2791-473b-8388-f6ba99785b1b" />



```
INSERT INTO Employee(EmployeeID,Name,Position)
VALUES(4,'Emily White','Analyst');
```

**Output:**

<img width="965" height="306" alt="image" src="https://github.com/user-attachments/assets/d22dfa2a-334b-490f-8c74-ed04e064335b" />


**Question 8**

<img width="1207" height="599" alt="image" src="https://github.com/user-attachments/assets/e307afe7-e4d6-491e-822f-325bf72678d7" />

```
ALTER TABLE customer
ADD discount DECIMAL(5,2);
```

**Output:**

<img width="1280" height="246" alt="image" src="https://github.com/user-attachments/assets/88c4277b-fcca-47f0-82b8-5315908d4f8c" />


**Question 9**

<img width="1252" height="393" alt="image" src="https://github.com/user-attachments/assets/414f1d63-f455-470c-af75-1781078eb1c4" />


```
ALTER TABLE Employee ADD COLUMN department_id INTEGER ;
ALTER TABLE Employee ADD COLUMN manager_id INTEGER DEFAULT NULL ; 
```

**Output:**
<img width="1278" height="286" alt="image" src="https://github.com/user-attachments/assets/437d7801-a40c-4fec-867e-cff98537eaeb" />


**Question 10**

<img width="1316" height="275" alt="image" src="https://github.com/user-attachments/assets/3bfdd163-40e7-4532-bb80-be7c486b4233" />


```
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

<img width="1334" height="259" alt="image" src="https://github.com/user-attachments/assets/98e21d49-582c-4049-92d3-21be0a447eae" />



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
