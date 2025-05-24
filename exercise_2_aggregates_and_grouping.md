
# Exercise 2: Aggregate Functions and Grouping

## 1. Total Number of Employees
```sql
SELECT COUNT(*) FROM exercise_2;
```
**Result:** 10

## 2. Total Salary Paid to IT Department
```sql
SELECT department, SUM(salary) AS Total_salary
FROM exercise_2
WHERE department='IT'
GROUP BY department;
```
**Result:**

| Department | Total Salary |
|------------|--------------|
| IT         | 220000       |

## 3. Average Salary in HR Department
```sql
SELECT AVG(salary) AS avg_salary, department
FROM exercise_2
WHERE department='HR'
GROUP BY department;
```
**Result:** 49500.00

## 4. Highest and Lowest Salary in the Company
```sql
SELECT MIN(salary), MAX(salary) FROM exercise_2;
```
**Result:** Min Salary = 48000, Max Salary = 62000

## 5. Total Salary Paid in Each Department
```sql
SELECT SUM(salary) AS Total_salary, department
FROM exercise_2
GROUP BY department;
```
**Result:**

| Department | Total Salary |
|------------|--------------|
| Finance    | 119000       |
| HR         | 99000        |
| IT         | 220000       |
| Marketing  | 105000       |

## 6. Number of Employees in Each City
```sql
SELECT COUNT(*) AS Total_employees_per_city, city
FROM exercise_2
GROUP BY city;
```
**Result:**

| City          | Total Employees |
|---------------|-----------------|
| Chicago       | 3               |
| Houston       | 1               |
| Los Angeles   | 2               |
| New York      | 2               |
| San Francisco | 2               |

## 7. Average Salary by Department Ordered Descending
```sql
SELECT AVG(salary) as avg_salary, department
FROM exercise_2
GROUP BY department
ORDER BY avg_salary DESC;
```
**Result:**

| Department | Average Salary |
|------------|----------------|
| Finance    | 59500.00       |
| IT         | 55000.00       |
| Marketing  | 52500.00       |
| HR         | 49500.00       |

## 8. Departments where Total Salary > 100,000
```sql
SELECT SUM(salary) as total_salary, department
FROM exercise_2
GROUP BY department
HAVING total_salary > 100000;
```
**Result:**

| Department | Total Salary |
|------------|--------------|
| Finance    | 119000       |
| IT         | 220000       |
| Marketing  | 105000       |

## 9. Cities with More than One Employee Ordered by Number of Employees Descending
```sql
SELECT COUNT(city) as no_of_empl_per_city, city
FROM exercise_2
GROUP BY city
HAVING COUNT(city) > 1
ORDER BY no_of_empl_per_city DESC;
```
**Result:**

| City          | Number of Employees |
|---------------|---------------------|
| Chicago       | 3                   |
| Los Angeles   | 2                   |
| New York      | 2                   |
| San Francisco | 2                   |

## 10. Department with Highest Average Salary
```sql
SELECT department, AVG(salary) as avg_salary
FROM exercise_2
GROUP BY department
ORDER BY avg_salary DESC
LIMIT 1;
```
**Result:**

| Department | Average Salary |
|------------|----------------|
| Finance    | 59500.00       |
