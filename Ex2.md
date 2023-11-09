## EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
#### DATE:
#### AIM:
To create a manager database and execute DML queries using SQL.
#### DML(Data Manipulation Language)
<div align="justify">
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.</div>

#### List of DML commands: 
<div align="justify">
INSERT: It is used to insert data into a table.<br>
UPDATE: It is used to update existing data within a table.<br>
DELETE: It is used to delete records from a database table.<br>
</div>

#### Create the table as given below:
``` create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
#### insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```
#### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.
#### QUERY:
``` UPDATE manager set salary=salary+(salary*0.10),annualsalary = annualsalary + (annualsalary * 0.10); ```
#### OUTPUT:
![image](https://github.com/NIXANDASS/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118781418/e7053dd2-ef93-4568-91e7-5d71a5d722ca)
#### Q2) Delete the records from manager table where the salary less than 2750.
#### QUERY:
```delete from manager where salary < 2750;```
#### OUTPUT:
![image](https://github.com/NIXANDASS/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118781418/9212a98f-c9fa-4912-a5cc-7d8bed04ee4a)
#### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)
#### QUERY:
``` SELECT ename as "Name", salary * 12 as "Annual Salary" from manager; ```
#### OUTPUT:
![image](https://github.com/NIXANDASS/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118781418/c3ab2084-04b6-41eb-9efa-be0ebd274beb)
#### Q5)	List the names of Clerks from emp table.
#### QUERY:
```SELECT ename from manager where designation='clerk';```
#### OUTPUT:
![image](https://github.com/NIXANDASS/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118781418/f2e5fac1-7883-4070-b45b-33f61ca88013)
#### Q6)	List the names of employee who are not Managers.
#### QUERY:
 ```SELECT ENAME FROM MANAGER WHERE DESIGNATION!='manager';```
#### OUTPUT:
![image](https://github.com/NIXANDASS/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118781418/609c592f-e3e3-45c8-9609-448d4a336578)
#### Q7)	List the names of employees not eligible for commission.
#### QUERY:
```SELECT ENAME FROM MANAGER WHERE commission=0;```
#### OUTPUT:
![image](https://github.com/NIXANDASS/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118781418/a4011624-ab05-4a75-a74a-0be0e70967d7)
#### Q8)	List employees whose name either start or end with ‘s’.
#### QUERY:
```select ename from manager where ename like '%s' or ename like 's%';```
#### OUTPUT:
![image](https://github.com/NIXANDASS/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118781418/b7e8cd10-23a4-45be-9a6b-5ed76f129cdb)
#### Q9) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.
#### QUERY:
```select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;```
#### OUTPUT:
![image](https://github.com/NIXANDASS/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118781418/a43604cc-9757-4c68-8cbf-70418da11ff1)
#### Q10) List the Details of Employees who have joined before 30 Sept 81.
#### QUERY:
```select * from manager where hiredate<'30-SEP-81';```
#### OUTPUT:
![image](https://github.com/NIXANDASS/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118781418/5b2c3a60-bd4d-479e-958f-0c155e8a7571)
#### Q11)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.
#### QUERY:
```SELECT ENAME,DEPTNO,SALARY FROM MANAGER ORDER BY DEPTNO ASC,SALARY DESC;```
#### OUTPUT:
![image](https://github.com/NIXANDASS/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118781418/e0363879-3aff-4849-bbcc-c68ca5ae44df)
#### Q12) List the names of employees not belonging to dept no 30,40 & 10
#### QUERY:
```SELECT ENAME FROM MANAGER WHERE DEPTNO NOT IN (30,40,10);```
#### OUTPUT:
![image](https://github.com/NIXANDASS/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118781418/10748743-3842-4a29-bbb0-7577ae5fc8b3)
#### Q13) Find number of rows in the table EMP
#### QUERY:
```select count(*) from manager;```
#### OUTPUT:
![image](https://github.com/NIXANDASS/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118781418/84d8c28e-4fda-41b9-a748-007dbe19c23c)
#### Q14) Find maximum, minimum and average salary in EMP table.
#### QUERY:
```select max(salary),min(salary),avg(salary) from manager;```
#### OUTPUT:
![image](https://github.com/NIXANDASS/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118781418/312d698c-a16a-44d3-8c70-94a544d8699b)
#### Q15) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.
#### QUERY:
```SELECT designation AS job, COUNT(*) AS num_emp FROM manager GROUP BY designation ORDER BY num_emp DESC;```
#### OUTPUT:
![image](https://github.com/NIXANDASS/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118781418/2df4a33c-c386-401d-8414-4c4ffb701335)
#### RESULT:
