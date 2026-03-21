# Experiment 5: Subqueries and Views

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
<img width="1041" height="518" alt="image" src="https://github.com/user-attachments/assets/cc9005d1-201c-4dd9-8081-0d5171998fcc" />

```sql
SELECT ord_no,
       purch_amt,
       ord_date,
       customer_id,
       salesman_id
FROM ORDERS
WHERE salesman_id IN (
        SELECT salesman_id
        FROM SALESMAN
        WHERE city = 'New York'
);
```

**Output:**

<img width="859" height="330" alt="image" src="https://github.com/user-attachments/assets/a82c5afc-01c6-4219-b0c8-29edb59de088" />


**Question 2**
---
<img width="744" height="448" alt="image" src="https://github.com/user-attachments/assets/397a436a-4e32-4697-8bff-df87f64a4766" />


```sql
SELECT id,
       name,
       age,
       city,
       income
FROM Employee
WHERE age < (
        SELECT AVG(age)
        FROM Employee
        WHERE income > 250000
);
```

**Output:**

<img width="947" height="360" alt="image" src="https://github.com/user-attachments/assets/bfdfc461-c5f3-403f-b24e-5468ec0fbd28" />


**Question 3**
---
<img width="1117" height="362" alt="image" src="https://github.com/user-attachments/assets/52303e36-68b1-436f-a3ba-064a437c1e5c" />


```sql
SELECT ord_no,
       purch_amt,
       ord_date,
       customer_id,
       salesman_id
FROM orders
WHERE salesman_id = (
        SELECT salesman_id
        FROM orders
        WHERE customer_id = 3007
);
```

**Output:**

<img width="862" height="280" alt="image" src="https://github.com/user-attachments/assets/adb2a075-7095-4d44-9835-2cfb6ac18257" />


**Question 4**
---
<img width="753" height="359" alt="image" src="https://github.com/user-attachments/assets/2befd88a-505a-4ff3-acad-b979bcafe1cb" />


```sql
SELECT id,
       name,
       city,
       email,
       phone
FROM customer
WHERE city <> (
        SELECT city
        FROM customer
        WHERE id = (SELECT MAX(id) FROM customer)
);
```

**Output:**

<img width="953" height="328" alt="image" src="https://github.com/user-attachments/assets/10609c5d-b156-4c9b-ae5b-e3d128ed0b5c" />


**Question 5**
---
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/eaaa7160-eb08-49d8-bfb2-b8f20fa0ac49" />


```sql
SELECT ord_no,
       purch_amt,
       ord_date,
       salesman_id
FROM orders
WHERE salesman_id IN (
        SELECT salesman_id
        FROM salesman
        WHERE commission = (
                SELECT MAX(commission)
                FROM salesman
        )
);
```

**Output:**

<img width="815" height="317" alt="image" src="https://github.com/user-attachments/assets/ff417e4f-94c4-4f28-83ed-9b7aa663ff82" />


**Question 6**
---
<img width="896" height="416" alt="image" src="https://github.com/user-attachments/assets/cffbde7d-3aa1-46fb-bbb4-696dd31fbd72" />


```sql
SELECT student_name,
       grade
FROM GRADES g1
WHERE grade = (
        SELECT MAX(g2.grade)
        FROM GRADES g2
        WHERE g2.subject = g1.subject
);
```

**Output:**

<img width="544" height="293" alt="image" src="https://github.com/user-attachments/assets/dcda02a6-a329-47df-9ba7-96dc2bcf4704" />


**Question 7**
---
<img width="961" height="323" alt="image" src="https://github.com/user-attachments/assets/8fe8bcd4-3761-435a-b711-fec6366012ca" />


```sql
SELECT grade, COUNT(*)
FROM customer
WHERE grade > (
        SELECT AVG(grade)
        FROM customer
        WHERE city = 'New York'
)
GROUP BY grade;
```

**Output:**

<img width="582" height="226" alt="image" src="https://github.com/user-attachments/assets/3993e37a-8ee6-433b-8cee-b7e1b3bb1d91" />

**Question 8**
---
<img width="694" height="520" alt="image" src="https://github.com/user-attachments/assets/6a070cf4-fcc5-4ee2-86ac-ad16cf3c5373" />


```sql
SELECT *
FROM CUSTOMERS
WHERE AGE < 30;
```

**Output:**

<img width="847" height="359" alt="image" src="https://github.com/user-attachments/assets/f8706398-7321-4310-a015-75861cd1a222" />

**Question 9**
---
<img width="776" height="459" alt="image" src="https://github.com/user-attachments/assets/21fb2682-d010-4fbc-a330-763b8fb0fe50" />

```sql
SELECT * FROM CUSTOMERS WHERE SALARY > 4500;
```

**Output:**

<img width="785" height="260" alt="image" src="https://github.com/user-attachments/assets/fdfc5052-f4a9-4b90-a105-4fdb4b98b577" />

**Question 10**
---
<img width="952" height="495" alt="image" src="https://github.com/user-attachments/assets/aee5644a-38ef-4a53-9631-ca644a053893" />

```sql
SELECT ord_no,
       purch_amt,
       ord_date,
       customer_id,
       salesman_id
FROM orders
WHERE salesman_id IN (
        SELECT salesman_id
        FROM salesman
        WHERE city = 'London'
);
```

**Output:**

<img width="893" height="249" alt="image" src="https://github.com/user-attachments/assets/6715472c-b924-4d64-827c-ee7c66023c53" />


## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
