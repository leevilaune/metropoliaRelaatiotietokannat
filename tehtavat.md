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






