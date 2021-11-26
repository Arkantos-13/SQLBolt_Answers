<h3 align="center"> SQLBolt
Learn SQL with simple, interactive exercises <hr></h3>

Visit the original site [Here!](https://sqlbolt.com/) if you wish to practise on your skills in SQL 

# SQL Lesson 10: Queries with aggregates (Pt. 1)

Exercise 10 — Tasks

1. Find the longest time that an employee has been at the studio 

```
SELECT MAX(Years_employed) FROM employees;
```

2. For each role, find the average number of years employed by employees in that role

```
SELECT Role, AVG(Years_employed) AS Average_Years FROM Employees GROUP BY Role;
```

3. Find the total number of employee years worked in each building

```
SELECT DISTINCT Building, SUM(Years_employed) FROM Employees
GROUP BY Building;
```


# SQL Lesson 11: Queries with aggregates (Pt. 2)

For this exercise, you are going to dive deeper into Employee data at the film studio. Think about the different clauses you want to apply for each task

Exercise 11 — Tasks

1. Find the number of Artists in the studio (without a HAVING clause)
```
SELECT COUNT(*) FROM Employees 
WHERE Role LIKE 'Artist';
```
2. Find the number of Employees of each role in the studio
```
SELECT DISTINCT Role, COUNT(*) FROM Employees 
GROUP BY Role;
```

3. Find the total number of years employed by all Engineers. 
```
SELECT Role, SUM(Years_employed) FROM Employees
GROUP BY Role
HAVING Role = 'Engineer';
```
