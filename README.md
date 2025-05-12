# 📊 SQL Basics

This project explores fundamental SQL queries using the `exercise_1` table, covering everything from `SELECT` to `LIMIT`, `WHERE`, logical operators, and more.

---

## 1️⃣ SELECT Statement  
**Retrieve all columns from the employees table.**

```sql
SELECT * FROM exercise_1;
2️⃣ SELECT DISTINCT Statement
Find all unique departments in the employees table.

sql
Copy code
SELECT DISTINCT(department)  
FROM exercise_1;
3️⃣ ORDER BY Statement
Get all employees' first and last names, ordered by salary (descending).

sql
Copy code
SELECT first_name, last_name, salary  
FROM exercise_1  
ORDER BY salary DESC;
4️⃣ LIMIT Statement
Retrieve the top 5 highest-paid employees.

sql
Copy code
SELECT first_name, last_name, salary  
FROM exercise_1  
ORDER BY salary DESC  
LIMIT 5;
5️⃣ WHERE Statement
Find employees who work in the IT department.

sql
Copy code
SELECT first_name, last_name, department  
FROM exercise_1  
WHERE department = 'IT';
6️⃣ AND Statement
Find employees in Finance AND earning more than 58,000.

sql
Copy code
SELECT first_name, last_name, department, salary  
FROM exercise_1  
WHERE department = 'Finance' AND salary > 58000;
7️⃣ OR Statement
Find employees in the HR OR Marketing department.

sql
Copy code
SELECT first_name, last_name, department  
FROM exercise_1  
WHERE department = 'HR' OR department = 'Marketing';
8️⃣ NOT Statement
Find employees NOT in the IT department.

sql
Copy code
SELECT first_name, last_name, department  
FROM exercise_1  
WHERE NOT department = 'IT';
9️⃣ IN Statement
Find employees in HR, IT, or Finance departments.

sql
Copy code
SELECT first_name, last_name, department  
FROM exercise_1  
WHERE department IN ('HR', 'IT', 'Finance');
🔟 Combining Conditions
Find IT employees with salary > 50,000 and based in New York.

sql
Copy code
SELECT first_name, last_name, department, salary, city  
FROM exercise_1  
WHERE department = 'IT' AND salary > 50000 AND city = 'New York';
1️⃣1️⃣ WHERE, AND, and ORDER BY
Finance/Marketing employees earning > 52,000, ordered by salary.

sql
Copy code
SELECT first_name, last_name, department, salary  
FROM exercise_1  
WHERE department IN ('Finance', 'Marketing') AND salary > 52000  
ORDER BY salary DESC;
1️⃣2️⃣ DISTINCT, WHERE, and IN
Unique cities excluding IT and HR departments.

sql
Copy code
SELECT DISTINCT(city)  
FROM exercise_1  
WHERE department NOT IN ('IT', 'HR');
1️⃣3️⃣ WHERE, NOT, AND, ORDER BY
Employees NOT in Finance, salary > 50,000, ordered by hire date.

sql
Copy code
SELECT first_name, last_name, department, salary  
FROM exercise_1  
WHERE department NOT IN ('Finance') AND salary > 50000  
ORDER BY hire_date ASC;
1️⃣4️⃣ WHERE, OR, IN, and LIMIT
First 3 employees in Chicago or LA from IT or Marketing.

sql
Copy code
SELECT first_name, last_name, city  
FROM exercise_1  
WHERE city IN ('Chicago', 'Los Angeles') AND department IN ('IT', 'Marketing')  
LIMIT 3;
yaml
Copy code

---

Would you like me to generate this as a `.md` file for upload too?








                
                
