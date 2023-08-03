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