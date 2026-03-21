# Experiment 4: Aggregate Functions, Group By and Having Clause

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
<img width="711" height="476" alt="image" src="https://github.com/user-attachments/assets/d06109e1-b887-4c2e-a1cb-f064f5789998" />


```sql
select DoctorID, count(*) as TotalPrescriptions from Prescriptions group by DoctorId;
```

**Output:**

<img width="599" height="554" alt="image" src="https://github.com/user-attachments/assets/656edc71-df2d-4d6f-84e8-50255f16fb52" />


**Question 2**
---
<img width="477" height="453" alt="image" src="https://github.com/user-attachments/assets/918083c5-de32-4706-aebf-c7a7547d6001" />


```sql
Select strftime('%H',AppointmentDateTime) as HourOfDay, count(*) as TotalAppointments from Appointments group by strftime('%H',AppointmentDateTime);
```

**Output:**

<img width="510" height="376" alt="image" src="https://github.com/user-attachments/assets/b63f1c74-bacd-45fc-b07a-1f36ab9e5b51" />


**Question 3**
---
<img width="735" height="332" alt="image" src="https://github.com/user-attachments/assets/f547d822-9f80-4f52-92f8-9eb0a655eb6a" />


```sql
Select Gender,count(*) as TotalPatients from Patients group by gender;
```

**Output:**

<img width="469" height="271" alt="image" src="https://github.com/user-attachments/assets/d576451f-40d7-472c-afcc-0ca6230816df" />


**Question 4**
---
<img width="884" height="369" alt="image" src="https://github.com/user-attachments/assets/6fd7804a-d1b5-40e6-976c-a645d771f105" />


```sql
select Count(*) as COUNT from customer ;
```

**Output:**

<img width="295" height="247" alt="image" src="https://github.com/user-attachments/assets/c6fa1641-a143-499e-9817-683352dee354" />


**Question 5**
---
<img width="655" height="340" alt="image" src="https://github.com/user-attachments/assets/994a30ef-1e7c-49db-9c9f-eaf2d6d3183e" />


```sql
select avg(income) as avg_income from employee where name like 'A%';
```

**Output:**

<img width="281" height="222" alt="image" src="https://github.com/user-attachments/assets/198ab4fa-b335-407a-acf2-58be01f7bafe" />


**Question 6**
---
<img width="838" height="394" alt="image" src="https://github.com/user-attachments/assets/339e233b-71f4-4977-bbaa-bcb0f0950305" />


```sql
select sum(Inventory) as total_available_amount from fruits where price>0.5;
```

**Output:**

<img width="486" height="219" alt="image" src="https://github.com/user-attachments/assets/3c55da3a-c254-4294-ac69-ecbe3f8f8009" />


**Question 7**
---
<img width="771" height="180" alt="image" src="https://github.com/user-attachments/assets/6274b58d-f3c4-4bc4-a2d7-6d8780a28b95" />

```sql
select sum(workhour) as 'Total working hours' from employee1;
```

**Output:**

<img width="489" height="244" alt="image" src="https://github.com/user-attachments/assets/064b69f8-1ea4-48f5-9573-db95aa1883a9" />


**Question 8**
---
<img width="1110" height="248" alt="image" src="https://github.com/user-attachments/assets/973f9a88-3717-400d-8414-6915096c9937" />

```sql
select (age/5)*5 as age_group,SUM(salary) from customer1 group by (age/5)*5 having sum(salary)>=5000;
```

**Output:**

<img width="450" height="235" alt="image" src="https://github.com/user-attachments/assets/7290c567-76be-49e5-b573-7a72281da5a4" />


**Question 9**
---
<img width="1039" height="270" alt="image" src="https://github.com/user-attachments/assets/5dec6bde-ea4b-46c2-b955-8a6c9b30d0f0" />


```sql
select jdate, SUM(workhour) from employee1 group by jdate having sum(workhour)>=40;
```

**Output:**

<img width="395" height="218" alt="image" src="https://github.com/user-attachments/assets/6c55620a-e5a5-45fd-b5e3-ab42be9a108e" />


**Question 10**
---
<img width="1028" height="271" alt="image" src="https://github.com/user-attachments/assets/d69fbd7d-7b45-4bb8-a866-316d51327a09" />


```sql
select jdate, MIN(workhour) from employee1 group by jdate having min(workhour)<=10;
```

**Output:**

<img width="385" height="253" alt="image" src="https://github.com/user-attachments/assets/34473308-abd8-46a0-b266-e21c8f2b4b4c" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
