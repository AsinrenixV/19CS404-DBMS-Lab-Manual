# Experiment 5: Subqueries and Views

## NAME : ASIN RENIX V
## REG NO : 212224040036

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**

<img width="1297" height="684" alt="image" src="https://github.com/user-attachments/assets/d07358d1-980a-4804-9c69-4c1e07999ccf" />


```sql
SELECT ord_no, purch_amt, ord_date, customer_id, o.salesman_id
FROM orders o
JOIN salesman s ON o.salesman_id = s.salesman_id
WHERE s.name = 'Paul Adam';

```

**Output:**

<img width="1290" height="357" alt="image" src="https://github.com/user-attachments/assets/5c8c32eb-b39b-42b9-8368-7caebd233f9b" />


**Question 2**

<img width="1287" height="571" alt="image" src="https://github.com/user-attachments/assets/59cb84ae-2f41-428b-be76-058f334677dd" />


```sql
SELECT 
    student_id,
    student_name,
    subject,
    grade
FROM 
    Grades
WHERE 
    grade = (
        SELECT MIN(g2.grade)
        FROM Grades g2
        WHERE g2.subject = Grades.subject
    );

```

**Output:**

<img width="1292" height="405" alt="image" src="https://github.com/user-attachments/assets/27037b76-1be2-4feb-9e18-4b6bacc67455" />


**Question 3**

<img width="1072" height="458" alt="image" src="https://github.com/user-attachments/assets/00d1b7ed-e897-4f5e-bd6a-8f02c19728c1" />


```sql
SELECT medication_id AS medic, medication_name, dosage
FROM Medications
WHERE dosage = (SELECT MIN(dosage) FROM Medications);

```

**Output:**

<img width="1295" height="373" alt="image" src="https://github.com/user-attachments/assets/5331ccc9-02f4-4662-abe6-b95a025a559c" />


**Question 4**


<img width="1271" height="460" alt="image" src="https://github.com/user-attachments/assets/ec2fa53a-7485-440e-bf69-dac86d79af7a" />


```sql
SELECT medication_id AS medic, medication_name, dosage
FROM Medications
WHERE dosage = (SELECT MAX(dosage) FROM Medications);

```

**Output:**


<img width="1289" height="368" alt="image" src="https://github.com/user-attachments/assets/e1492e51-3c2f-4bc6-ad49-17f0d61293d7" />


**Question 5**


<img width="1283" height="496" alt="image" src="https://github.com/user-attachments/assets/17a85e06-fe1b-4c59-9ec3-9d9a1f19820d" />


```sql
WHERE city != (SELECT city FROM customer WHERE id = (SELECT MAX(id) FROM customer));
```

**Output:**


<img width="1290" height="449" alt="image" src="https://github.com/user-attachments/assets/8541e443-2517-4fa4-b4e0-499852d39f7d" />


**Question 6**


<img width="1291" height="583" alt="image" src="https://github.com/user-attachments/assets/27b14102-c386-4d2f-a480-99a9965c6409" />


```sql
SELECT * FROM CUSTOMERS WHERE SALARY=1500;

```

**Output:**


<img width="1287" height="309" alt="image" src="https://github.com/user-attachments/assets/a076b899-8f3e-4f11-a0ad-72ad0434082d" />


**Question 7**


<img width="1283" height="655" alt="image" src="https://github.com/user-attachments/assets/02fa02d4-bc02-4674-9f4b-9ab68fe0d879" />


```sql
SELECT ord_no, purch_amt, ord_date, customer_id, o.salesman_id
FROM orders o
JOIN salesman s ON o.salesman_id = s.salesman_id
WHERE s.city = 'London';

```

**Output:**


<img width="1292" height="378" alt="image" src="https://github.com/user-attachments/assets/0d4e1953-0ee4-493f-867e-6755510b8024" />


**Question 8**


<img width="1290" height="491" alt="image" src="https://github.com/user-attachments/assets/827749e4-5497-4fe8-9fa1-211ffef64177" />


```sql
SELECT name, city
FROM customer
WHERE city IN (SELECT city FROM customer WHERE id=3 OR id=7);

```

**Output:**


<img width="1292" height="421" alt="image" src="https://github.com/user-attachments/assets/4e942598-89a6-4c00-acd5-ed338ae3cc7c" />


**Question 9**


<img width="1287" height="571" alt="image" src="https://github.com/user-attachments/assets/c747459e-f15d-48de-8ab1-a47a3d8c483f" />


```sql
SELECT * 
FROM Grades
WHERE grade = (SELECT MAX(grade) FROM Grades g2 WHERE g2.subject = Grades.subject);

```

**Output:**


<img width="1288" height="405" alt="image" src="https://github.com/user-attachments/assets/d052276a-3cdc-4e9e-8f23-ff8d7bd705b5" />


**Question 10**


<img width="1286" height="613" alt="image" src="https://github.com/user-attachments/assets/2c0ea3fc-06f6-496e-b9a5-207fff224ffb" />


```sql
SELECT * FROM CUSTOMERS WHERE SALARY>4500;

```

**Output:**

<img width="1293" height="402" alt="image" src="https://github.com/user-attachments/assets/98429cb5-bc2f-46cc-a473-01eea2996f8d" />

## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.


## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
