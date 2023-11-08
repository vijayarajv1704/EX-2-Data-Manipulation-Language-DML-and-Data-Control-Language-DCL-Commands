
# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL

## Date:

## AIM:
To create a manager database and execute DML queries using SQL.


## DML(Data Manipulation Language)
<div align="justify">
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.
</div>

## List of DML commands: 
<div align="justify">
INSERT: It is used to insert data into a table.<br>
UPDATE: It is used to update existing data within a table.<br>
DELETE: It is used to delete records from a database table.<br>
</div>

## Create the table as given below:
```sql
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
```
update manager set salary=salary+(salary*0.10);
```
### OUTPUT:
![image](https://github.com/vijayarajv1704/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121303741/c53354fd-f705-48b7-b6ef-ed91406a6817)

### Q2) Delete the records from manager table where the salary less than 2750.
### QUERY:
```
delete from manager where salary<2750;
```
### OUTPUT:
![image](https://github.com/vijayarajv1704/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121303741/eb2ad97d-7073-412b-9b2d-64d5e5b61332)


### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)
### QUERY:
```
select ename as "Name",salary*12 as "Annual salary" from manager;
```
### OUTPUT:
![image](https://github.com/vijayarajv1704/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121303741/89e5f8d6-088a-4d58-a45f-4bd8ff08e412)


### Q4) List the names of Clerks from emp table.
### QUERY:
```
select ename from manager where designation='clerk';
```
### OUTPUT:
![image](https://github.com/vijayarajv1704/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121303741/a3214233-d176-4f1e-bb55-181ed6ce6711)


### Q5)	List the names of employee who are not Managers.
### QUERY:
```
select ename from manager where designation <> 'manager';
```
### OUTPUT:
![image](https://github.com/vijayarajv1704/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121303741/06bb405c-1dac-4810-9d80-afe9b6085279)

### Q6)	List the names of employees not eligible for commission.
### QUERY:
```
select ename from manager where commission=0;
```
### OUTPUT:
![image](https://github.com/vijayarajv1704/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121303741/f973cf7e-61a0-4595-af81-fd6790c124b5)


### Q7)	List employees whose name either start or end with ‘s’
### QUERY:
```
select ename from manager where ename like '%s' or ename like 's%';
```
### OUTPUT:
![image](https://github.com/vijayarajv1704/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121303741/8b7c5965-c175-4039-8d50-1eb603f70057)


### Q8) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.
### QUERY:
```
select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;
```
### OUTPUT:
![image](https://github.com/vijayarajv1704/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121303741/ac349e8f-dccc-46ae-871e-b601c242c58d)


### Q9) List the Details of Employees who have joined before 30 Sept 81.
### QUERY:
```
select * from manager where hiredate<to_date('1981-09-30','YYYY-MM-DD');
```
### OUTPUT:
![image](https://github.com/vijayarajv1704/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121303741/e1735ecd-2c52-4091-be85-9c7c93f88d37)


### Q10)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.
### QUERY:
```
select ename,deptno,salary from manager order by deptno asc,salary desc;
```
### OUTPUT:
![image](https://github.com/vijayarajv1704/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121303741/a8559d65-8ed8-4e9e-a072-5a6cc81f2034)


### Q11) List the names of employees not belonging to dept no 30,40 & 10
### QUERY:
```
select ename from manager where deptno not in (30,40,10);
```
### OUTPUT:
![image](https://github.com/vijayarajv1704/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121303741/68c68c55-a7fd-4245-9986-7871a1e16bda)


### Q12) Find number of rows in the table EMP
### QUERY:
```
select count(*) from manager;
```
### OUTPUT:
![image](https://github.com/vijayarajv1704/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121303741/9791b4ad-9473-4821-a631-3a4c7d9e7027)


### Q13) Find maximum, minimum and average salary in EMP table.
### QUERY:
## MAXIMUM:
```
select max(salary) from manager;
```
### OUTPUT:
![image](https://github.com/vijayarajv1704/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121303741/fb552fd7-38e9-4b4e-a570-b94583e44024)


## MINIMUM:
```
select min(salary) from manager;
```
## OUTPUT:
![image](https://github.com/vijayarajv1704/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121303741/b62e7b60-583a-4c1c-aed0-17eabf4b8521)

## AVERAGE:
```
select avg(salary) from manager;
```
## OUTPUT:
![image](https://github.com/vijayarajv1704/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121303741/065e1662-10de-4dc8-a8bd-3836043dd40a)

### Q14) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```
SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;
```
### OUTPUT:
![image](https://github.com/vijayarajv1704/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121303741/427dd47d-f8a6-4eb3-81dc-e52b604297f0)

### RESULT:
Hence successfully created a manager database and execute DML queries using SQL.
