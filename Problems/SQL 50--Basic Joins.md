# No.1378
**Write your MySQL query statement below**  
select EmployeeUNI.unique_id, Employees.name
from Employees **left join** EmployeeUNI
on Employees.id = EmployeeUNI.id

# No.1068
**Write your MySQL query statement below**  
select Product.product_name, Sales.year, Sales.price
from Product **inner join** Sales
on Sales.product_id = Product.product_id;

"INNER JOIN" only returns rows where there is at least one match in both tables. If there is no match, the rows are not returned. 
This contrasts with a LEFT JOIN, which returns all rows from the left table and the matched rows from the right table, with the unmatched portions filled with NULLs.

# No.197
**Write your MySQL query statement below**
```
SELECT w1.id
FROM Weather w1, Weather w2
WHERE DATEDIFF(w1.recordDate, w2.recordDate)=1 AND w1.temperature > w2.temperature
```

