# Experiment 3: DML Commands

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
<img width="892" height="366" alt="image" src="https://github.com/user-attachments/assets/f408aca8-0040-4106-9264-2da77bab9217" />

```sql
update purchases set per_unit_price=25 where purchase_date= '2022-08-15' and product_id=12;
update purchases set total_price= (quantity*per_unit_price) where purchase_date= '2022-08-15' and product_id=12;
```

**Output:**

<img width="1117" height="222" alt="image" src="https://github.com/user-attachments/assets/c6adf13d-dc70-4800-a12d-9bc86cb21b12" />

**Question 2**
---
<img width="712" height="206" alt="image" src="https://github.com/user-attachments/assets/0523dafa-5094-4fa2-94a7-accf64c38602" />

```sql
update products set availability= availability*2 where product_id=1;
```

**Output:**

<img width="892" height="153" alt="image" src="https://github.com/user-attachments/assets/b93fd429-c985-4cfd-a79c-f1ca39fc92d6" />


**Question 3**
---
<img width="963" height="379" alt="image" src="https://github.com/user-attachments/assets/539843ea-19de-4749-b1d9-63197ec756c6" />

```sql
update products set reorder_lvl=reorder_lvl-(reorder_lvl*0.3) where cost_price>50 and quantity<100;
```

**Output:**

<img width="1100" height="171" alt="image" src="https://github.com/user-attachments/assets/71ed61c1-773b-442e-a4ae-76ae52636ede" />


**Question 4**
---
<img width="874" height="453" alt="image" src="https://github.com/user-attachments/assets/e83a02c5-d1d6-43a2-adca-f972046bc15b" />

```sql
update products set reorder_lvl=40 where category='Grocery';
```

**Output:**

<img width="1094" height="190" alt="image" src="https://github.com/user-attachments/assets/afb646e0-5077-4e83-9112-0641eaa27c6a" />

**Question 5**
---
<img width="866" height="434" alt="image" src="https://github.com/user-attachments/assets/07205105-e8b5-414c-a16f-a89bd1af27df" />


```sql
update products set sell_price=sell_price+(sell_price*0.1)where supplier_id=6;
```

**Output:**

<img width="1056" height="241" alt="image" src="https://github.com/user-attachments/assets/e5bd9d37-ab54-48ac-a12e-5d504768ecc0" />


**Question 6**
---
<img width="866" height="299" alt="image" src="https://github.com/user-attachments/assets/c0af7986-748e-4d40-97ef-fb9a914f4480" />

```sql
delete from Doctors where (specialization='Pediatrics' or specialization='Cardiology') and last_name='Brown';
```

**Output:**

<img width="755" height="537" alt="image" src="https://github.com/user-attachments/assets/9f2684a4-b1de-4291-b258-3bdcb9874f30" />


**Question 7**
---
<img width="860" height="564" alt="image" src="https://github.com/user-attachments/assets/f07fdf67-6eda-4968-8b46-8c764343d8d7" />

```sql
delete from customer where agent_code='A003' or agent_code='A008';
```

**Output:**

<img width="413" height="582" alt="image" src="https://github.com/user-attachments/assets/d1368a5d-acba-4237-a3da-059248491f5b" />


**Question 8**
---
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/ee8d34f7-2b30-4e65-8ac4-7ecf6749a4c8" />


```sql
delete from Surgeries where surgeon_id=3;
```

**Output:**

<img width="873" height="219" alt="image" src="https://github.com/user-attachments/assets/2973dfb7-da8d-43e9-8900-c844deacd3d9" />


**Question 9**
---
<img width="823" height="303" alt="image" src="https://github.com/user-attachments/assets/77e3eee4-97ff-4ea9-b6fb-a86e38a9e0c8" />

```sql
delete from Doctors where (specialization='Pediatrics' or specialization='Cardiology') and last_name='Brown';
```

**Output:**

<img width="836" height="560" alt="image" src="https://github.com/user-attachments/assets/8b37a2f3-abf3-48a2-a1b6-94b24e3dc591" />

**Question 10**
---
<img width="876" height="84" alt="image" src="https://github.com/user-attachments/assets/79873e79-87fe-475e-87df-1694f5e5c442" />


```sql
delete from Doctors where specialization='Pediatrics' and first_name='Michael';
```

**Output:**

<img width="812" height="226" alt="image" src="https://github.com/user-attachments/assets/8f13846f-f2d0-4aa5-a9f3-b632274e42be" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
