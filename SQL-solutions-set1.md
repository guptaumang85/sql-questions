Q1. Query all columns for all American cities in the CITY table with populations larger than 100000.
The CountryCode for America is USA.

A1. 
```
  CREATE DATABASE assignment;

USE assignment;

CREATE TABLE city (
    id INT,
    name VARCHAR(17),
    countrycode VARCHAR(3),
    district VARCHAR(20),
    population INT
);

INSERT INTO city VALUES (6,'Rotterdam','NLD','Zuid-Holland',593321),
(19,'Zaanstad','NLD','Noord-Holland',135621),
(214,'Porto Alegre','BRA','Rio Grande do Sul',1314032),
(397,'Lauro de Freitas','BRA','Bahia',109236),
(547,'Dobric','BGR','Varna',100399),
(552,'Bujumbura','BDI','Bujumbura',300000),
(554,'Santiago de Chile','CHL','Santiago',4703954),
(626,'al-Minya','EGY','al-Minya',201360),
(646,'Santa Ana','SLV','Santa Ana',139389),
(762,'Bahir','Dar','ETH Amhara',96140),
(796,'Baguio','PHL','CAR',252386),
(896,'Malungon','PHL','Southern Mindanao',93232),
(904,'Banjul','GMB','Banjul',42326),
(924,'Villa','GTM','Nueva',101295),
(990,'Waru','IDN','East Java',124300),
(1155,'Latur','IND','Maharashtra',197408),
(1222,'Tenali','IND','Andhra Pradesh',143726),
(1235,'Tirunelveli','IND','Tamil Nadu',135825),
(1256,'Alandur','IND','Tamil Nadu',125244),
(1279,'Neyveli','IND','Tamil Nadu',118080),
(1293,'Pallavaram','IND','Tamil Nadu',111866),
(1350,'Dehri','IND','Bihar',94526),
(1383,'Tabriz','IRN','East Azerbaidzan',1191043),
(1385,'Karaj','IRN','Teheran',940968),
(1508,'Bolzano','ITA','Trentino-Alto Adige',97232),
(1520,'Cesena','ITA','Emilia-Romagna',89852),
(1613,'Neyagawa','JPN','Osaka',257315),
(1630,'Ageo','JPN','Saitama',209442),
(1661,'Sayama','JPN','Saitama',162472),
(1681,'Omuta','JPN','Fukuoka',142889),
(1739,'Tokuyama','JPN','Yamaguchi',107078),
(1793,'Novi Sad','YUG','Vojvodina',179626),
(1857,'Kelowna','CAN','British Colombia',89442),
(1895,'Harbin','CHN','Heilongjiang',4289800),
(1900,'Changchun','CHN','Jilin',2812000),
(1913,'Lanzhou','CHN','Gansu',1565800),
(1947,'Changzhou','CHN','Jiangsu',530000),
(2070,'Dezhou','CHN','Shandong',195485),
(2081,'Heze','CHN','Shandong',189293),
(2111,'Chenzhou','CHN','Hunan',169400),
(2153,'Xianning','CHN','Hubei',136811),
(2192,'Lhasa','CHN','Tibet',120000),
(2193,'Lianyuan','CHN','Hunan',118858),
(2227,'Xingcheng','CHN','Liaoning',102384),
(2273,'Villavicencio','COL','Meta',273140),
(2384,'Tong-yong','KOR','Kyongsangnam',131717),
(2386,'Yongju','KOR','Kyongsangbuk',131097),
(2387,'Chinhae','KOR','Kyongsangnam',125997),
(2388,'Sangju','KOR','Kyongsangbuk',124116),
(2406,'Herakleion','GRC','Crete',116178),
(2440,'Monrovia','LBR','Montserrado',850000),
(2462,'Lilongwe','MWI','Lilongwe',435964),
(2505,'Taza','MAR','Taza-Al Hoceima-Taou',92700),
(2555,'Xalapa','MEX','Veracruz',390058),
(2602,'Ocosingo','MEX','Chiapas',171495),
(2609,'Nogales','MEX','Sonora',159103),
(2670,'San Pedro Cholula','MEX','Puebla',99734),
(2689,'Palikir','FSM','Pohnpei',8600),
(2706,'Tete','MOZ','Tete',101984),
(2716,'Sittwe (Akyab)','MMR','Rakhine',137600),
(2922,'Carolina','PRI','Carolina',186076),
(2967,'Grudziadz','POL','Kujawsko-Pomorskie',102434),
(2972,'Malabo','GNQ','Bioko',40000),
(3073,'Essen','DEU','Nordrhein-Westfalen',599515),
(3169,'Apia','WSM','Upolu',35900),
(3198,'Dakar','SEN','Cap-Vert',785071),
(3253,'Hama','SYR','Hama',343361),
(3288,'Luchou','TWN','Taipei',160516),
(3309,'Tanga','TZA','Tanga',137400),
(3353,'Sousse','TUN','Sousse',145900),
(3377,'Kahramanmaras','TUR','Kahramanmaras',245772),
(3430,'Odesa','UKR','Odesa',1011000),
(3581,'St Petersburg','RUS','Pietari',4694000),
(3770,'Hanoi','VNM','Hanoi',1410000),
(3815,'El Paso','USA','Texas',563662),
(3878,'Scottsdale','USA','Arizona',202705),
(3965,'Corona','USA','California',124966),
(3973,'Concord','USA','California',121780),
(3977,'Cedar Rapids','USA','Iowa',120758),
(3982,'Coral Springs','USA','Florida',117549),
(4054,'Fairfield','USA','California',92256),
(4058,'Boulder','USA','Colorado',91238),
(4061,'Fall River','USA','Massachusetts',9055);
```
` SELECT * FROM city WHERE countrycode='USA' AND population > 100000;`

Q2. Query the NAME field for all American cities in the CITY table with populations larger than 120000.
The CountryCode for America is USA.
The CITY table is described as follows:

A2. `SELECT name from city where countrycode = 'USA' AND population > 120000;`

Q3. Query all columns (attributes) for every row in the CITY table
A3. `SELECT * FROM city;`

Q4. Query all columns for a city in CITY with the ID 1661.
A4. `SELECT * FROM city WHERE id = 1661`

Q5. Query all attributes of every Japanese city in the CITY table. The COUNTRYCODE for Japan is
JPN.
The CITY table is described as follows:
A5. `SELECT * FROM city WHERE countrycode = 'JPN';`

Q6. Query the names of all the Japanese cities in the CITY table. The COUNTRYCODE for Japan is
JPN.
A6. `SELECT name FROM city WHERE countrycode = 'JPN';`

Q7. Query a list of CITY and STATE from the STATION table
A7. 
```
CREATE TABLE station (
    id int,
    city VARCHAR(50),
    state VARCHAR(2),
    lat_n int,
    long_w INT
);

`SELECT city, state FROM station;`
```

Q8. Query a list of CITY names from STATION for cities that have an even ID number. Print the results
in any order, but exclude duplicates from the answer.
A8. `SELECT distinct city FROM station where id %2 = 0;`

Q9. Find the difference between the total number of CITY entries in the table and the number of
distinct CITY entries in the table.
A9. `SELECT (count(city) - count(DISTINCT city) FROM station);`

Q10. Query the two cities in STATION with the shortest and longest CITY names, as well as their
respective lengths (i.e.: number of characters in the name). If there is more than one smallest or
largest city, choose the one that comes first when ordered alphabetically
A10. 
```
SELECT city as shortest_city, length(city) FROM station ORDER BY length(city) ASC, city ASC LIMIT 1;
SELECT city as longest_city, length(city) FROM station ORDER BY length(city) DESC, city ASC LIMIT 1;
```

Q11. Query the list of CITY names starting with vowels (i.e., a, e, i, o, or u) from STATION. Your result
cannot contain duplicates.
A11. `SELECT DISTINCT city FROM station where substring(city, 1,1) IN ('a', 'e', 'i', 'o', 'u');`

Q12. Query the list of CITY names ending with vowels (a, e, i, o, u) from STATION. Your result cannot
contain duplicates.
A12. `SELECT DISTINCT city FROM station where substring(city, length(city),1) IN ('a', 'e', 'i', 'o', 'u');`

Q13. Q13. Query the list of CITY names from STATION that do not start with vowels. Your result cannot
contain duplicates.
A13. `SELECT DISTINCT city FROM station where substring(city, 1,1) NOT IN ('a', 'e', 'i', 'o', 'u');`

Q14. Query the list of CITY names from STATION that do not end with vowels. Your result cannot
contain duplicates.
A14. `SELECT DISTINCT city FROM station where SUBSTRING(city, LENGTH(city), 1) NOT IN ('a', 'e', 'i', 'o', 'u');`

Q15. Query the list of CITY names from STATION that either do not start with vowels or do not end
with vowels. Your result cannot contain duplicates
A15. `SELECT DISTINCT city FROM station where substring(city, 1,1) NOT IN ('a', 'e', 'i', 'o', 'u') OR
SUBSTRING(city, LENGTH(city), 1) NOT IN ('a', 'e', 'i', 'o', 'u');`

Q16. Query the list of CITY names from STATION that do not start with vowels and do not end with
vowels. Your result cannot contain duplicates.
A16. `SELECT DISTINCT city FROM station where substring(city, 1,1) NOT IN ('a', 'e', 'i', 'o', 'u') AND
SUBSTRING(city, LENGTH(city), 1) NOT IN ('a', 'e', 'i', 'o', 'u');`

Q17. Write an SQL query that reports the products that were only sold in the first quarter of 2019. That is,
between 2019-01-01 and 2019-03-31 inclusive.
A17. `SELECT * FROM product WHERE product_id NOT IN (SELECT product_id from sales where sale_date > '2019-03-31')`

Q18. Write an SQL query to find all the authors that viewed at least one of their own articles.
Return the result table sorted by id in ascending order
A18. `SELECT DISTINCT author_id FROM views WHERE author_id = viewer_id ORDER BY author_id;`

Q19. Write an SQL query to find the percentage of immediate orders in the table, rounded to 2 decimal
places.
A19. `SELECT ROUND(count(1)*100/ (SELECT count(1) FROM delivery), 2) as immediate_percentage from delivery where order_date = customer_pref_delivery_date;`

Q20. Write an SQL query to find the ctr of each Ad. Round ctr to two decimal points.
Return the result table ordered by ctr in descending order and by ad_id in ascending order in case of a
tie.
A20. 
```
SELECT q.ad_id, (case when base != 0 then round(q.num*100/q.base,2) else 0 end) AS ctr FROM (
    SELECT ad_id, sum( case when action = 'Clicked' then 1 else 0 end ) as num, sum( case when action = 'Clicked' or action = 'Viewed' then 1 else 0 end) as base FROM ads GROUP BY ad_id
) q;
```

Q21. Write an SQL query to find the team size of each of the employees
A21. `SELECT employee_id, count(team_id) over (partition by team_id) as team_size from employee order by employee_id `

Q22.Write an SQL query to find the type of weather in each country for November 2019.
The type of weather is:
● Cold if the average weather_state is less than or equal 15,
● Hot if the average weather_state is greater than or equal to 25, and
● Warm otherwise.
A22. 
```
SELECT c.country_name, (CASE 
    WHEN AVG(w.weather_state) <= 15 THEN 'Cold'
    WHEN AVG(w.weather_state) > 15 AND AVG(w.weather_state) <= 25 then 'Hot'
    ELSE 'Warm' 
END) as weather_type FROM countries as c INNER JOIN weather as w
    on c.country_id = w.country_id
    where w.day like '2019-11-__' GROUP BY country_name
```

Q23. Write an SQL query to find the average selling price for each product. average_price should be
rounded to 2 decimal places.
A23. 
```
SELECT p.product_id, round(sum(price*units)/sum(units),2) as average_price FROM prices as p JOIN units_sold as u on
    p.product_id = u.product_id WHERE purchase_date BETWEEN start_date AND end_date
GROUP BY product_id
```

Q24. Write an SQL query to report the first login date for each player.
A24. `SELECT player_id, event_date as first_login from (SELECT player_id, event_date, row_number() over(partition by player_id order by event_date) as num from activity) q where q.num = 1`

Q25. Same as Q24
A25. Same as A24

Q26. Write an SQL query to get the names of products that have at least 100 units ordered in February 2020
and their amount.
A26. `SELECT p.product_id, product_name, sum(unit) as unit from products p inner join 
    orders o on p.product_id = o.product_id where o.order_date like '2020-02-__'
    group by product_id having unit >= 100
`

Q27. Write an SQL query to find the users who have valid emails.
A valid e-mail has a prefix name and a domain where:
- The prefix name is a string that may contain letters (upper or lower case), digits, underscore
'_', period '.', and/or dash '-'. The prefix name must start with a letter.
- The domain is '@leetcode.com'.
A27. `SELECT * from users WHERE REGEXP_LIKE(mail, '^[a-zA-Z][a-zA-Z0-9\_\.\-]*@leetcode.com');`

Q28. Write an SQL query to report the customer_id and customer_name of customers who have spent at
least $100 in each month of June and July 2020
A28. 
```
SELECT c.customer_id, c.name, sum(price*quantity) as cost from customers c inner join orders o on c.customer_id = o.customer_id
    inner join product p on p.product_id = o.product_id where order_date like '2020-06-__' or order_date like '2020-07-__'
    group by c.customer_id
    having (
    sum(case when o.order_date like '2020-06%' then o.quantity*p.price else 0 end) >= 100
    and
    sum(case when o.order_date like '2020-07%' then o.quantity*p.price else 0 end) >= 100
); 
```

Q29. Write an SQL query to report the distinct titles of the kid-friendly movies streamed in June 2020
A29. `SELECT distinct title from content c join tv_program as tvp on 
    c.content_id = tvp.content_id where program_date like ('2020-06-__') and kids_content = 'Y'`

Q30. Write an SQL query to find the npv of each query of the Queries table.Return
the result table in any order.
A30. `SELECT q.*, coalesce(npv.npv,0) as Npv  from npv right join queries q on npv.id = q.id and npv.year = q.year`

Q31. Same as Q30
A31. Same as A30

Q32. Write an SQL query to show the unique ID of each user, If a user does not have a unique ID replace just show null.
A32. `select u.unique_id, e.name from employees e left join employeeUNI u on e.id = u.id;`

Q33. Write an SQL query to report the distance travelled by each user.
Return the result table ordered by travelled_distance in descending order, if two or more users travelled the same distance, order them by their name in ascending order.
A33. `select u.name, coalesce(sum(r.distance),0) as travelled_distance from users u left join rides r on u.id = r.user_id group by u.name order by travelled_distance desc, u.name;`

Q34. Write an SQL query to get the names of products that have at least 100 units ordered in February 2020 and their amount. Return result table in any order
A34. `select p.product_name, sum(o.unit) as unit
from
Products p
left join
Orders o
on p.product_id = o.product_id
where month(o.order_date) = 2 and year(o.order_date) = 2020
group by p.product_id
having unit >= 100;`

Q35. Write an SQL query to:
- Find the name of the user who has rated the greatest number of movies. In case of a tie,
return the lexicographically smaller user name.
- Find the movie name with the highest average rating in February 2020. In case of a tie, return
the lexicographically smaller movie name.
A35 `SELECT name as results from (SELECT u.user_id, u.name, count(u.user_id) as movie_count from users u inner join movie_rating mr on u.user_id = mr.user_id group by u.user_id, u.name order by movie_count desc limit 1) first_query
union SELECT title as results from (SELECT m.movie_id, m.title, avg(rating) as avg_rating from movie_rating mr join movies m on m.movie_id = mr.movie_id where mr.created_at like '2020-02-__' group by m.movie_id order by avg_rating desc, title asc limit 1) second_query`

Q36. Write an SQL query to report the distance travelled by each user.
Return the result table ordered by travelled_distance in descending order, if two or more users
travelled the same distance, order them by their name in ascending order.
A36. `SELECT u.id, u.name, coalesce(sum(distance),0) as travelled_distance from users u left join rides r on u.id = r.user_id group by u.id order by travelled_distance desc, name asc`

Q37. Same as Q32
A37. Same as A32

Q38. Write an SQL query to find the id and the name of all students who are enrolled in departments that no longer exist.
A38. `SELECT id,name from students where department_id not in (SELECT id from departments)`

Q39. Write an SQL query to report the number of calls and the total call duration between each pair of distinct persons (person1, person2) where person1 < person2.
A39. `select t.person1, t.person2, count(*) as call_count, sum(t.duration) as
total_duration
from
(select duration,
case when from_id < to_id then from_id else to_id end as person1,
case when from_id > to_id then from_id else to_id end as person2
from Calls) t
group by t.person1, t.person2;`

Q40. Same as Q23
A40. Same as A23

Q41. Write an SQL query to report the number of cubic feet of volume the inventory occupies in each warehouse.
A41. `SELECT name, sum(units*length*width*height) as volume from warehouse w join products p on w.product_id = p.product_id group by name`


Q42. Write an SQL query to report the difference between the number of apples and oranges sold each day. Return the result table ordered by sale_date.
A42. `SELECT q.sale_date, (q.apples_sold - q.oranges_sold) as diff from (SELECT sale_date, max(case when fruit = 'apples' then sold_num else 0 end) as apples_sold,`
