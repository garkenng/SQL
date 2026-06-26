## SQL Lesson 3: Queries with constraints (Pt. 2)
### Exercise

<p> Here's the definition of a query with a WHERE clause again, go ahead and try and write some queries with the operators above to limit the results to the information we need in the tasks below. </p>

1. Find all the Toy Story movies

```
SELECT * FROM movies
WHERE Title like '%Toy Story%'
```
<br>

2. Find all the movies directed by John Lasseter

```
SELECT * FROM movies
WHERE Director = "John Lasseter"
```
<br>

3. Find all the movies (and director) not directed by John Lasseter

```
SELECT * FROM movies
WHERE Director != "John Lasseter"
```
<br>

4. Find all the WALL-* movies

```
SELECT * FROM movies
WHERE Title like "%WALL-%"
```
