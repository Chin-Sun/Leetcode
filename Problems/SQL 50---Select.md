# No.1757
**Write your MySQL query statement below**
SELECT product_id
From Products
WHERE low_fats = 'Y' AND
recyclable = 'Y'

# No.584
**Write your MySQL query statement below**
SELECT name
FROM Customer
WHERE COALESCE(referee_id,0) <> 2;

# No.595. Big Countries
**Write your MySQL query statement below**
SELECT name, area, population
From World
Where (area >= 3000000 OR
population >= 25000000) 

# No. 1148
**Write your MySQL query statement below**
SELECT distinct author_id as id
FROM Views
WHERE author_id = viewer_id
ORDER BY id;

# No.Article View I
**Write your MySQL query statement below**
SELECT distinct author_id as id
FROM Views
WHERE author_id = viewer_id
ORDER BY id;

# No.1683
**Write your MySQL query statement below**
select tweet_id
from Tweets
where char_length(content) > 15;
