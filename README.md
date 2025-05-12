# SQL-Basics
Exercise 1-3 dedicated to SQL fundamentals
--Questions
--1. SELECT Statement
--Write a SQL query to retrieve all columns from the employees table.

select *
    from exercise_1;


--2. SELECT DISTINCT Statement
--Write a SQL query to find all the unique departments in the employees table.
select distinct(department)
        from exercise_1;

--3. ORDER BY Statement
--Write a SQL query to retrieve all employees' first and last names, ordered by salary in 
--descending order.

select first_name,last_name,salary
    from exercise_1
        order by salary desc;

--4. LIMIT Statement
--Write a SQL query to retrieve the top 5 highest-paid employees.

select first_name,last_name,salary
    from exercise_1
        order by salary desc
         limit 5;


--5. WHERE Statement
--Write an SQL query to find employees who work in the IT department.

 select first_name,last_name,department
    from exercise_1
        where department='IT' ;   
        
--6. AND Statement
--Write a SQL query to find employees who work in the Finance department AND have a 
--salary greater than 58,000.

select first_name,last_name,department,salary
    from exercise_1
        where department='Finance'
            AND salary>58000;
        


--7. OR Statement
--Write a SQL query to find employees who work in the HR department OR the Marketing 
--department.

select first_name,last_name,department
    from exercise_1
        where department='HR' OR department='Marketing';
        
--8. NOT Statement
--Write a SQL query to find employees who do not work in the IT department.

select first_name,last_name,department
    from exercise_1
        where NOT department='IT';
--9. IN Statement
--Write a SQL query to find employees who are in the HR, IT, or Finance departments.

select first_name,last_name,department
    from exercise_1
        where department IN ('HR','IT','Finance');
        
--10. Combining Conditions
--Write a SQL query to find employees who are in the IT department, have a salary greater 
--than 50,000, and are located in New York.

select first_name,last_name,department,salary,city
    from exercise_1
        where department='IT'
            AND salary >50000
                AND  city ='New York';
--11. Combining WHERE, AND, and ORDER BY
--Write a SQL query to retrieve the first and last names of employees who work in the 
--Finance or Marketing department, earn more than 52,000, and order the results by 
--salary in descending order.

select first_name,last_name,department,salary
    from exercise_1
        where department IN ('Finance','Marketing')
            AND salary>52000
                order by salary desc;

--12. Combining SELECT DISTINCT, WHERE, and IN
--Write a SQL query to find all the unique cities where employees work, excluding those 
--in the IT and HR departments.
select distinct(city)
    from exercise_1
        where not department IN ('IT','HR');
        
--13. Combining WHERE, NOT, AND, and ORDER BY
--Write a SQL query to retrieve employees who are NOT in the Finance department, 
--have a salary greater than 50,000, and order the results by hire date in ascending 
--order.

select first_name,last_name,department,salary
    from exercise_1
        where not department IN ('Finance')
            AND salary>50000
                order by hire_date asc;
        
--14. Combining WHERE, OR, IN, and LIMIT
--Write a SQL query to find the first 3 employees who work in either Chicago or Los 
--Angeles and belong to the IT or Marketing department
select first_name, last_name,city
    from exercise_1
        Where city IN ('Chicago', 'Los Angeles')
            AND department IN ('IT', 'Marketing')
                Limit 3;
                
