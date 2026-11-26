# Experiment 3: DML Commands
NAME:PAMURU VENKATESH
```
REG.NO:212224040230
```
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
--
<img width="1230" height="782" alt="image" src="https://github.com/user-attachments/assets/cb047c00-3c29-4a2a-8c86-f1bfe77b7698" />


```sql
UPDATE products   
SET sell_price = ROUND(cost_price * (100 + 35) / 100)
WHERE (sell_price - cost_price) / sell_price * 100 < 30;
```

**Output:**

<img width="1217" height="566" alt="image" src="https://github.com/user-attachments/assets/99aa7cab-b8c2-46c8-98ad-c9ac73d7195b" />


**Question 2**
---
<img width="1128" height="552" alt="image" src="https://github.com/user-attachments/assets/aa11c920-86b1-457f-878b-5e5acd79919a" />

```sql
update products
set category='Household'
where product_name like '%Detergent%';
```

**Output:**

<img width="1215" height="572" alt="image" src="https://github.com/user-attachments/assets/1f5250fd-5904-46fb-9b49-4f3140f2a123" />


**Question 3**
---
<img width="1308" height="336" alt="image" src="https://github.com/user-attachments/assets/e59a3cd2-e987-4eb8-9a4f-3cec00e443ed" />

```sql
update suppliers
set supplier_name='A1 Suppliers'
where supplier_id like '%8%';
```

**Output:**
<img width="1237" height="492" alt="image" src="https://github.com/user-attachments/assets/8b0db813-330c-4be0-8f45-28150baed93e" />


**Question 4**
---
<img width="1118" height="120" alt="image" src="https://github.com/user-attachments/assets/35ec3428-a7cf-418e-a146-949bc04b348f" />


```sql
UPDATE Customer
SET grade = 5
WHERE city = 'Chennai';
```

**Output:**

<img width="1222" height="541" alt="image" src="https://github.com/user-attachments/assets/188caeb2-bfb7-4924-bc1d-67db07acb88c" />


**Question 5**
---
<img width="1395" height="642" alt="image" src="https://github.com/user-attachments/assets/d0d8bcbb-1344-458b-878d-e62659551545" />

```sql
UPDATE products
SET reorder_lvl = reorder_lvl * 0.7
WHERE product_name LIKE '%cream%'
AND quantity > reorder_lvl;
```

**Output:**

<img width="1216" height="575" alt="image" src="https://github.com/user-attachments/assets/ce50048e-9a8b-449c-ae78-191c35cef16f" />


**Question 6**
---
<img width="1406" height="527" alt="image" src="https://github.com/user-attachments/assets/67938b1c-3e7a-4360-ac11-f7492230033d" />


```sql
DELETE FROM customer
WHERE cust_city != 'New York'
  AND outstanding_amt > 5000;
```

**Output:**

<img width="1233" height="601" alt="image" src="https://github.com/user-attachments/assets/aaad5b98-d30a-4a71-aa63-563573d5870a" />


**Question 7**
---
<img width="1430" height="510" alt="image" src="https://github.com/user-attachments/assets/b000399f-10e2-419b-8c1e-d0aa4f02ed31" />

```sql
DELETE FROM Customer
WHERE GRADE % 2 != 0;
```

**Output:**

<img width="1220" height="545" alt="image" src="https://github.com/user-attachments/assets/14daa26b-95ad-476a-9dd5-25cba92ed660" />


**Question 8**
---
<img width="1407" height="488" alt="image" src="https://github.com/user-attachments/assets/ac324200-1645-4aa2-a302-79fcfb05710a" />

```sql
delete from Customer
where CUST_COUNTRY='UK'
AND WORKING_AREA='London'
and GRADE < 3;
```

**Output:**
<img width="1216" height="550" alt="image" src="https://github.com/user-attachments/assets/07693b84-002e-4025-b116-4de33d7758cb" />



**Question 9**
---
<img width="1410" height="480" alt="image" src="https://github.com/user-attachments/assets/569e7848-7d3f-42ef-b164-42e116809d15" />

```sql
DELETE FROM Customer
WHERE CUST_COUNTRY NOT IN ('India', 'USA');
```

**Output:**
<img width="1217" height="612" alt="image" src="https://github.com/user-attachments/assets/63f7cf9b-135d-4e11-b370-f335f64c2751" />


**Question 10**
---
<img width="1403" height="513" alt="image" src="https://github.com/user-attachments/assets/1124c30c-264c-44de-baa7-92a7ee321e28" />

```sql
DELETE FROM Customer
WHERE (GRADE = 3 OR AGENT_CODE = 'A008') AND OUTSTANDING_AMT < 5000;
```

**Output:**

<img width="1231" height="462" alt="image" src="https://github.com/user-attachments/assets/541bf617-42e3-4851-9416-43ab537d5f94" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
