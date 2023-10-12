# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
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
UPDATE manager set salary=salary+(salary*0.10),annualsalary = annualsalary +
(annualsalary * 0.10);

### OUTPUT:
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118668751/740c6278-2c21-49b8-ad31-a8dc8aee8277)

### Q2) Delete the records from manager table where the salary less than 2750.


### QUERY:

delete from manager where salary < 2750;

### OUTPUT:
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118668751/7b186a42-d7f1-4bde-8800-395d890fbc76)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)


### QUERY:
SELECT ename as "Name", salary * 12 as "Annual Salary" from manager;

### OUTPUT:
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118668751/9969660d-60ab-49d1-8056-03085aa76496)

### Q5)	List the names of Clerks from emp table.


### QUERY:

SELECT ename from manager where designation='clerk';
### OUTPUT:
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118668751/b6928da4-9506-48c7-86be-ac2b1e3bb05b)


### Q6)	List the names of employee who are not Managers.


### QUERY:
SELECT ENAME FROM MANAGER WHERE DESIGNATION!='manager';

### OUTPUT:
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118668751/0e7d3e0c-b43e-4483-8593-55900c6ddff5)


### Q7)	List the names of employees not eligible for commission.


### QUERY:
SELECT ENAME FROM MANAGER WHERE commission=0;


### OUTPUT:

![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118668751/98a1c77a-3950-443c-a477-7375dd76497b)

### Q8)	List employees whose name either start or end with ‘s’.


### QUERY:

select ename from manager where ename like '%s' or ename like 's%';

### OUTPUT:
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118668751/5c324dc8-646f-4c87-b659-bf62bf5e81f7)


### Q9) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.


### QUERY:
select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;


### OUTPUT:

![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118668751/474603c4-4d85-4d54-aa90-4b5e08561456)

### Q10) List the Details of Employees who have joined before 30 Sept 81.


### QUERY:
select * from manager where hiredate<'30-SEP-81';


### OUTPUT:
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118668751/8da93f18-e5f7-47be-857f-ba767625dd88)


### Q11)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.


### QUERY:

SELECT ENAME,DEPTNO,SALARY FROM MANAGER ORDER BY DEPTNO ASC,SALARY DESC;

### OUTPUT:

![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118668751/c2a66abf-7475-4b16-a50c-61c667ae9008)

### Q12) List the names of employees not belonging to dept no 30,40 & 10


### QUERY:
SELECT ENAME FROM MANAGER WHERE DEPTNO NOT IN (30,40,10);


### OUTPUT:
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118668751/e6b4322d-06a2-4451-aaf1-d075098d4abe)

### Q13) Find number of rows in the table EMP

### QUERY:
select count(*) from manager;


### OUTPUT:
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118668751/f8eea69e-25b2-494a-8a1c-d07b18a10e60)


### Q14) Find maximum, minimum and average salary in EMP table.

### QUERY:
select max(salary),min(salary),avg(salary) from manager;

### OUTPUT:
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118668751/d17a767a-2d2b-4419-8cd5-5b763a020fef)


### Q15) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
SELECT designation AS job, COUNT(*) AS num_emp FROM manager GROUP BY designation ORDER
BY num_emp DESC;


### OUTPUT:
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118668751/52c5a565-7236-4213-b391-c19d1b91032d)

