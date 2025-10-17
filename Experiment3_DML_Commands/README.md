# Experiment 3: DML Commands

## NAME : ASIN RENIX V
## REG NO : 212224040036

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**

Write a SQL statement to Update the product_name to 'Premium Bread' whose product ID is 5 in the products table. Products table

```sql
update products set product_name ='Premium Bread' where product_id=5;
```

**Output:**

<img width="1246" height="476" alt="image" src="https://github.com/user-attachments/assets/3a475077-d2d0-4366-8a59-408bde95c87c" />

**Question 2**

Write a SQL statement to Update the grade of all customers in Chennai city as 5. Customer table (customer_id,cust_name,city,grade,salesman_id)

```sql
update Customer set grade=5 where city='Chennai';
```

**Output:**

<img width="1235" height="558" alt="image" src="https://github.com/user-attachments/assets/6fbde466-6139-4a1f-865e-3e0c635cf46a" />


**Question 3**

Salary will be increased by 25% for the department 40, 15% for department 90 and 10% for the department 110 and the rest of the departments will remain same. Employees table

```sql
update Employees set salary=salary+salary*0.25 where department_id=40;
update Employees set salary=salary+salary*0.15 where department_id=90;
update Employees set salary=salary+salary*0.1 where department_id=110;
```

**Output:**

<img width="1229" height="530" alt="image" src="https://github.com/user-attachments/assets/bdeced98-e011-4cc3-a7a0-6f521cdc9a2b" />


**Question 4**

Write a SQL query to Delete all Doctors whose Specialization is either 'Pediatrics' or 'Cardiology' and Last Name is Brown. Sample table: Doctors attributes : doctor_id, first_name, last_name, specialization

```sql
delete from Doctors where specialization in('Pediatrics','Cardiology') and last_name='Brown';
```

**Output:**

<img width="1231" height="982" alt="image" src="https://github.com/user-attachments/assets/817901f8-f1ec-452c-9753-95d3473b9ee5" />



**Question 5**

Write a SQL query to Delete customers from 'customer' table where 'CUST_CITY' is not 'New York' and 'OUTSTANDING_AMT' is greater than 5000. Sample table: Customer


```sql
delete from Customer where CUST_CITY!='New York' and OUTSTANDING_AMT>5000;
```

**Output:**

<img width="1216" height="667" alt="image" src="https://github.com/user-attachments/assets/d8f8d668-39fa-47fd-a54d-4f0fccfc4cc8" />


**Question 6**

Write a SQL query to Delete customers with 'GRADE' 3 or 'AGENT_CODE' 'A008' whose 'OUTSTANDING_AMT' is less than 5000 Sample table: Customer

```sql
delete from Customer where (GRADE=3 OR AGENT_CODE='A008') and OUTSTANDING_AMT<5000;
```

**Output:**

<img width="1237" height="491" alt="image" src="https://github.com/user-attachments/assets/10bb3d2b-18ed-4885-bae4-8d18d093551a" />


**Question 7**

Write a query to fetch last 5 rows in EmployeeInfo table.

```sql
select*from Employeeinfo order by EmpID desc limit 5;
```

**Output:**

<img width="1241" height="402" alt="image" src="https://github.com/user-attachments/assets/4656c61b-29bb-4ba6-9aa3-ed5b06517dd2" />



**Question 8**

Write a query to get all the records from EmployeePosition table who have joined in the year 2020.

```sql
select *from EmployeePosition where DateOfJoining BETWEEN '2020-01-01' AND '2020-12-31';
```

**Output:**

<img width="1147" height="360" alt="image" src="https://github.com/user-attachments/assets/6a4c770f-1154-496a-81fa-eca3e2db8ccc" />


**Question 9**

Write a SQL query to label rows in the Calculations table as 'Even' if value1 is even, otherwise 'Odd'.

```sql
SELECT id,
        value1,
        case
            when value1%2=0 then 'Even'
            ELSE 'Odd'
        end as parity
from Calculations;
```

**Output:**

<img width="955" height="559" alt="image" src="https://github.com/user-attachments/assets/2254d7d5-2c26-488f-ac47-267c5c3da0cb" />


**Question 10**

Write a query to calculate the discounted_price and discounted_price_percentage for each product from the products table. Return product_id, original_price, discount_percentage, discounted_price, and discounted_price_percentage. Discounted Price: Calculate the price of the product after applying the discount. Discounted Price Percentage: Calculate the percentage that the discounted price represents relative to the original price.

```sql
select product_id,original_price,discount_percentage,(original_price-(original_price*discount_percentage)) as discounted_price,
cast(round(((original_price-(original_price*discount_percentage))/original_price)*100,0)as int)||'%' as discounted_price_percentage
from products;
```

**Output:**

<img width="1239" height="405" alt="image" src="https://github.com/user-attachments/assets/f16543f8-d475-4c6e-8ae0-80e302d1f836" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
