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

# No.1661
**Write your MySQL query statement below**
```
SELECT a1.machine_id, ROUND(avg(a1.timestamp-a2.timestamp),3) AS processing_time
FROM Activity a1 JOIN Activity a2
ON a1.machine_id=a2.machine_id AND a1.process_id=a2.process_id
AND a1.activity_type = 'end' AND a2.activity_type = 'start'
GROUP BY a1.machine_id;
```

# No.577
**Write your MySQL query statement below**
```
SELECT e.name, b.bonus
FROM Employee e LEFT JOIN Bonus b
ON e.empId = b.empId 
WHERE b.bonus < 1000 OR b.bonus is null
```

# No.1280
**Write your MySQL query statement below**
```
SELECT stu.student_id, stu.student_name, sub.subject_name, count(e.subject_name) as attended_exams
FROM Students stu 
CROSS JOIN Subjects sub 
LEFT JOIN Examinations e
ON stu.student_id = e.student_id
AND sub.subject_name = e.subject_name 
GROUP BY stu.student_id, stu.student_name, sub.subject_name
ORDER BY stu.student_id, sub.subject_name;
```

# No. 570
**Write your MySQL query statement below**
```
# Write your MySQL query statement below
SELECT e1.name
FROM Employee e1
JOIN Employee e2
ON e1.id = e2.managerId
GROUP BY e1.id
-- name is not unique, so that's why we use ei.id to group by
HAVING count(e1.id)>=5
```
# No. 1934
**Write your MySQL query statement below**
```
SELECT s.user_id, round(AVG(if(c.action="confirmed",1,0)),2) AS confirmation_rate
FROM Signups s
LEFT JOIN Confirmations c
ON s.user_id = c.user_id
GROUP BY s.user_id
```
