# Kantar-Case-study-on-SQL
This is the case study on the kantar company. I have solved some small questions using SQL queries 

There are 4 questions that i have solved in this case study 

create database kantar;

use kantar;

select * from data1;
select * from data2;
select OrderID from data1;


-- question 1
select count(*)
from data1 d1 left join data2 d2 on d1.OrderID=d2.OrderID and d1.productID=d2.ProductID
where d2.OrderID is null and d2.ProductID is null;
-- question 2
select count(*)
from data2 d2 left join data1 d1 on d1.OrderID=d2.OrderID and d1.productID=d2.ProductID
where d1.OrderID is null and d1.ProductID is null;
-- question 3
select sum(d2.qty)
from data2 d2 left join data1 d1 on d1.OrderID=d2.OrderID and d1.productID=d2.ProductID
where d1.OrderID is null and d1.ProductID is null;
-- question 4
select count(*)
from 
(
select orderID,ProductID
from data1
union
select orderID,ProductID
from data2) as temptable;
