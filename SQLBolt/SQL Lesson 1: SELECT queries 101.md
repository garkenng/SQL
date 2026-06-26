## SQL Lesson 1: SELECT queries 101

### Exercise
We will be using a database with data about some of Pixar's classic movies for most of our exercises. This first exercise will only involve the Movies table, and the default query below currently shows all the properties of each movie. To continue onto the next lesson, alter the query to find the exact information we need for each task.

1. Find the title of each film.<br>

```
SELECT Title FROM movies;
```
<br>

2. Find the director of each film.<br><br>

```
SELECT Director FROM movies;
```
<br>

3. Find the title and director of each film.<br><br>

```
SELECT Title, Director FROM movies;
```
<br>

4. Find the title and year of each film

```
SELECT Title, Year FROM movies;
```
<br>

5. Find all the information about each film

```
SELECT * FROM movies;
```

