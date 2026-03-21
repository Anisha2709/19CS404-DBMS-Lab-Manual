# Experiment 6: Joins

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
<img width="1116" height="695" alt="image" src="https://github.com/user-attachments/assets/32e4e07f-5034-4840-b8fe-de19482c2634" />

```sql
SELECT 
    c.cust_name,
    c.city,
    o.ord_no,
    o.ord_date,
    o.purch_amt AS "Order Amount",
    s.name,
    s.commission
FROM customer c
LEFT JOIN orders o 
    ON c.customer_id = o.customer_id
LEFT JOIN salesman s 
    ON c.salesman_id = s.salesman_id;
```

**Output:**

<img width="1121" height="578" alt="image" src="https://github.com/user-attachments/assets/2630ad0b-a034-4ae8-bdb5-61baaaea9b64" />


**Question 2**
---
<img width="1118" height="705" alt="image" src="https://github.com/user-attachments/assets/95221957-53cf-4aa2-b3e3-7dd4999b14bf" />


```sql
SELECT 
    o.ord_no,
    o.ord_date,
    o.purch_amt,
    c.cust_name AS "Customer Name",
    c.grade,
    s.name AS "Salesman",
    s.commission
FROM orders o
JOIN customer c 
    ON o.customer_id = c.customer_id
JOIN salesman s 
    ON o.salesman_id = s.salesman_id;
```

**Output:**

<img width="1120" height="574" alt="image" src="https://github.com/user-attachments/assets/0907232d-0104-46a1-aa04-0aba832922ef" />


**Question 3**
---
<img width="1113" height="567" alt="image" src="https://github.com/user-attachments/assets/86929ecf-acc1-4089-aeb8-360bc064ccd5" />


```sql
SELECT 
    c.cust_name,
    c.city,
    o.ord_no,
    o.ord_date,
    o.purch_amt as  "Order Amount"
FROM customer c
LEFT JOIN orders o
    ON c.customer_id = o.customer_id
ORDER BY o.ord_date ASC;
```

**Output:**

<img width="1112" height="579" alt="image" src="https://github.com/user-attachments/assets/7a6eed05-7a70-4fdf-b7b2-4b3027136246" />

**Question 4**
---
<img width="1118" height="470" alt="image" src="https://github.com/user-attachments/assets/b5e4f800-f73c-4720-9022-1091111d77cf" />

```sql
SELECT 
    o.ord_no,
    o.purch_amt,
    c.cust_name,
    c.city
FROM orders o
JOIN customer c
    ON o.customer_id = c.customer_id
WHERE o.purch_amt BETWEEN 500 AND 2000;
```

**Output:**

<img width="1099" height="230" alt="image" src="https://github.com/user-attachments/assets/59fa5265-2df8-4d50-b0c2-7663a8656b6c" />

**Question 5**
---
<img width="1097" height="430" alt="image" src="https://github.com/user-attachments/assets/c5a01c13-6be2-4ab5-8f99-f96417356161" />

```sql
SELECT 
    s.name AS Salesman,
    c.cust_name,
    c.city
FROM salesman s
JOIN customer c
    ON s.city = c.city;
```

**Output:**

<img width="1138" height="328" alt="image" src="https://github.com/user-attachments/assets/4dda0357-842d-4366-bfa3-0e2d86a3c45d" />

**Question 6**
---
<img width="1117" height="366" alt="image" src="https://github.com/user-attachments/assets/009ca681-21a9-4951-9480-18983b159b02" />


```sql
SELECT 
    p.first_name,
    p.last_name
FROM patients p
INNER JOIN surgeries s
    ON p.patient_id = s.patient_id
WHERE s.surgery_date BETWEEN '2024-01-01' AND '2024-01-31';
```

**Output:**

<img width="1126" height="190" alt="image" src="https://github.com/user-attachments/assets/501e0f75-27a7-457b-9bb4-75b1e2a6eaf7" />

**Question 7**
---
<img width="1100" height="354" alt="image" src="https://github.com/user-attachments/assets/3bccb60d-0eda-479d-9915-98e245847549" />

```sql
SELECT 
    p.*
FROM patients p
INNER JOIN doctors d
    ON p.doctor_id = d.doctor_id
WHERE d.first_name = 'John'
  AND d.last_name = 'Smith';
```

**Output:**

<img width="1116" height="188" alt="image" src="https://github.com/user-attachments/assets/ea967439-3b08-4ac1-a990-18c8632afc11" />

**Question 8**
---
<img width="1119" height="172" alt="image" src="https://github.com/user-attachments/assets/9a5ce9a3-86d9-4704-aa12-bf2f9351c9d0" />


```sql
SELECT 
    c.*
FROM customer c
LEFT JOIN salesman s
    ON c.salesman_id = s.salesman_id
WHERE s.name = 'Mc Lyon';
```

**Output:**
<img width="1128" height="221" alt="image" src="https://github.com/user-attachments/assets/abd9e40e-eca4-4016-acb6-dbcabbf0c4f6" />


**Question 9**
---
<img width="1128" height="396" alt="image" src="https://github.com/user-attachments/assets/5d3ae85e-1d13-40ab-9ccf-7ffe38282815" />


```sql
SELECT 
    p.first_name
FROM patients p
INNER JOIN surgeries s
    ON p.patient_id = s.patient_id
WHERE s.surgery_date = '2024-01-15';
```

**Output:**

<img width="1119" height="232" alt="image" src="https://github.com/user-attachments/assets/50f39fa6-fd4b-40d7-af74-26c1d2c6c8b5" />


**Question 10**
---
<img width="1114" height="332" alt="image" src="https://github.com/user-attachments/assets/0967161e-3628-4060-8764-dedbf3d7893e" />


```sql
SELECT 
    c.cust_name
FROM customer c
LEFT JOIN orders o
    ON c.customer_id = o.customer_id;
```

**Output:**

<img width="1111" height="613" alt="image" src="https://github.com/user-attachments/assets/36560d4f-8d8f-4835-949e-56a6deb3bd31" />


## Screenshot of Module 5 SEB Completion Grades
<img width="1001" height="46" alt="image" src="https://github.com/user-attachments/assets/e6c4c542-7542-4432-bc09-dc1166527c3f" />


## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
