
# 📘 Snowflake SQL Fundamentals Practice 1
This document contains beginner SQL exercises completed using Snowflake. Each question is followed by the SQL code used to solve it and a sample of the resulting output based on the dataset provided.

---

## 1️⃣ SELECT all columns from the employees table

### 💻 SQL Code:
```sql
SELECT * FROM exercise_1;
```

### 📊 Result:
| ID | FIRST_NAME | LAST_NAME | DEPARTMENT | SALARY | HIRE_DATE | CITY           |
|----|------------|-----------|------------|--------|------------|----------------|
| 1  | John       | Doe       | IT         | 55000  | 2018-06-15 | New York       |
| 2  | Jane       | Smith     | HR         | 48000  | 2019-07-20 | Chicago        |
| 3  | Mike       | Johnson   | Finance    | 60000  | 2017-09-30 | Los Angeles    |
| 4  | Sarah      | Brown     | IT         | 53000  | 2021-03-25 | New York       |
| 5  | David      | White     | Marketing  | 52000  | 2016-04-10 | San Francisco  |

---

## 2️⃣ SELECT DISTINCT departments

### 💻 SQL Code:
```sql
SELECT DISTINCT(department) FROM exercise_1;
```

### 📊 Result:
| department  |
|-------------|
| IT          |
| HR          |
| Finance     |
| Marketing   |

---

## 3️⃣ ORDER BY salary DESC

### 💻 SQL Code:
```sql
SELECT first_name, last_name, salary
FROM exercise_1
ORDER BY salary DESC;
```

### 📊 Result:
| first_name | last_name | salary |
|------------|-----------|--------|
| Emily      | Davis     | 62000  |
| Mike       | Johnson   | 60000  |
| Robert     | Wilson    | 59000  |
| John       | Doe       | 55000  |
| Daniel     | Clark     | 53000  |

---

## 4️⃣ LIMIT to Top 5 Highest-Paid Employees

### 💻 SQL Code:
```sql
SELECT first_name, last_name, salary
FROM exercise_1
ORDER BY salary DESC
LIMIT 5;
```

### 📊 Result:
(Same as question 3 above — top 5 salaries)

---

## 5️⃣ Employees in IT Department

### 💻 SQL Code:
```sql
SELECT first_name, last_name, department
FROM exercise_1
WHERE department = 'IT';
```

### 📊 Result:
| first_name | last_name | department |
|------------|-----------|------------|
| John       | Doe       | IT         |
| Sarah      | Brown     | IT         |
| Emily      | Davis     | IT         |
| Laura      | Hall      | IT         |

---

## 6️⃣ Finance Employees with Salary > 58,000

### 💻 SQL Code:
```sql
SELECT first_name, last_name, department, salary
FROM exercise_1
WHERE department = 'Finance'
AND salary > 58000;
```

### 📊 Result:
| first_name | last_name | department | salary |
|------------|-----------|------------|--------|
| Mike       | Johnson   | Finance    | 60000  |

---

## 7️⃣ Employees in HR OR Marketing

### 💻 SQL Code:
```sql
SELECT first_name, last_name, department
FROM exercise_1
WHERE department = 'HR' OR department = 'Marketing';
```

### 📊 Result:
| first_name | last_name | department |
|------------|-----------|------------|
| Jane       | Smith     | HR         |
| Jessica    | Moore     | HR         |
| David      | White     | Marketing  |
| Daniel     | Clark     | Marketing  |

---

## 8️⃣ NOT in IT Department

### 💻 SQL Code:
```sql
SELECT first_name, last_name, department
FROM exercise_1
WHERE NOT department = 'IT';
```

### 📊 Result:
(Everyone except those in IT)

---

## 9️⃣ IN HR, IT, or Finance

### 💻 SQL Code:
```sql
SELECT first_name, last_name, department
FROM exercise_1
WHERE department IN ('HR', 'IT', 'Finance');
```

### 📊 Result:
(Everyone except Marketing)

---

## 🔟 In IT, Salary > 50,000, and in New York

### 💻 SQL Code:
```sql
SELECT first_name, last_name, department, salary, city
FROM exercise_1
WHERE department = 'IT'
AND salary > 50000
AND city = 'New York';
```

### 📊 Result:
| first_name | last_name | department | salary | city     |
|------------|-----------|------------|--------|----------|
| John       | Doe       | IT         | 55000  | New York |

---

## 1️⃣1️⃣ Finance or Marketing, Salary > 52,000, Ordered by Salary

### 💻 SQL Code:
```sql
SELECT first_name, last_name, department, salary
FROM exercise_1
WHERE department IN ('Finance', 'Marketing')
AND salary > 52000
ORDER BY salary DESC;
```

### 📊 Result:
| first_name | last_name | department | salary |
|------------|-----------|------------|--------|
| Mike       | Johnson   | Finance    | 60000  |
| Daniel     | Clark     | Marketing  | 53000  |

---

## 1️⃣2️⃣ Unique Cities, Excluding IT and HR Departments

### 💻 SQL Code:
```sql
SELECT DISTINCT(city)
FROM exercise_1
WHERE NOT department IN ('IT', 'HR');
```

### 📊 Result:
| city         |
|--------------|
| Los Angeles  |
| San Francisco |
| Houston       |

---

## 1️⃣3️⃣ NOT Finance, Salary > 50,000, Ordered by Hire Date

### 💻 SQL Code:
```sql
SELECT first_name, last_name, department, salary
FROM exercise_1
WHERE NOT department IN ('Finance')
AND salary > 50000
ORDER BY hire_date ASC;
```

### 📊 Result:
| first_name | last_name | department | salary |
|------------|-----------|------------|--------|
| Emily      | Davis     | IT         | 62000  |
| David      | White     | Marketing  | 52000  |
| John       | Doe       | IT         | 55000  |
| Sarah      | Brown     | IT         | 53000  |
| Daniel     | Clark     | Marketing  | 53000  |

---

## 1️⃣4️⃣ First 3 in Chicago or LA, in IT or Marketing

### 💻 SQL Code:
```sql
SELECT first_name, last_name, city
FROM exercise_1
WHERE city IN ('Chicago', 'Los Angeles')
AND department IN ('IT', 'Marketing')
LIMIT 3;
```

### 📊 Result:
| first_name | last_name | city       |
|------------|-----------|------------|
| Emily      | Davis     | Chicago    |
| Daniel     | Clark     | Chicago    |

---
