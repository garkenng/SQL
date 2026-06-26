## SQL Lesson 7: OUTER JOINs
### Summary

<p> In this exercise, you are going to be working with a new table which stores fictional data about Employees in the film studio and their assigned office Buildings. Some of the buildings are new, so they don't have any employees in them yet, but we need to find some information about them regardless.</p>

1. Find the list of all buildings that have employees

```
SELECT DISTINCT Building FROM Employees;
```
<br>

2. Find the list of all buildings and their capacity

```
SELECT * FROM Buildings;
```
<br>

3. List all buildings and the distinct employee roles in each building (including empty buildings)

```
SELECT DISTINCT Building_name, Role FROM Buildings 
  LEFT JOIN Employees ON Building_name = Building;
```
