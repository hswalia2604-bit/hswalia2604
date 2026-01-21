🗂 Tables Used
Students
CREATE TABLE students (
  id INTEGER PRIMARY KEY,
  name TEXT,
  age INTEGER,
  marks INTEGER,
  city TEXT
);

Employees
CREATE TABLE employees (
  emp_id INTEGER PRIMARY KEY,
  name TEXT,
  department TEXT,
  salary INTEGER,
  experience INTEGER
);

Orders
CREATE TABLE orders (
  order_id INTEGER PRIMARY KEY,
  customer TEXT,
  amount INTEGER,
  status TEXT
);

🔹 BASIC SQL (WHERE, ORDER BY, DISTINCT)
1. Find students whose marks are greater than 60
SELECT name, marks
FROM students
WHERE marks > 60;

2. Find students from Delhi with marks above 70
SELECT city, name, marks
FROM students
WHERE city = 'Delhi' AND marks > 70;

3. Find students who are not from Mumbai
SELECT name, city
FROM students
WHERE city != 'Mumbai';

4. Find students whose name starts with letter C
SELECT name
FROM students
WHERE name LIKE 'c%';

5. List students ordered by marks (highest first)
SELECT name, marks
FROM students
ORDER BY marks DESC;

6. Show only distinct cities
SELECT DISTINCT(city)
FROM students;

🔹 Employees – Basic Queries
7. Find employees with salary between 40,000 and 60,000
SELECT name, salary
FROM employees
WHERE salary BETWEEN 40000 AND 60000;

8. Find employees who work in IT or HR
SELECT name, department
FROM employees
WHERE department = 'HR' OR department = 'IT';

9. List employees ordered by experience (descending)
SELECT name, experience
FROM employees
ORDER BY experience DESC;

10. Show distinct departments
SELECT DISTINCT(department)
FROM employees;

🟡 AGGREGATE FUNCTIONS
Students
11. Find the average marks
SELECT AVG(marks)
FROM students;

12. Find the highest marks
SELECT MAX(marks)
FROM students;

13. Count students from each city
SELECT COUNT(name), city
FROM students
GROUP BY city;

Employees
14. Find total salary paid
SELECT SUM(salary) AS [Total Salary]
FROM employees;

15. Find average salary of IT department
SELECT AVG(salary)
FROM employees
WHERE department = 'IT';

16. Find minimum and maximum salary
SELECT MIN(salary) AS [min salary], MAX(salary) AS [max salary]
FROM employees;

Orders
17. Count total number of orders
SELECT COUNT(*) AS Orders
FROM orders;

18. Find total order amount
SELECT SUM(amount) AS [Order Amount]
FROM orders;

19. Find average order amount
SELECT AVG(amount) AS [Avg Amount]
FROM orders;
