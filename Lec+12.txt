use prod;

Create table new_table as 
select 
a.`Order Date (DD/MM/YYYY)` as `Order_Date_DD_MM_YYYY`,
a.`Product ID` as `product_id`,
a.availability,
a.demand,
b.`Product Name` as `product_name`,
b.`Unit Price ($)` as `unit_price`
from
prod.`prod env inventory dataset` as a left join prod.products as b
on a.`Product ID` = b.`Product ID`