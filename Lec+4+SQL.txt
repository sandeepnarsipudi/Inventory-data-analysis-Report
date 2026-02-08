

create database test_env

use test_env

select * from [dbo].[Products]

select * from [dbo].[Test Environment Inventory Dataset]

select distinct demand from 
[dbo].[Test Environment Inventory Dataset]

-------------------------------------------------

select a.[Order_Date_DD_MM_YYYY],
a.product_id,a.availability,a.demand,b.product_name,b.unit_price

from [dbo].[Test Environment Inventory Dataset] as a
left join products as b on a.product_id=b.product_id
---------------------------------------------------------

 select * into new_table from 
(select a.[Order_Date_DD_MM_YYYY],
a.product_id,a.availability,a.demand,b.product_name,b.unit_price

from [dbo].[Test Environment Inventory Dataset] as a
left join products as b on a.product_id=b.product_id) x


-----------------------------------


select * from new_table
 



