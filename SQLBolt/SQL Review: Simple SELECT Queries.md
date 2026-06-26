## SQL Review: Simple SELECT Queries
### Summary

<p> In the exercise below, you will be working with a different table. This table instead contains information about a few of the most populous cities of North America including their population and geo-spatial location in the world.</p>
<p> Try and write some queries to find the information requested in the tasks below. You may have to use a different combination of clauses in your query for each task. Once you're done, continue onto the next lesson to learn about queries that span multiple tables.</p>


1. List all the Canadian cities and their populations

```
SELECT * FROM north_american_cities
WHERE Country = "Canada"
```
<br>

2. Order all the cities in the United States by their latitude from north to south

```
SELECT * FROM north_american_cities
WHERE Country = "United States"
ORDER BY Latitude DESC;
```
<br>

3. List all the cities west of Chicago, ordered from west to east

```
SELECT City FROM north_american_cities
ORDER BY Longitude ASC
LIMIT 6
```
<br>

4. List the two largest cities in Mexico (by population)

```
SELECT * FROM north_american_cities
WHERE Country = "Mexico"
ORDER BY Population DESC
LIMIT 2
```
<br>

5. List the third and fourth largest cities (by population) in the United States and their population
   
```
SELECT * FROM north_american_cities
WHERE Country = "United States"
ORDER BY Population DESC
LIMIT 2 OFFSET 2
```
<br>
