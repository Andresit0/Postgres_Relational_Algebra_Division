# RELATIONAL ALGEBRA DIVISION IMPLEMENTED IN POSTGRES

If we have two tables A, B where the name of the attributes of A are 1,2 and the name for attribute B is 2. Then, A/B in the relational algebra could be found using 

	select A.1 from A, B where A.2 = B.2 group by A.1 having count(*)= (select count(*) from B);

If we have two tables A, B where the name of the attributes of A are 1,2,3,4, and the name for attributes B are 3,4. Then, A/B in the relational algebra could be found using 

	select A.1, A.2 from A, B where A.3 = B.3 and A.4 = B.4 group by A.1, A.2 having count(*)= (select count(*) from B);
	
Using this deduction, we could use the function "divide (divide_function.txt)" that returns a "div" temporal table. Then, we could obtain a division of two tables with:

	select divide('table_1','table_2');  --table_1_name / table_2_name
	select * from div;