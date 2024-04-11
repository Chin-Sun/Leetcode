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

# 
