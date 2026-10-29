# ER Diagram Workshop – Submission Template

## Objective
To understand and apply ER modeling concepts by creating ER diagrams for real-world applications.

## Purpose
Gain hands-on experience in designing ER diagrams that represent database structure including entities, relationships, attributes, and constraints.

---

# Scenario A: City Fitness Club Management

**Business Context:**  
FlexiFit Gym wants a database to manage its members, trainers, and fitness programs.

**Requirements:**  
- Members register with name, membership type, and start date.  
- Each member can join multiple programs (Yoga, Zumba, Weight Training).  
- Trainers assigned to programs; a program may have multiple trainers.  
- Members may book personal training sessions with trainers.  
- Attendance recorded for each session.  
- Payments tracked for memberships and sessions.

### ER Diagram:
*Paste or attach your diagram here*  
![ER Diagram](er_diagram_fitness.png)

### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|              |            |               |       |
|              |            |               |       |
|              |            |               |       |

### Assumptions
- 
- 
- 

---

# Scenario B: City Library Event & Book Lending System

**Business Context:**  
The Central Library wants to manage book lending and cultural events.

**Requirements:**  
- Members borrow books, with loan and return dates tracked.  
- Each book has title, author, and category.  
- Library organizes events; members can register.  
- Each event has one or more speakers/authors.  
- Rooms are booked for events and study.  
- Overdue fines apply for late returns.

### ER Diagram:
*Paste or attach your diagram here*  
![ER Diagram](er_diagram_library.png)

### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|              |            |               |       |
|              |            |               |       |
|              |            |               |       |

### Assumptions
- 
- 
- 

---

# Scenario C: Restaurant Table Reservation & Ordering

**Business Context:**  
A popular restaurant wants to manage reservations, orders, and billing.

**Requirements:**  
- Customers can reserve tables or walk in.  
- Each reservation includes date, time, and number of guests.  
- Customers place food orders linked to reservations.  
- Each order contains multiple dishes; dishes belong to categories (starter, main, dessert).  
- Bills generated per reservation, including food and service charges.  
- Waiters assigned to serve reservations.

### ER Diagram:
*Paste or attach your diagram here*  
<img width="1682" height="642" alt="image" src="https://github.com/user-attachments/assets/7c53c377-21ed-4b11-874c-3a43eab9b1b7" />

### Entities and Attributes

| Entity      | Attributes (PK, FK)                                                                | Notes                      |
| ----------- | ------------------------------------------------                                   | -------------------------- |
| Customer    | **Customer_ID (PK)**, Name, Contact Details, Table Number                             | Stores customer details    |
| Chef        | **Chef_ID (PK)**, Name, Contact Details                                            | Stores reservation details |
| Order       | **Order_ID (PK)**, Date Time, Total Amount , Status                                | Stores food order details  |
| Food Item   | **Dish_ID (PK)**, Name, Category, Price                                            | Stores menu information    |
| Waiter      | **Waiter_ID (PK)**, Name, Contact Details                                          | Stores waiter details      
| Table       | **Table_ID (PK)**, Location, Status                                                | Stores customer details    |
| OrderItem   | **OrderItem_ID (PK)**, **Order_ID (FK)**, **FoodItem_ID (FK)**,Quantity, Status    | Stores reservation details |
| Bill        | **Bill_ID (PK)**,  **Order_ID (FK)**, Total Amount, Payment Status                 | Stores food order details  |
| Supervisor  | **Supervisor_ID (PK)**, Name, Contact Details                                      | Stores menu information    |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
| Customer - Table (Has) | Many-to-One | Customer: Total; Table: Partial | A customer is assigned to one table |
| Waiter - Table (Serves) | One-to-Many | Waiter: Partial; Table: Total | A waiter serves multiple tables |
| Waiter - Order (Creates) | One-to-Many | Waiter: Partial; Order: Total | A waiter creates multiple orders |
| Order - Table (Belongs to) | Many-to-One | Order: Total; Table: Partial | An order belongs to one table |
| Order - OrderItem (Contains) | One-to-Many | Both: Total | An order contains multiple order items |
| OrderItem - FoodItem (Refers to) | Many-to-One | OrderItem: Total; FoodItem: Partial | Each order item refers to one food item |
| Order - Bill (Generates) | One-to-One | Order: Partial; Bill: Total | A bill is generated for one order |
| Chef - OrderItem (Prepares) | One-to-Many | Chef: Partial; OrderItem: Total | A chef prepares multiple order items |
| Supervisor - Order (Manages) | One-to-Many | Supervisor: Partial; Order: Partial | A supervisor manages exceptional order cases |
### Assumptions
- Each entity has a unique primary key.
- Foreign keys maintain relationships between entities.
- Each customer is assigned to one table.
- Each order is created by one waiter and belongs to one table.
- Each order contains multiple order items.
- Each order item refers to one food item.
- Each order can have one bill.
- Each order item is prepared by one chef.
- A supervisor oversees exceptional order cases when necessary.### Entities and Attributes

---

## Instructions for Students

1. Complete **all three scenarios** (A, B, C).  
2. Identify entities, relationships, and attributes for each.  
3. Draw ER diagrams using **draw.io / diagrams.net** or hand-drawn & scanned.  
4. Fill in all tables and assumptions for each scenario.  
5. Export the completed Markdown (with diagrams) as **a single PDF**
