# Experiment 6: Joins
NAME:PAMURU VENKATESH
```
REG NO.:212224040230
```
## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**
--
<img width="1392" height="647" alt="image" src="https://github.com/user-attachments/assets/7618b5e7-b04c-40fc-b6b3-df9d592f0dd7" />

```sql
SELECT c.cust_name
FROM customer c
LEFT JOIN orders o ON c.customer_id = o.customer_id;
```

**Output:**

<img width="1003" height="832" alt="image" src="https://github.com/user-attachments/assets/83f8467a-473a-48cf-87fe-04ff645aa99e" />

**Question 2**
---
<img width="1436" height="745" alt="image" src="https://github.com/user-attachments/assets/1d25d7e2-bbb3-42ea-a229-b2cb65160814" />

```sql
SELECT p.first_name as patient_name , t.test_name
FROM patients p
INNER JOIN test_results t ON p.patient_id = t.patient_id
```

**Output:**

<img width="778" height="607" alt="image" src="https://github.com/user-attachments/assets/b5d5818c-7d74-448f-90f7-781ac99b876b" />

**Question 3**
---
<img width="1418" height="803" alt="image" src="https://github.com/user-attachments/assets/84e8e262-170c-4703-90ae-455ed77fcaa0" />

```sql
SELECT p.first_name as patient_name, d.specialization as Doctor_specialization
FROM patients p
INNER JOIN doctors d ON p.doctor_id = d.doctor_id
WHERE p.admission_date BETWEEN '2024-01-01' AND '2024-01-31'
```

**Output:**

<img width="735" height="463" alt="image" src="https://github.com/user-attachments/assets/3fe0c212-83ec-4397-9455-bfeb8f95e15c" />

**Question 4**
---
<img width="1436" height="900" alt="image" src="https://github.com/user-attachments/assets/e501350e-94be-4b4b-b543-f803ed8c0532" />

```sql
SELECT a.cust_name AS "Customer Name", 
       a.city, 
       b.name AS "Salesman", 
       b.city, b.commission  
FROM customer a  
INNER JOIN salesman b  
ON a.salesman_id = b.salesman_id 
WHERE b.commission > 0.12 
AND a.city <> b.city;
```

**Output:**

<img width="1263" height="701" alt="image" src="https://github.com/user-attachments/assets/decc9378-1a8a-47af-b446-9f05ecdde9c8" />

**Question 5**
---
<img width="1376" height="801" alt="image" src="https://github.com/user-attachments/assets/55b03bc0-e375-4dac-9a21-fd53d80261e5" />

```sql
SELECT p.*
FROM patients p 
INNER JOIN doctors d ON p.doctor_id = d.doctor_id
WHERE d.first_name = 'John' AND d.last_name = 'Smith'
```

**Output:**

<img width="1248" height="472" alt="image" src="https://github.com/user-attachments/assets/2c473c5d-f8f8-4b1b-8b04-15dbcbd3e14f" />

**Question 6**
---
<img width="1441" height="495" alt="image" src="https://github.com/user-attachments/assets/55d72789-43b6-4841-86d7-e6f3c52b9009" />

```sql
SELECT c.*
FROM customer c
LEFT JOIN orders o
ON c.customer_id = o.customer_id
WHERE o.ord_date > '2012-08-17';
```

**Output:**

<img width="1246" height="916" alt="image" src="https://github.com/user-attachments/assets/5d751a8b-f898-4e2f-986b-f3c621841ead" />

**Question 7**
---
<img width="1442" height="832" alt="image" src="https://github.com/user-attachments/assets/f050d011-a765-4dbb-abba-1c7541e71d52" />

```sql
SELECT 
    a.ord_no, 
    a.ord_date, 
    a.purch_amt, 
    b.cust_name AS "Customer Name", 
    b.grade, 
    c.name AS "Salesman", 
    c.commission
FROM 
    orders a
INNER JOIN 
    customer b ON a.customer_id = b.customer_id
INNER JOIN 
    salesman c ON a.salesman_id = c.salesman_id;
```

**Output:**

<img width="1257" height="872" alt="image" src="https://github.com/user-attachments/assets/eab3d4e3-7caa-495b-bb28-b369d0ef6884" />

**Question 8**
---
<img width="1257" height="901" alt="image" src="https://github.com/user-attachments/assets/f35877b5-042c-406f-b63f-b64b2b4eff25" />

```sql
SELECT salesman.name AS "Salesman", customer.cust_name, customer.city
FROM salesman
JOIN customer ON salesman.city = customer.city;
```

**Output:**

<img width="1040" height="752" alt="image" src="https://github.com/user-attachments/assets/420e68a4-e4c8-4efd-98c0-06fce0daf0ea" />

**Question 9**
---
<img width="1445" height="937" alt="image" src="https://github.com/user-attachments/assets/d0ca4440-ec47-4d61-a828-732421080be7" />

```sql
SELECT 
    c.cust_name,
    c.city,
    o.ord_no,
    o.ord_date,
    o.purch_amt AS "Order Amount"
FROM
    customer c
LEFT JOIN
    orders o
ON
    c.customer_id = o.customer_id
ORDER BY
    o.ord_date ASC;
```

**Output:**

<img width="1252" height="876" alt="image" src="https://github.com/user-attachments/assets/9cebe560-ed4c-4864-a34f-66cb9e97917e" />

**Question 10**
---
<img width="1442" height="951" alt="image" src="https://github.com/user-attachments/assets/1d252e23-d18f-4947-b7d3-85335aa6dd4d" />

```sql
SELECT
    a.cust_name,
    a.city,
    a.grade,
    b.name AS "Salesman",
    b.city
FROM 
    customer a
INNER JOIN
    salesman b
ON
    a.salesman_id = b.salesman_id
ORDER BY
    a.customer_id ASC;
```

**Output:**

<img width="1252" height="926" alt="image" src="https://github.com/user-attachments/assets/1bb7682c-1f42-440b-aaeb-956793906700" />


## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
