# SQL-Lab2

# We will use the Employees and Awards table below:

 <img src="Lab2.png" width="500" height="500">

### Q1: Choose all employees who have received an award (Nested Query)?
Query: SELECT *
 FROM employee 
 WHERE id in ( SELECT employee_id 
             FROM awards) ; 

Output:<img src="Q1.png" width="1083" height="219"> 
 

### Q2: Choose all employees who have never received an award (Nested Query)?
Query:SELECT *
FROM employee 
WHERE id not in ( SELECT employee_id 
             FROM awards) ; 

Output:<img src="Q2.png" width="500" height="500"> 

 
### Q3: Choose all Developers who make more than all Managers combined (Nested Query)?
Query:SELECT *
FROM employee
WHERE role = "Developer" and salary > ( SELECT MAX(salary)
                FROM employee
                WHERE role ="Manager" ); 

Output:<img src="Q3.png" width="500" height="500"> 

 
### Q4: Choose all Developers who make more money than any Manager (Nested Query)?
Query:SELECT *
FROM employee
WHERE role = "Developer" and salary > ( SELECT MIN(salary)
                FROM employee
                WHERE role ="Manager" );

Output:<img src="Q4.png" width="500" height="500">

 
### Q5: Choose all employees whose salaries are higher than the average for their position. (Nested Query)?
Query:SELECT *
FROM employee 
where salary > (SELECT AVG(salary)
                FROM employee 
                where role= employee.role ) ;

Output:<img src="Q5.png" width="500" height="500">
