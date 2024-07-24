<h1>SQL EXAMPLE AND SOLUTIONS</h1>
<h4>first letter is upper case and after first letter is lower case

select user_id, concat(
    Upper(substring(name,1,1)),
    Lower(substring(name,2,length(name)))
) as name
from Users;



multiple data in one line

select sell_date,count(distinct(product)) as num_sold,
GROUP_CONCAT(distinct(product) ORDER BY product ASC SEPARATOR ',') AS products
from Activities group by sell_date;


cross join 


select s.student_id, s.student_name,Subjects.subject_name,
count(e.subject_name) as attended_exams from Students s
cross join Subjects left join Examinations e on s.student_id=e.student_id and e.subject_name=Subjects.subject_name
group by s.student_id, s.student_name,Subjects.subject_name
order by s.student_id, s.student_name;


if and time stamp use 

SELECT s.user_id, 
  ROUND(AVG(IF(c.action='confirmed',1,0)),2) as confirmation_rate 
FROM Signups s
LEFT JOIN Confirmations c using (user_id)
GROUP BY s.user_id;

join basic

SELECT a.name 
FROM Employee a 
JOIN Employee b ON a.id = b.managerId 
GROUP BY b.managerId 
HAVING COUNT(*) >= 5;

regex in sql  mail check

SELECT *
FROM Users
WHERE mail REGEXP '^[A-Za-z][A-Za-z0-9_\.\-]*@leetcode(\\?com)?\\.com$';




upper and lower case in sql

select user_id, concat(
    Upper(substring(name,1,1)),
    Lower(substring(name,2,length(name)))
) as name
from Users
order by user_id asc;</h4>
