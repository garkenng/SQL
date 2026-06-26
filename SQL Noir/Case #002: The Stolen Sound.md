## Case #002: The Stolen Sound
### Summary<br>
In the neon glow of 1980s Los Angeles, the West Hollywood Records store was rocked by a daring theft. A prized vinyl record, worth over $10,000, vanished during a busy evening, leaving the store owner desperate for answers. Vaguely recalling the details, you know the incident occurred on July 15, 1983, at this famous store. Your task is to track down the thief and bring them to justice.
<br><br>
### Objectives<br>
1. Retrieve the crime scene report for the record theft using the known date and location.
2. Retrieve witness records linked to that crime scene to obtain their clues.
3. Use the clues from the witnesses to find the suspect in the suspects table.
4. Retrieve the suspect's interview transcript to confirm the confession.
<br><br>
### Question<br>
Submit the suspect you discovered through your investigation to see if you cracked the case.
<br><br>

### Schema 

crime_scene

| Column	| Type	| Key | 
| ---- | ---- | ---- |
| id	| INTEGER	 | ✔ |
| date	| INTEGER |	|
| type	| TEXT	| |
| location	| TEXT | |	
| description	| TEXT | |

witnesses

| Column |	Type |	Key |
| ---- | ---- | ---- |
| id	| INTEGER	| ✔ |
| crime_scene_id |	INTEGER | 🔗 |
| clue | | TEXT | |

suspects

| Column	| Type	| Key |
| ---- | ---- | ---- |
| id	| INTEGER | ✔ |	
| name	| TEXT | |	
| bandana_color	| TEXT | |	
| accessory	| TEXT | |

interviews

| Column	| Type	| Key |
| ---- | ---- | ---- |
| suspect_id	| INTEGER	| 🔗 |
| transcript	| TEXT | |

<br>
Retrieve the crime scene report.<br><br>

```
SELECT * FROM crime_scene
WHERE location = 'West Hollywood Records'
```
<br>

Results

| id	| date	| type	| location	| description |
| ---- | ---- | ---- | ---- | ---- |
| 65	| 19830715	| theft	| West Hollywood Records	| A prized vinyl record was stolen from the store during a busy evening. |

Retrieve witness records linked to the crime scene.<br><br>

```
SELECT * FROM witnesses
WHERE crime_scene_id = 65
```
<br>

Results

| id	| crime_scene_id	| clue |
| ---- | ---- | ---- | 
| 28 |	65 |	I saw a man wearing a red bandana rushing out of the store. |
| 75 |	65	| he main thing I remember is that he had a distinctive gold watch on his wrist. |


Use the clues from previous results to look for a suspect with a red bandana and a gold watch.<br><br>

```
SELECT * FROM suspects
WHERE bandana_color = "red" 
AND accessory = "gold watch"
```
<br>

Results

| id	| name	| bandana_color	| accessory |
| ---- | ---- | ---- | ---- | 
| 35	| Tony Ramirez	| red	| gold watch |
| 44	| Mickey Rivera	| red	| gold watch | 
| 97	| Rico Delgado	| red	| gold watch |

Narrowed down to 3 suspects. Run a query on the interview table with the ID's.<br><br>

```
SELECT * FROM interviews
WHERE suspect_id in (35, 44, 97);
```
<br>

Results

| suspect_id	| transcript |
| ---- | ---- |
| 35	| I wasn't anywhere near West Hollywood Records that night. |
| 44	| I was busy with my music career; I have nothing to do with this theft. |
| 97	| I couldn't help it. I snapped and took the record. |

The  ID 97 is our suspect. To confirm the findings, can lookup suspect id on the suspects table.<br><br>

```
SELECT * FROM suspects
WHERE id = 97
```
<br>

Results


| id	| name	| bandana_color	| accessory |
| ---- | ---- | ---- | ---- |
| 97	| Rico Delgado	| red	gold | watch |

### Answer: Rico Delgado
