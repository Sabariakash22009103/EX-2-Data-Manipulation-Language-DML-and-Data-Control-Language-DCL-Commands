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
create table manager(enumber numeric(6),ename varchar(15),salary numeric(5),commission numeric(4),annualsalary numeric(7),Hiredate date,designation varchar(10),deptno numeric(2),reporting varchar(10));
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
```sql
update manager set salary=salary+(salary*0.10);

```

### OUTPUT:
![image](https://github.com/Sabariakash22009103/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119390227/a3eaf989-22d9-416c-afb2-8dc3b8230771)

### Q2) Delete the records from manager table where the salary less than 2750.


### QUERY:
```sql
delete from manager where salary<2750;
```

### OUTPUT:
![image](https://github.com/Sabariakash22009103/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119390227/f871bb11-f76d-49ed-9c21-0283e11624b2)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)


### QUERY:
```sql
select ename as "Name",salary*12 as "Annual salary" from manager;
```

### OUTPUT:
![image](https://github.com/Sabariakash22009103/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119390227/a0656ce8-e196-4b93-b53f-40e8fa2d5698)

### Q4)	List the names of Clerks from emp table.


### QUERY:
```sql
select ename from manager where designation='clerk';
```

### OUTPUT:

![image](https://github.com/Sabariakash22009103/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119390227/f41efc7d-7329-4d5e-ac5a-e9fcd07f0a06)

### Q5)	List the names of employee who are not Managers.


### QUERY:
```sql
select ename from manager where designation <> 'manager';
```

### OUTPUT:
![image](https://github.com/Sabariakash22009103/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119390227/521fa217-e182-4fe1-b2aa-3cb72d40ac0a)


### Q6)	List the names of employees not eligible for commission.


### QUERY:
```sql
select ename from manager where commission=0;
```

### OUTPUT:
![image](https://github.com/Sabariakash22009103/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119390227/8bdf2a51-51a1-4b35-8cbb-d7aa6037c1d9)


### Q7)	List employees whose name either start or end with ‘s’.


### QUERY:
```sql
select ename from manager where ename like '%s' or ename like 's%';
```

### OUTPUT:
![image](https://github.com/Sabariakash22009103/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119390227/2e0a07a3-392d-43a5-a802-457eed9ccc3b)


### Q8) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.


### QUERY:
```sql
select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;
```

### OUTPUT:
![image](https://github.com/Sabariakash22009103/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119390227/1a0b5fd7-ef1b-42a6-a619-7d1a4767233a)


### Q9) List the Details of Employees who have joined before 30 Sept 81.


### QUERY:
```sql
SELECT * FROM manager WHERE Hiredate < '1981-09-30';
```

### OUTPUT:
![image](https://github.com/Sabariakash22009103/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119390227/7aa29c4a-6857-4791-a804-e77b3178edae)


### Q10)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.


### QUERY:
```sql
 select ename,deptno,salary from manager order by deptno asc,salary desc;
```

### OUTPUT:
![image](https://github.com/Sabariakash22009103/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119390227/7561db47-5ee4-44a3-952a-6456168f66fe)


### Q11) List the names of employees not belonging to dept no 30,40 & 10


### QUERY:
```sql
select ename from manager where deptno not in (30,40,10);
```

### OUTPUT:
![image](https://github.com/Sabariakash22009103/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119390227/8de4d7d7-09f0-414c-8d88-2d6c58db5a34)

### Q12) Find number of rows in the table EMP

### QUERY:
```sql
 select count(*) from manager;
```

### OUTPUT:
![image](https://github.com/Sabariakash22009103/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119390227/1ac23a32-e0c4-4a25-9e27-13013b263ddb)


### Q13) Find maximum, minimum and average salary in EMP table.

### QUERY:

### MAXIMUM:
```sql
select max(salary) from manager;
```

### OUTPUT:
![image](https://github.com/Sabariakash22009103/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119390227/19c284e3-9b04-4c27-afeb-82768772a63b)

### MINIMUM:
```sql
select min(salary) from manager;
```
### OUTPUT:
![image](https://github.com/Sabariakash22009103/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119390227/ccab6fb2-5070-48f5-a62b-c2b6afe1f034)

### AVERAGE:
```sql
select avg(salary) from manager;
```
### OUTPUT:
![image](https://github.com/Sabariakash22009103/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119390227/2ceab41c-3291-4f79-897c-5e3b43f79cc0)

### Q14) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```sql
SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;
```

### OUTPUT:
![image](https://github.com/Sabariakash22009103/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119390227/4153086d-49f3-42c9-9753-118e06e11b3a)

## Result:
 To create a manager database and execute DML queries using SQL is executed successfully.
