# 📘 SQL Practice — Basic Queries & Aggregate Functions (Q → SQL)

This document contains my **foundational SQL practice**, rewritten in a clean **Question → SQL Answer** format.

The focus here is on building strong fundamentals using:

* `WHERE`, logical operators, `ORDER BY`, `DISTINCT`
* Aggregate functions: `COUNT`, `SUM`, `AVG`, `MIN`, `MAX`

All queries are written and executed on simple sample tables.

---

## 🗂 Tables Used

### Students

```sql
CREATE TABLE students (
  id INTEGER PRIMARY KEY,
  name TEXT,
  age INTEGER,
  marks INTEGER,
  city TEXT
);
```

### Employees

```sql
CREATE TABLE employees (
  emp_id INTEGER PRIMARY KEY,
  name TEXT,
  department TEXT,
  salary INTEGER,
  experience INTEGER
);
```

### Orders

```sql
CREATE TABLE orders (
  order_id INTEGER PRIMARY KEY,
  customer TEXT,
  amount INTEGER,
  status TEXT
);
```

---

## 🔹 BASIC SQL (WHERE, ORDER BY, DISTINCT)

### Q1. Find students whose marks are greater than 60.

```sql
select name, marks
from students
where marks > 60;
```

### Q2. Find students from Delhi with marks above 70.

```sql
select city, name, marks
from students
where city = 'Delhi'
  and marks > 70;
```

### Q3. Find students who are not from Mumbai.

```sql
select name, city
from students
where city != 'Mumbai';
```

### Q4. Find students whose name starts with the letter C.

```sql
select name
from students
where name like 'c%';
```

### Q5. List students ordered by marks (highest first).

```sql
select name, marks
from students
order by marks desc;
```

### Q6. Show only distinct cities.

```sql
select distinct city
from students;
```

---

## 🔹 EMPLOYEES — BASIC QUERIES

### Q7. Find employees with salary between 40,000 and 60,000.

```sql
select name, salary
from employees
where salary between 40000 and 60000;
```

### Q8. Find employees who work in IT or HR.

```sql
select name, department
from employees
where department = 'HR'
   or department = 'IT';
```

### Q9. List employees ordered by experience (descending).

```sql
select name, experience
from employees
order by experience desc;
```

### Q10. Show distinct departments.

```sql
select distinct department
from employees;
```

---

## 🟡 AGGREGATE FUNCTIONS

### Students

#### Q11. Find the average marks of students.

```sql
select avg(marks)
from students;
```

#### Q12. Find the highest marks.

```sql
select max(marks)
from students;
```

#### Q13. Count students from each city.

```sql
select count(name), city
from students
group by city;
```

---

### Employees

#### Q14. Find total salary paid to employees.

```sql
select sum(salary) as [Total Salary]
from employees;
```

#### Q15. Find the average salary of IT department.

```sql
select avg(salary)
from employees
where department = 'IT';
```

#### Q16. Find minimum and maximum salary.

```sql
select min(salary) as [Min Salary],
       max(salary) as [Max Salary]
from employees;
```

---

### Orders

#### Q17. Count total number of orders.

```sql
select count(*) as Orders
from orders;
```

#### Q18. Find total order amount.

```sql
select sum(amount) as [Order Amount]
from orders;
```

#### Q19. Find average order amount.

```sql
select avg(amount) as [Avg Amount]
from orders;
```

---

## ✅ Notes

* Queries focus on **clarity and correctness**
* Syntax follows **standard SQL**
* Designed to be **interview‑ready foundational practice**


