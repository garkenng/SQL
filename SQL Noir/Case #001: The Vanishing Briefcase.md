## Case #001: The Vanishing Briefcase
### Summary<br>
Set in the gritty 1980s, a valuable briefcase has disappeared from the Blue Note Lounge. A witness reported that a man in a trench coat was seen fleeing the scene. Investigate the crime scene, review the list of suspects, and examine interview transcripts to reveal the culprit.
<br><br>
### Objectives<br>
1. Retrieve the correct crime scene details to gather the key clue.
2. Identify the suspect whose profile matches the witness description.
3. Verify the suspect using their interview transcript.
<br><br>
### Question<br>
Submit the suspect you discovered through your investigation to see if you cracked the case.

### Schema 

crime_scene

| Column | Type |	Key |
| ---- | ---- | ---- |
| id	| INTEGER	| ✔ |
| date	| INTEGER | |	
|type	| TEXT	| |
| location	| TEXT | | 	
| description	| TEXT | |

<br>
suspects

| Column |Type | Key |
| ---- | ---- | ---- |
|id |	INTEGER	| ✔ |
| name	| TEXT	| |
| attire | TEXT	| |
| scar | TEXT | |

<br>
interviews

| Column	| Type	| Key |
| ---- | ---- | ---- |
| suspect_id	| INTEGER	| ✔ |
| transcript | TEXT | |

<br><br>

To begin the investigation, search for suspects who were wearing trench coat.

```
SELECT * FROM suspects
WHERE attire = "trench coat"
```
<br>

Results
| id	| name	| attire	| scar |
| ---- | ---- | ---- | ---- |
| 3	| Frankie Lombardi	| trench coat	| left cheek |
| 183	| Vincent Malone	| trench coat	| left cheek |
| 237	| Christopher Black	| trench coat	| right cheek |

<br><br>

Pull the interviews for each of the suspects above.<br><br>

```
SELECT * FROM interviews
WHERE suspect_id in (3, 183, 237);
```
<br>


Results
| suspect_id	| transcript |
| ---- | ---- |
| 3	| NULL |
| 183	| I wasn’t going to steal it, but I did. |

<br>
It appears that Vicent Malone is our suspect. Given the  interview and wearing a trench coat. Can check if there is any mention of the scar in the crime scene table.

```
SELECT * FROM crime_scene
WHERE location = "Blue Note Lounge"
```
<br>

Results
| id	| date	| type	| location	| description |
| ---- | ---- | ---- | ---- | ---- |
| 76	| 19851120	| theft	| Blue Note Lounge	| A briefcase containing sensitive documents vanished. A witness reported a man in a trench coat with a scar on his left cheek fleeing the scene. |

