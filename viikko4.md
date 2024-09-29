# join harjoitukset:
# tehtävä 1
SELECT country.name as "country name", airport.name as "airport name"
FROM airport inner join country on
airport.iso_country = country.iso_country
WHERE country.name = "Finland"and scheduled_service = "yes" ;

![screenshot](tehtava1-4.png)

# tehtävä2
SELECT screen_name , airport.name
FROM game inner join airport on 
location = ident;

![screenshot](tehtava2-4.png)

# tehtävä 3
SELECT screen_name, country.name
FROM game inner join airport on 
location = ident inner join country on
airport.iso_country = country.iso_country;

![screenshot](tehtava3-4.png)

# tehtava 4
SELECT airport.name, screen_name
FROM airport left join game on 
ident = location
WHERE name like "%Hels%";

![screenshot](tehtava4-4.png)

# tehtävä 5
SELECT name, screen_name
FROM goal left join goal_reached on 
goal.id = goal_id  left join game
on game.id = game_id;

![screenshot](tehtava5-4.png)

# Sisäkysely harjoitukset:
# tehtävä 6
select name
from country
where iso_country in(
select iso_country
from airport
where name like "Satsuma%"

);
![screenshot](tehtava6-4.png)

# tehtävä 7
select name
from airport
where iso_country in(
select iso_country
from country
where name = "Monaco"

);
![screenshot](tehtava7-4.png)

# tehtävä 8
select screen_name
from game
where id in (
select game_id
from goal_reached
where goal_id in(
select id
from goal
where name = "CLOUDS"
)

);
![screenshot](tehtava8-4.png)

# tehtävä 9
select name
from country
where iso_country not in (
select iso_country
from airport);
![screenshot](tehtava9-4.png)

# tehtävä 10
select name
from goal
where id not in (
select goal_id
from goal_reached
where game_id not in (
select id
from game
where screen_name ="Heini"));
![screenshot](tehtava10-4.png)