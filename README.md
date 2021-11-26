<h3 align="center"> SQLBolt
Learn SQL with simple, interactive exercises <hr></h3>

Visit the original site [Here!](https://sqlbolt.com/) if you wish to practise on your skills in SQL 


# SQL Lesson 1: SELECT queries 101

Exercise 1 — Tasks

1. Find the title of each film
```
SELECT Title FROM movies;
```

2. Find the director of each film
```
SELECT Director FROM movies;
```

3. Find the title and director of each film
```
SELECT Title, Director FROM movies;
```
4. Find the title and year of each film
```
SELECT Title, Year FROM movies;
```
5. Find all the information about each film
```
SELECT * FROM movies;
```


# SQL Lesson 2: Queries with constraints (Pt. 1)

Exercise 2 — Tasks

1. Find the movie with a row id of 6
```
SELECT * FROM movies WHERE Id = 6;
```

2. Find the movies released in the years between 2000 and 2010
```
SELECT * FROM movies WHERE Year BETWEEN 2000 AND 2010;

```
3. Find the movies not released in the years between 2000 and 2010
```
SELECT * FROM movies WHERE Year NOT BETWEEN 2000 AND 2010;

```
4. Find the first 5 Pixar movies and their release year
```
SELECT Title, Year FROM movies LIMIT 5;

```


# SQL Lesson 3: Queries with constraints (Pt. 2)

Exercise 3 — Tasks

1. Find all the Toy Story movies
```
SELECT * FROM movies WHERE Title LIKE '%Toy Story%';
```
2. Find all the movies directed by John Lasseter
```
SELECT * FROM movies WHERE Director = 'John Lasseter';
```
3. Find all the movies (and director) not directed by John Lasseter
```
SELECT Title, Director FROM movies WHERE Director != 'John Lasseter';
```
4. Find all the WALL-* movies
```
SELECT Title FROM movies WHERE Title LIKE '%WALL%';
```

# SQL Lesson 4: Filtering and sorting Query results

Exercise 4 — Tasks
1. List all directors of Pixar movies (alphabetically), without duplicates
```
SELECT DISTINCT Director FROM movies ORDER BY Director;
```
2. List the last four Pixar movies released (ordered from most recent to least)
```
SELECT Title FROM movies ORDER BY Year DESC LIMIT 4;
```
3. List the first five Pixar movies sorted alphabetically
```
SELECT Title FROM movies ORDER BY Title LIMIT 5;
```
4. List the next five Pixar movies sorted alphabetically
```
SELECT Title FROM movies ORDER BY Title LIMIT 5 OFFSET 5;
```

# SQL Review: Simple SELECT Queries

Review 1 — Tasks

1. List all the Canadian cities and their populations
```

```
2. Order all the cities in the United States by their latitude from north to south
```

```
3. List all the cities west of Chicago, ordered from west to east
```

```
4.List the two largest cities in Mexico (by population)
```

```
5. List the third and fourth largest cities (by population) in the United States and their population
```

```

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
INSERT INTO Movies VALUES (4, 'Toy Story 4', 'John Lasseter', 2013,100);
```
2.Toy Story 4 has been released to critical acclaim! It had a rating of 8.7, and made 340 million domestically and 270 million internationally. Add the record to the BoxOffice table.
```
INSERT INTO Boxoffice VALUES(4,8.7,340000000,270000000);
```

# SQL Lesson 14: Updating rows

Exercise 14 — Tasks

1. The director for A Bug's Life is incorrect, it was actually directed by John Lasseter
```
UPDATE Movies
SET Director = 'John Lasseter'
WHERE Id = 2;
```

OR 

```
UPDATE Movies
SET Director = 'John Lasseter'
WHERE Title = "A Bug's Life";
```

2. The year that Toy Story 2 was released is incorrect, it was actually released in 1999
```
UPDATE Movies
SET Year = '1999'
WHERE Title = 'Toy Story 2'
```

3. Both the title and director for Toy Story 8 is incorrect! The title should be "Toy Story 3" and it was directed by Lee Unkrich
```
UPDATE Movies
SET Title = 'Toy Story 3', Director = 'Lee Unkrich'
WHERE Movies.Id = 11;
```


# SQL Lesson 15: Deleting rows

Exercise 15 — Tasks

1. This database is getting too big, lets remove all movies that were released before 2005.
```
DELETE FROM Movies WHERE Year < 2005;
```

2.Andrew Stanton has also left the studio, so please remove all movies directed by him.
```
DELETE FROM Movies WHERE Director = 'Andrew Stanton';
```

# SQL Lesson 16: Creating tables

Exercise 16 — Tasks

1. Create a new table named Database with the following columns:
  – Name A string (text) describing the name of the database
  – Version A number (floating point) of the latest version of this database
  – Download_count An integer count of the number of times this database was downloaded

This table has no constraints.

```
CREATE TABLE Database
(Name TEXT,
Version REAL,
Download_count INTEGER);
```

# SQL Lesson 17: Altering tables

Exercise 17 — Tasks

1. Add a column named Aspect_ratio with a FLOAT data type to store the aspect-ratio each movie was released in.
```
ALTER TABLE  Movies 
  ADD Aspect_ratio FLOAT;
```

2. Add another column named Language with a TEXT data type to store the language that the movie was released in. Ensure that the default for this language is English.
```
ALTER TABLE Movies
  ADD COLUMN Language TEXT DEFAULT 'English';
```

# SQL Lesson 18: Dropping tables

Exercise 18 — Tasks

1. We've sadly reached the end of our lessons, lets clean up by removing the Movies table
```
DROP TABLE IF EXISTS Movies ;
```

2. And drop the BoxOffice table as well
```
DROP TABLE IF EXISTS BoxOffice  ;
```

# 
