# Experiment 4: Aggregate Functions, Group By and Having Clause

## NAME : ASIN RENIX V
## REG NO : 212224040036

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**

<img width="1023" height="512" alt="image" src="https://github.com/user-attachments/assets/02878034-e5e8-40ed-ad04-dd33ca2be907" />


```sql
SELECT 
  T.ValidityYear,
  COUNT(DISTINCT T.PatientId) AS TotalPatients
FROM
  (
    SELECT
      PatientId,
      CAST(SUBSTR(ValidityPeriod, 1, 4) AS INT) AS ValidityYear
    FROM
      Insurance
  ) AS T
GROUP BY
  T.ValidityYear
ORDER BY
  T.ValidityYear;
```

**Output:**

<img width="1240" height="352" alt="image" src="https://github.com/user-attachments/assets/3cb9cb65-4bde-4f13-905a-fd8f137c76b4" />


**Question 2**

<img width="1240" height="542" alt="image" src="https://github.com/user-attachments/assets/8fc83caa-87d7-4959-8fcd-15b1eba9e48d" />


```sql
select Specialty,
count(DoctorID) AS TotalDoctors
FROM Doctors
GROUP BY Specialty;
```

**Output:**

<img width="1257" height="622" alt="image" src="https://github.com/user-attachments/assets/06889e49-8e78-4b59-aea8-8eeabe35818e" />

**Question 3**

<img width="1242" height="443" alt="image" src="https://github.com/user-attachments/assets/d24eff24-0b21-4e84-8498-916dee89cd7a" />


```sql
SELECT
  strftime('%Y-%m', Date) AS Month,
  COUNT(RecordID) AS TotalRecords
FROM
  MedicalRecords
GROUP BY
  Month;
```

**Output:**

<img width="1245" height="402" alt="image" src="https://github.com/user-attachments/assets/10a53896-15df-4c9e-b090-95eeb1a83b9e" />


**Question 4**

<img width="1189" height="431" alt="image" src="https://github.com/user-attachments/assets/5d9f6e28-e0a5-4948-86a5-ec63bfbb7f9f" />


```sql
SELECT AVG(LENGTH(email)) AS avg_email_length
FROM customer;
```

**Output:**

<img width="1249" height="293" alt="image" src="https://github.com/user-attachments/assets/443e1d65-ad33-4380-bc27-a92760f45c5e" />


**Question 5**

<img width="1234" height="504" alt="image" src="https://github.com/user-attachments/assets/9f6efe12-3e39-4d4a-9201-cafeb08560c0" />


```sql
SELECT SUM(inventory) AS total_available_amount
FROM fruits
WHERE price > 0.5;
```

**Output:**

<img width="1256" height="295" alt="image" src="https://github.com/user-attachments/assets/b3a450b4-4c69-4c2f-9dff-95c6363cfe85" />


**Question 6**

<img width="1238" height="462" alt="image" src="https://github.com/user-attachments/assets/a4e85ca9-0c8e-4ac4-9c31-75e0954997df" />


```sql
SELECT COUNT(*) AS employees_in_california FROM employee WHERE city = 'California';
```

**Output:**

<img width="1243" height="293" alt="image" src="https://github.com/user-attachments/assets/3159540e-c78d-452e-a8a9-5fccc0348b5f" />


**Question 7**

<img width="1238" height="425" alt="image" src="https://github.com/user-attachments/assets/f0108e1b-7a65-4845-a93c-87c9be2ee315" />


```sql
SELECT COUNT(*) AS employees_count FROM employee WHERE income > 50000;
```

**Output:**

<img width="1250" height="295" alt="image" src="https://github.com/user-attachments/assets/0e4350f2-5228-4d8f-bec6-34713864bf05" />


**Question 8**

<img width="1244" height="495" alt="image" src="https://github.com/user-attachments/assets/5519033a-40ba-48a0-af23-42c0edff1476" />


```sql
SELECT age, Income
AS Income
FROM employee
GROUP BY age
HAVING MIN(Income) < 1000000;
```

**Output:**

<img width="1246" height="404" alt="image" src="https://github.com/user-attachments/assets/fd50cf5e-f9f6-4028-96d5-ef877bf91f4e" />


**Question 9**

<img width="1236" height="522" alt="image" src="https://github.com/user-attachments/assets/3c44d87f-799f-46b6-9818-4160d7b71233" />


```sql
SELECT address, AVG(salary)
FROM customer1
GROUP BY address
HAVING AVG(salary) < 15000;
```

**Output:**

<img width="1248" height="561" alt="image" src="https://github.com/user-attachments/assets/7ec60375-52b6-4080-b4b3-dd3837b51d98" />


**Question 10**

<img width="1235" height="501" alt="image" src="https://github.com/user-attachments/assets/dfa74a98-ae18-4267-b2c8-5d351bbe7711" />


```sql
SELECT occupation, MIN(workhour)
FROM employee1
GROUP BY occupation
HAVING MIN(workhour) > 8;
```

**Output:**

<img width="1248" height="450" alt="image" src="https://github.com/user-attachments/assets/4efd6014-bf37-4d28-815c-324929c98395" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
