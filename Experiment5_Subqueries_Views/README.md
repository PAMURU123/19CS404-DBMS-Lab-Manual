# Experiment 5: Subqueries and Views
NAME:PAMURU VENKATESH
```
REG NO.:212224040230
```
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
--
<img width="1460" height="712" alt="image" src="https://github.com/user-attachments/assets/79f7ed04-a3bd-4691-bd19-3c9be8256259" />

```sql
SELECT student_name,grade
FROM GRADES G1
WHERE grade=(SELECT MIN(grade) FROM GRADES G2 WHERE G1.subject=G2.subject);
```

**Output:**

<img width="812" height="495" alt="image" src="https://github.com/user-attachments/assets/e9509444-d473-4a41-ae02-40b7a587713d" />

**Question 2**
---
<img width="1260" height="471" alt="image" src="https://github.com/user-attachments/assets/c67b34a5-e86e-4980-8dd1-f678942b57cc" />

```sql
select department_id as depar,department_name from Departments where length(department_name)>(
select avg(length(department_name)) from Departments);
```

**Output:**

<img width="737" height="467" alt="image" src="https://github.com/user-attachments/assets/2d9790fc-2a48-469d-b1d5-3d8d6ec6bfea" />

**Question 3**
---
<img width="1308" height="747" alt="image" src="https://github.com/user-attachments/assets/77580a4d-a87f-4394-b862-fd84e94edb9e" />

```sql
SELECT *
FROM CUSTOMERS
WHERE AGE<30;
```

**Output:**

<img width="1271" height="642" alt="image" src="https://github.com/user-attachments/assets/085f778a-8824-4078-9660-cfd104c7fd87" />

**Question 4**
---
<img width="1423" height="847" alt="image" src="https://github.com/user-attachments/assets/cd795879-4b64-432c-a51d-e80187421269" />

```sql
select ord_no,purch_amt,ord_date,salesman_id
from Orders
where salesman_id in(
select salesman_id
from Salesman
where commission=(select max(commission)
from Salesman));
```

**Output:**

<img width="1030" height="530" alt="image" src="https://github.com/user-attachments/assets/0fc300e7-27b9-4b55-8b98-0cb08ed8c5c4" />

**Question 5**
---
<img width="1231" height="627" alt="image" src="https://github.com/user-attachments/assets/59363991-f6ca-4178-97b6-3e5b58a36a81" />

```sql
select *
from customers
where Address='Delhi';
```

**Output:**

<img width="1252" height="390" alt="image" src="https://github.com/user-attachments/assets/b715c5e7-6ddd-4929-a65d-7ef6546229bd" />

**Question 6**
---
<img width="1428" height="761" alt="image" src="https://github.com/user-attachments/assets/ca9ef63d-89da-4137-87b2-34ba29624369" />

```sql
SELECT*
FROM Orders
WHERE salesman_id=(SELECT salesman_id FROM Salesman WHERE NAME='Paul Adam');
```

**Output:**

<img width="1236" height="441" alt="image" src="https://github.com/user-attachments/assets/24a13011-1ca3-4282-8c27-3acf3051479e" />

**Question 7**
---
<img width="1216" height="720" alt="image" src="https://github.com/user-attachments/assets/3bb82168-bcfc-47d4-9982-2c6ee5651350" />

```sql
select * 
from customer 
where customer_id=(select salesman_id from salesman where name='Mc Lyon')-2001;
```

**Output:**

<img width="1268" height="373" alt="image" src="https://github.com/user-attachments/assets/725d56da-d239-4ec9-b11e-9b205f7b7107" />

**Question 8**
---
<img width="1317" height="623" alt="image" src="https://github.com/user-attachments/assets/19af9850-4636-43a9-99dc-628cea69dd38" />

```sql
SELECT*
FROM Employee
WHERE age<(SELECT AVG(age) FROM Employee WHERE income>1000000);
```

**Output:**
<img width="1255" height="493" alt="image" src="https://github.com/user-attachments/assets/ad1a62d7-5c0a-40c1-a282-157c96a1dab7" />


**Question 9**
---
<img width="1175" height="683" alt="image" src="https://github.com/user-attachments/assets/b279c8bc-3c48-42f1-b30f-34548259a27b" />

```sql
select * 
from customers 
where salary>4500;
```

**Output:**

<img width="1210" height="501" alt="image" src="https://github.com/user-attachments/assets/88cd3c42-9c92-4682-b9fc-7d48fc6799d2" />

**Question 10**
---
<img width="1217" height="616" alt="image" src="https://github.com/user-attachments/assets/914473b5-f972-42cf-b312-3ed003a185ff" />

```sql
select * 
from CUSTOMERS 
where salary = 1500;
```

**Output:**

<img width="1215" height="412" alt="image" src="https://github.com/user-attachments/assets/07cdf7f3-8b04-4ea9-bc38-481ca3e55fa4" />


## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
