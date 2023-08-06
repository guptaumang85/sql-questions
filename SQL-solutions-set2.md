Q51. Write an SQL query to report the name, population, and area of the big countries.
Return the result table in any order.

A51. `SELECT name, population, area FROM world_table where area >= 3000000 OR population >= 25000000`

Q52. Write an SQL query to report the names of the customer that are not referred by the customer with id
= 2.

A52. `SELECT id, name from customer where referee_id !=2 or referee_id is NULL`

Q53. Write an SQL query to report all customers who never order anything.

A53. `SELECT name from orders o right join customer c on o.customerId = c.id where o.customerId is NULL`

Q54. Write an SQL query to find the team size of each of the employees.

A54. `SELECT employee_id, count(*) over (partition by team_id) as team_size from employee order by employee_id`

Q55. A telecommunications company wants to invest in new countries. The company intends to invest in
the countries where the average call duration of the calls in this country is strictly greater than the
global average call duration.
Write an SQL query to find the countries where this company can invest.
Return the result table in any order.

A55.
```
SELECT q2.name from (SELECT q1.country_code, q1.name, avg(q1.duration) over(partition by q1.name) as avg_call_duration, avg(q1.duration) over() as global_average from (SELECT p.id, c.country_code, cal.duration, cal.caller_id, cal.callee_id, c.name FROM person p inner join country c 
	on p.country_code = c.country_code
    inner join calls cal on p.id = cal.callee_id
union
SELECT p.id, c.country_code, cal.duration, cal.caller_id, cal.callee_id, c.name FROM person p inner join country c 
	on p.country_code = c.country_code
    inner join calls cal on p.id in (cal.caller_id, cal.callee_id)) q1) q2
where q2.avg_call_duration > q2.global_average
group by q2.name
```

Q56. Write an SQL query to report the device that is first logged in for each player.
Return the result table in any order.

A56. `SELECT q.player_id, q.device_id from (SELECT *, row_number() over (partition by player_id order by event_date) as row_rank from activity) q
WHERE q.row_rank = 1`

Q57. Write an SQL query to find the customer_number for the customer who has placed the largest
number of orders

A57. `SELECT customer_number from orders group by customer_number order by count(*) desc limit 1`

Q58. Write an SQL query to report all the consecutive available seats in the cinema.
Return the result table ordered by seat_id in ascending order.

A58. 
```
SELECT q.seat_id from (SELECT *, lag(free) over () as prev, lead(free) over () as next from cinema) q
	WHERE q.free = 1 AND ((q.prev is null and q.next = 1) or (q.prev = 1 AND q.next is null) or (q.prev=1 AND q.next=1)
		or q.prev=0 AND q.next=1)
```

59. Write an SQL query to report the names of all the salespersons who did not have any orders related to
the company with the name "RED". Return the result table in any order.

`SELECT sp.name from SalesPerson sp where sp.sales_id not in (SELECT sales_id FROM orders o join company c on o.com_id = c.com_id where c.name = 'RED')`

60. Write an SQL query to report for every three line segments whether they can form a triangle. Return the result table in any order.

`SELECT *, CASE when x + y > z AND y + z > x AND x + z > y then 'Yes' ELSE 'NO' END as triangle FROM triangle`

61. Write an SQL query to report the shortest distance between any two points from the Point table.
The query result format is in the following example.

`SELECT abs(p1.x - p2.x) as shortest from point p1 join point p2 on p1.x != p2.x order by shortest asc limit 1`

62. Write a SQL query for a report that provides the pairs (actor_id, director_id) where the actor has
cooperated with the director at least three times. Return the result table in any order.

`SELECT actor_id, director_id from ActorDirector GROUP BY actor_id, director_id having count(*) >= 3`

63. Write an SQL query that reports the product_name, year, and price for each sale_id in the Sales table. Return the resulting table in any order.

`SELECT product_name, year, price FROM sales s join product p on s.product_id = p.product_id`

64. Write an SQL query that reports the average experience years of all the employees for each project,
rounded to 2 digits. Return the result table in any order.

`SELECT project_id, round(avg(experience_years),2) from project p join employee e on p.employee_id = e.employee_id GROUP BY project_id`

65. Write an SQL query that reports the best seller by total sales price, If there is a tie, report them all. Return the result table in any order.

`SELECT seller_id FROM sales group by seller_id having SUM(price) = (SELECT SUM(price) as total_price FROM sales group by seller_id order by total_price desc limit 1)`

