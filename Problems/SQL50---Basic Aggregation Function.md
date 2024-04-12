# No. 620 
**Write your MySQL query statement below**
```
SELECT id, movie, description, rating
FROM Cinema
WHERE mod(id, 2) = 1 AND description != 'boring'
ORDER BY rating DESC;
```
ORDER BY rating ASC(升序)
mod 函数用来计算两个数相除的余数

# No. 1251
**Write your MySQL query statement below**
```
SELECT p.product_id, 
round(IFNULL(sum(p.price*u.units)/sum(u.units),0),2) AS average_price
FROM Prices p LEFT JOIN UnitsSold u
ON p.product_id = u.product_id AND 
u.purchase_date BETWEEN p.start_date AND p.end_date
GROUP BY p.product_id;
```
# No. 1075
**Write your MySQL query statement below**
```
SELECT p.project_id, 
round(sAVG(e.experience_years),2) AS average_years
FROM Project p INNER JOIN Employee e
ON p.employee_id = e.employee_id
GROUP BY p.project_id
```
这个公式sum(e.experience_years)/count(p.project_id)错误， 因为会有null的情况，count()无法去除。所以使用AVG()

# No. 1633
**Write your MySQL query statement below**
```
SELECT r.contest_id, 
round(count(r.contest_id)*100/(SELECT count(user_id) FROM Users),2) AS percentage
FROM Users u JOIN Register r
ON u.user_id = r.user_id
GROUP BY r.contest_id
ORDER BY percentage DESC, contest_id ASC
```
先按照percentage降序排列，再按照contest_id升序排列

# No. 1211
**Write your MySQL query statement below**
```
SELECT query_name, 
round(sum(rating/position)/count(query_name),2) AS quality,
round(sum(if(rating<3, 1, 0))*100/count(query_name),2) AS poor_query_percentage
FROM Queries
WHERE query_name is not null
GROUP BY query_name;
```
上面两个公式sum/count，都可以用AVG代替

# No.1193
