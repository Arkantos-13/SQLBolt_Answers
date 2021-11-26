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

# SQL Lesson 12: Order of execution of a Query

Exercise 12 — Tasks

1. Find the number of movies each director has directed
```
SELECT Director , COUNT(Title) AS Amount_of_Movies FROM Movies 
GROUP BY Director;
```
2. Find the total domestic and international sales that can be attributed to each director
```
SELECT Director, SUM(Domestic_sales + International_sales) AS Sales FROM Movies 
INNER JOIN Boxoffice  ON
Movies.Id = Boxoffice.Movie_id
GROUP BY Director;
```

# SQL Lesson 13: Inserting rows

Exercise 13 — Tasks

1. Add the studio's new production, Toy Story 4 to the list of movies (you can use any director)
```
INSERT INTO Movies 
(Title,Director,Year,Length_minutes)
VALUES
('Toy Story 4', 'John Lasseter', 2013,100);
```
2.Toy Story 4 has been released to critical acclaim! It had a rating of 8.7, and made 340 million domestically and 270 million internationally. Add the record to the BoxOffice table.
```

```
