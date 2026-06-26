## SQL Lesson 4: Filtering and sorting Query results
### Exercise

<p> There are a few concepts in this lesson, but all are pretty straight-forward to apply. To spice things up, we've gone and scrambled the Movies table for you in the exercise to better mimic what kind of data you might see in real life. Try and use the necessary keywords and clauses introduced above in your queries.</p>

1. List all directors of Pixar movies (alphabetically), without duplicates

```
SELECT DISTINCT Director
FROM movies
ORDER BY Director ASC
```
<br>

2. List the last four Pixar movies released (ordered from most recent to least)

```
SELECT *
FROM movies
ORDER BY Year DESC
LIMIT 4;
```
<br>

3. List the first five Pixar movies sorted alphabetically

```
```
<br>

4. List the next five Pixar movies sorted alphabetically

```
```
