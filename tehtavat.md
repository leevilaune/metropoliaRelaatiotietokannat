Osa kuvista leikattu tilan säästämiseksi

# 03 Yhteen tauluun kohdistuvat kyselyt

### Tehtävä 1
```sql
SELECT * 
FROM goal;
```
![image](https://github.com/user-attachments/assets/6d9dbfba-bce3-4a4f-aa00-dbc6b9ebc769)

### Tehtävä 2
```sql
SELECT name
FROM airport
WHERE iso_country="FI";
```
![image](https://github.com/user-attachments/assets/1c1a06fd-5fb7-4057-af22-874925305f24)

### Tehtävä 3
```sql
SELECT name 
FROM airport 
WHERE iso_country="FI" 
ORDER BY name ASC;
```
![image](https://github.com/user-attachments/assets/d37cf9cf-f4ef-4c3b-abc6-33282a99e7ce)

### Tehtävä 4
```sql
SELECT name, type 
FROM airport 
WHERE iso_country = "FI" 
ORDER BY type, name;
```
![image](https://github.com/user-attachments/assets/6d1511d2-1c22-40f1-a927-05c7e2d774cb)

### Tehtävä 5
```sql
SELECT name
FROM country
WHERE name LIKE "F%";
```
![image](https://github.com/user-attachments/assets/e49ddac8-5465-43e7-a549-ed349e825f0c)

### Tehtävä 6
```sql
SELECT name
FROM country
WHERE name LIKE "%F%";
```
![image](https://github.com/user-attachments/assets/82046ed0-645d-492a-8b35-d82212a4793a)

### Tehtävä 7
```sql
SELECT location 
FROM game 
WHERE screen_name = "Vesa";
```
![image](https://github.com/user-attachments/assets/51d03874-199b-4b0f-9622-4c6a0f829b02)

### Tehtävä 8
```sql
SELECT co2_consumed
FROM game
WHERE screen_name="Ilkka";
```
![image](https://github.com/user-attachments/assets/cff5dd39-faae-468d-85fa-3798eb9ccaf3)

### Tehtävä 9
```sql
SELECT DISTINCT co2_budget
FROM game;
```
![image](https://github.com/user-attachments/assets/a6fa43be-50fc-47c2-81c7-88058aaed81c)

# 04 Where-osan liitosehto

### Tehtävä 1
```sql
SELECT country.name AS "country name", airport.name AS "airport name"
FROM country, airport
WHERE country.name = "Iceland" AND airport.iso_country=country.iso_country;
```
![image](https://github.com/user-attachments/assets/b4f082e7-db45-48ac-ad38-319ac1086408)

### Tehtävä 2
```sql
SELECT name AS "airport name"
FROM airport
WHERE iso_country="FR" AND type="large_airport";
```
![image](https://github.com/user-attachments/assets/e7326875-fcb4-4874-aec8-ead3e57f9d4c)

### Tehtävä 3
```sql
SELECT country.name AS "country_name", airport.name AS "airport_name"
FROM country, airport
WHERE airport.iso_country = country.iso_country AND airport.continent="AN";
```
![image](https://github.com/user-attachments/assets/c263ca6c-c80d-4b5f-ac3d-eb779a188ea5)

### Tehtävä 4
```sql
SELECT airport.elevation_ft
FROM airport, game
WHERE game.screen_name="Heini" AND airport.ident=game.location;
```
![image](https://github.com/user-attachments/assets/758b27e1-45d1-4236-9df8-58fc51c2f709)

### Tehtävä 5
```sql
SELECT airport.elevation_ft*0.3048 AS "elevation_m"
FROM airport, game
WHERE game.screen_name="Heini" AND airport.ident=game.location;
```
![image](https://github.com/user-attachments/assets/3604afc9-7456-4ac4-b053-1cc9e2ba9e61)

### Tehtävä 6
```sql
SELECT airport.name
FROM airport, game
WHERE game.screen_name="Ilkka" AND airport.ident=game.location;
```
![image](https://github.com/user-attachments/assets/cc027ca3-31e4-482b-b1e6-449ac14c927d)

### Tehtävä 7
```sql
SELECT country.name
FROM airport, game, country
WHERE game.screen_name="Ilkka" AND airport.ident=game.location AND airport.iso_country=country.iso_country;
```
![image](https://github.com/user-attachments/assets/e271a0a6-219f-4d98-8fd7-e264a79d5292)

### Tehtävä 8 
```sql
SELECT name
FROM goal, goal_reached, game
WHERE game.id = game_id AND goal.id = goal_id AND screen_name = "Heini";
```
![image](https://github.com/user-attachments/assets/d672a72a-bb78-4814-bf6f-1618e41f20ea)

### Tehtävä 9
```sql
SELECT airport.name
FROM airport, game, goal, goal_reached
WHERE ident = location AND game.id = game_id AND goal.id = goal_id
AND screen_name = "Ilkka" AND goal.name = "CLOUDS";
```
![image](https://github.com/user-attachments/assets/ef2d4445-86ca-4cb4-b05d-e800beb820a7)

### Tehtävä 10
```sql
SELECT country.name
FROM country, airport, game, goal, goal_reached
WHERE airport.iso_country = country.iso_country AND ident = location AND game.id = game_id
AND goal.id = goal_id AND screen_name = "Ilkka" and goal.name = "CLOUDS";
```
![image](https://github.com/user-attachments/assets/3a323c2d-c68d-4dff-9cda-ef8693bd7b29)

# 05 Join

### Tehtävä 1
```sql
SELECT country.name AS "country name", airport.name AS "airport name"
FROM airport
INNER JOIN country ON country.iso_country = airport.iso_country
AND country.name = "Finland" AND airport.scheduled_service="yes";
```
![image](https://github.com/user-attachments/assets/a8657d62-2b55-4f4f-a8c9-f4ad16e79c3e)

### Tehtävä 2
```sql
SELECT game.screen_name, airport.name
FROM airport
INNER JOIN game ON game.location = airport.ident;
```
![image](https://github.com/user-attachments/assets/5ca3dd7b-2195-43d2-9604-447285f5bc7e)

### Tehtävä 3
```sql
SELECT game.screen_name, country.name
FROM airport
INNER JOIN game on game.location = airport.ident
INNER JOIN country
WHERE country.iso_country = airport.iso_country;
```
![image](https://github.com/user-attachments/assets/ff1e65af-35ac-42d0-9326-0949b9d7ada2)

### Tehtävä 4
```sql
SELECT airport.name, game.screen_name
FROM airport
LEFT JOIN game ON game.location = airport.ident
WHERE airport.name LIKE "%hels%";
```
![image](https://github.com/user-attachments/assets/fc85fe4c-3ef4-4003-b811-86ce1a3def1c)

### Tehtävä 5
```sql
SELECT name, screen_name
FROM goal
LEFT JOIN goal_reached ON goal.id = goal_id
LEFT JOIN game ON game.id = game_id;
```
![image](https://github.com/user-attachments/assets/af63a2ae-4403-4056-b68a-db635fafe763)
