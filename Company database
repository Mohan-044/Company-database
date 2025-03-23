create table employee(emp_id int primary key,first_name varchar(40),last_name varchar(40),birth_day date, sex varchar(1),salary int,super_id int,branch_id int);
create table branch(branch_id int primary key,branch_name varchar(40),mgr_id int,mgr_start_date date, foreign key(mgr_id) references employee(emp_id) on delete set null);

alter table employee add foreign key (branch_id) references branch(branch_id) ;
alter table employee add foreign key(super_id) references employee(emp_id);

create table client( client_id int primary key, client_name varchar(40),branch_id int ,foreign key(branch_id) references branch(branch_id));
create table works_with(emp_id int, client_id int,total_sales int,primary key(emp_id,client_id),foreign key(emp_id)references employee(emp_id),foreign key(client_id)references client(client_id));
create table branch_supplier(branch_id int, supplier_name varchar(40),supply_type varchar(40),primary key(branch_id,supplier_name),foreign key(branch_id)references branch(branch_id));

insert into employee values(100,'David','Wallace','1967-11-17','m',250000,null,null);
insert into branch values(1,'corporate',100,'2006-02-09');

update employee set branch_id =1 where emp_id=100;

insert into employee values(101,'jan','Levinson','1961-05-11','f',110000,100,1);
insert into employee values(102,'Michael','Scott','1964-03-15','m',75000,100,null);
insert into branch values(2,'scranton',102,'1992-04-06');

update employee set branch_id=2 where emp_id=102;

insert into employee values(103,'Angela','Martin','1971-06-25','f',63000,102,2);
insert into employee values(104,'Kelly','kapoor','1980-02-05','f',55000,102,2);
insert into employee values(105,'stanley','Hudson','1958-02-19','m',69000,102,2);
insert into employee values(106,'Josh','Porter','1969-09-05','m',78000,100,null);
insert into branch values(3,'Stamford',106,'1998-02-13');

update employee set branch_id = 3 where emp_id =106;

insert into employee values(107,'Andy','Bernard','1973-07-22','m',65000,106,3);
insert into employee values(108,'Jim','Halpert','1971-06-25','m',71000,106,3);

insert into branch_supplier values(2,'Hammer mill','Paper');
insert into branch_supplier values(2,'Uni_ball','Writing utensils');
insert into branch_supplier values(3,'Patriot paper','Paper');
insert into branch_supplier values(2,'J.T.forms & labels','Custom forms');
insert into branch_supplier values(3,'Uni-ball','Writing Utensils');
insert into branch_supplier values(3,'Hammer mill','Paper');
insert into branch_supplier values(3,'Stamford Lables','Custom forms');
--client 
insert into client values(401,'Dunmore highschool',2);
insert into client values(401,'Lackawana country',2);
insert into client values(402,'Fedex',3);
insert into client values(403,'John daly law llc',3);
insert into client values(404,'Scranton whitepages',2);
insert into client values(405,'Times Newspaper',3);
insert into client values(406,'Fedex',2);

-- works_with
insert into works_with values(105,400,55000);
insert into works_with values(102,401,267000);
insert into works_with values(108,402,22500);
insert into works_with values(107,403,5000);
insert into works_with values(108,403,12000);
insert into works_with values(105,404,33000);
insert into works_with values(107,405,26000);
insert into works_with values(102,406,15000);
insert into works_with values(105,406,130000);

select * from works_with;
