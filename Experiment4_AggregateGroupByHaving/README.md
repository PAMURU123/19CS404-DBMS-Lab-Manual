# Experiment 4: Aggregate Functions, Group By and Having Clause
NAME:PAMURU VENKATESH
```
REG NO.:212224040230
```
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
--
-- <img width="1302" height="565" alt="image" src="https://github.com/user-attachments/assets/11f4c2f2-deac-404d-9027-5b003eae9760" />


```sql
SELECT DoctorID,COUNT(*) AS TotalAppointments
FROM Appointments
GROUP BY DoctorID;
```

**Output:**

<img width="1012" height="710" alt="image" src="https://github.com/user-attachments/assets/7751819f-026b-4314-b030-26c18bc2b9c0" />

**Question 2**
---
<img width="1335" height="590" alt="image" src="https://github.com/user-attachments/assets/cf9bd070-6ab2-4f7d-82fe-f93a9a089703" />


```sql
SELECT Frequency,COUNT(*) AS TotalPrescriptions
FROM Prescriptions
GROUP BY Frequency;
```

**Output:**

<img width="1105" height="607" alt="image" src="https://github.com/user-attachments/assets/f26cc0f3-a9a6-489b-b4a5-b865d071a472" />

**Question 3**
---
<img width="1236" height="543" alt="image" src="https://github.com/user-attachments/assets/474e8426-d00f-4cd7-b1e5-406ece1c0b87" />

```sql
select DoctorID ,count(DoctorID) as   TotalRecords
from MedicalRecords
group by DoctorID;
```

**Output:**

<img width="852" height="675" alt="image" src="https://github.com/user-attachments/assets/a5b31ea9-14ec-471d-9afc-d7efac57064e" />

**Question 4**
---
<img width="1165" height="492" alt="image" src="https://github.com/user-attachments/assets/6623fc1a-8cac-49de-a993-b3a740aa712b" />

```sql
SELECT AVG(LENGTH(email)) AS avg_email_length
FROM customer;
```

**Output:**

<img width="715" height="391" alt="image" src="https://github.com/user-attachments/assets/c53f6e08-9b02-46cc-96c8-9e793f26e90d" />

**Question 5**
---
<img width="1007" height="483" alt="image" src="https://github.com/user-attachments/assets/b3231264-84a0-4e00-b5a6-920e87e26a57" />

```sql
SELECT SUM(income) AS total_income
FROM employee
WHERE age >= 40;
```

**Output:**

<img width="567" height="382" alt="image" src="https://github.com/user-attachments/assets/cd505748-19ff-499f-9793-045f406da315" />

**Question 6**
---
<img width="1293" height="527" alt="image" src="https://github.com/user-attachments/assets/04ea7b2f-fe0c-4c01-9490-8bcc6210585d" />

```sql
select count(*) as COUNT
from customer;
```

**Output:**

<img width="423" height="372" alt="image" src="https://github.com/user-attachments/assets/64bb67d0-d466-4864-b2ed-c83161562482" />

**Question 7**
---
<img width="1003" height="477" alt="image" src="https://github.com/user-attachments/assets/fd5f9145-35f4-4646-8398-eacb656547ae" />

```sql
select name, email, min(length(email)) as min_email_length
from customer;
```

**Output:**

<img width="1178" height="377" alt="image" src="https://github.com/user-attachments/assets/83d55cbb-8a08-45e0-ac1a-41274c44ffbd" />

**Question 8**
---
<img width="1403" height="502" alt="image" src="https://github.com/user-attachments/assets/400981a9-9258-419c-b521-161bb6981489" />

```sql
SELECT category_id, COUNT(*) AS COUNT
FROM products
WHERE category_id > 2
GROUP BY category_id;
```

**Output:**

<img width="738" height="396" alt="image" src="https://github.com/user-attachments/assets/c0db335d-bc22-4912-9383-13d0399fa821" />

**Question 9**
---
<img width="1181" height="603" alt="image" src="https://github.com/user-attachments/assets/e9e75e19-0978-4ca5-8b8e-e70d8bb2ce3a" />

```sql
SELECT address,AVG(salary)
FROM customer1
group by address
HAVING AVG(salary)<15000;
```

**Output:**

<img width="755" height="677" alt="image" src="https://github.com/user-attachments/assets/83e7ed02-763f-4d76-ab97-26bc49039c73" />

**Question 10**
---
<img width="1405" height="497" alt="image" src="https://github.com/user-attachments/assets/55208235-4111-4160-9923-67aca33bd90b" />

```sql
SELECT category_id, AVG(Price)
FROM products
GROUP BY category_id
HAVING AVG(Price) BETWEEN 10 AND 15;
```

**Output:**

<img width="762" height="410" alt="image" src="https://github.com/user-attachments/assets/e5b49e77-312c-4d72-b8ac-4fb593db2f8e" />


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
