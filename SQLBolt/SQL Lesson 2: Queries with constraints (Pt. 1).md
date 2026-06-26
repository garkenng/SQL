## SQL Lesson 2: Queries with constraints (Pt. 1)

### Exercise

<p> Using the right constraints, find the information we need from the Movies table for each task below.</p>

1. Find the movie with a row id of 6.

```
SELECT * FROM movies
WHERE Id = 6
```
<br>

2. Find the movies released in the years between 2000 and 2010.

```
SELECT * FROM movies
WHERE Year BETWEEN 2000 AND 2010
```
<br>

3. Find the movies not released in the years between 2000 and 2010

```
SELECT * FROM movies
WHERE Year NOT BETWEEN 2000 AND 2010
```
<br>

4. Find the first 5 Pixar movies and their release year

```
SELECT * FROM movies
WHERE Id BETWEEN 1 AND 5
```

