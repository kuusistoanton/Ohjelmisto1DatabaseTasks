Yhteen tauluun kohdistuvien kyselyiden harjoitukset:

1. SELECT * FROM goal;
   ![image](https://github.com/user-attachments/assets/5ce8de59-ca39-4d03-b64d-2b52f3ce0f35)

2. SELECT name type FROM airport WHERE iso_country='FI';
   ![image](https://github.com/user-attachments/assets/8a5cf23f-0f0b-4dab-b936-d5b60b76321c)

3. SELECT name FROM airport WHERE iso_country='FI' order by name;
   ![image](https://github.com/user-attachments/assets/41e36392-04ca-4694-9e92-236aa5da899b)

4. SELECT name, type FROM airport WHERE iso_country='FI' order by type, name;
   ![image](https://github.com/user-attachments/assets/8a48fc83-64a3-4652-879d-c66b3ec7a8fa)

5. SELECT name FROM country WHERE name like "F%";
   ![image](https://github.com/user-attachments/assets/b9106f28-c428-44a4-b5c4-a5d7af7e53ca)

6. SELECT name FROM country WHERE name like "%f%";
   ![image](https://github.com/user-attachments/assets/2e75e741-9dde-49c9-a9de-4f8404389a06)

7. SELECT location FROM game WHERE screen_name='Vesa';
   ![image](https://github.com/user-attachments/assets/71a24ff7-2148-4ad2-abe7-f32a321c663d)

8. SELECT co2_consumed FROM game WHERE screen_name='Ilkka';
   ![image](https://github.com/user-attachments/assets/014f9b5c-4dd0-4db7-b68e-6f83a338b635)

9. SELECT co2_budget FROM game WHERE id=1;
    ![image](https://github.com/user-attachments/assets/1a401beb-3a2d-428f-bc98-0ed4e7653c83)


Where-osan liitosehto harjoitukset

1. SELECT country.name as "country name", airport.name as "airport name" FROM country, airport WHERE country.name='Iceland' and airport.iso_country = country.iso_country;
   ![image](https://github.com/user-attachments/assets/c3194f4a-ac1a-4558-8515-8585d8e48cee)

2. SELECT name as "airport name" FROM airport WHERE iso_country='FR' and type='large_airport';
   ![image](https://github.com/user-attachments/assets/3007b9f6-9ab8-4d94-b1c2-84b489fb338b)

3. SELECT country.name as country_name, airport.name as airport_name FROM country, airport WHERE country.continent='AN' and airport.iso_country = country.iso_country;
   ![image](https://github.com/user-attachments/assets/2f5caa33-bf6b-41d5-b8f7-f41747446f4e)

4. SELECT elevation_ft FROM airport, game WHERE game.screen_name='Heini' and airport.ident=game.location;
   ![image](https://github.com/user-attachments/assets/f3cb6c3f-0c4d-4b62-b329-620631a6149e)

5. SELECT elevation_ft * 0.3048 as elevation_m FROM airport, game WHERE game.screen_name='Heini' and airport.id
ent=game.location;
   ![image](https://github.com/user-attachments/assets/5475c6a9-e74c-44dd-9556-5fd4cdc495c2)

6. SELECT name FROM airport, game WHERE airport.ident = game.location and game.screen_name = 'Ilkka';
   ![image](https://github.com/user-attachments/assets/395a5ea4-60a6-4f72-b394-38e1c1b71376)

7. SELECT country.name FROM country, airport, game WHERE airport.ident = game.location and game.scre
en_name = 'Ilkka' and country.iso_country=airport.iso_country;
   ![image](https://github.com/user-attachments/assets/14602b54-b8ac-4570-890c-3b7d7bde8088)

8. SELECT goal.name FROM goal, game, goal_reached WHERE game.screen_name='Heini' and goal_reached.goal_id=goal.id and goal_reached.game_id=game.id;
   ![image](https://github.com/user-attachments/assets/381a0512-d956-4fbe-ac23-db3fe1be8c71)

9. SELECT airport.name FROM airport, goal_reached, game, goal WHERE game.screen_name='Ilkka' and goal.name='CLOUDS' and goal_reached.goal_id=goal.id and goal_reached.game_id=game.id and airport.ident=game.location;
    ![image](https://github.com/user-attachments/assets/24d23639-7019-4245-a351-091ed845580c)

10. SELECT country.name FROM country, airport, goal_reached, game, goal WHERE game.screen_name='Ilkka' and goal.
name='CLOUDS' and goal_reached.goal_id=goal.id and goal_reached.game_id=game.id and airport.ident=game.location and airport.iso_country=country.iso_country;
   ![image](https://github.com/user-attachments/assets/df285de6-70ac-4164-b613-2fe4e2fda400)


Join harjoitukset

1. SELECT country.name as "country name", airport.name as "airport name" FROM airport inner join country on country.iso_country = airport.iso_country WHERE country.name='Finland' and scheduled_service='yes';
   ![image](https://github.com/user-attachments/assets/bd19a6ec-a5d2-4615-b03c-7e052c9047a6)

2. SELECT screen_name, name FROM game inner join airport on airport.ident = location;
   ![image](https://github.com/user-attachments/assets/4a64c0b7-50c7-4861-a3df-41071d685ce1)

3. SELECT screen_name, country.name FROM game inner join airport on airport.ident = location
-> inner join country on country.iso_country = airport.iso_country;
   ![image](https://github.com/user-attachments/assets/45752aa9-fda4-43a4-838e-afa33d2c845b)

4. SELECT name, screen_name FROM airport left join game on game.location = ident WHERE airport.name like '%Hels%';
   ![image](https://github.com/user-attachments/assets/958cd1ea-83f8-4733-9796-40881815c6e5)

5. SELECT name, screen_name FROM goal left join goal_reached on goal_reached.goal_id = id left join game on game.id = goal_reached.game_id;
   ![image](https://github.com/user-attachments/assets/037a24ed-7d2f-4d7a-b944-a06f27691163)
