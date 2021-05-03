/*EXPERIMENT NO. 3: DDL COMMANDS  and CONSTRAINTS*/

/*1.Create a  table emp with attributes empno number(4)as  primary key, ename char(10),hiredate, salary, commission */
CREATE TABLE emp(EMPNO INT(4) PRIMARY KEY, ENAME CHAR(10), HIREDATE DATE, SALARY INT(5), COMMISSION INT(5));

/*insert 5 rows of data*/
INSERT INTO emp(EMPNO,ENAME,HIREDATE,SALARY) VALUES (101,'RAMESH','1980-01-17',5000);
INSERT INTO emp(EMPNO,ENAME,HIREDATE,SALARY,COMMISSION) VALUES (102,'AJAY','1985-07-05',5000,500);
INSERT INTO emp(EMPNO,ENAME,HIREDATE,SALARY) VALUES (103,'RAVI','1981-08-12',1500);
INSERT INTO emp(EMPNO,ENAME,HIREDATE,SALARY,COMMISSION) VALUES (104,'Nikesh','1983-03-03',3000,700);
INSERT INTO emp(EMPNO,ENAME,HIREDATE,SALARY) VALUES (105,'Ravi','1985-07-05',3000);

/*2.Modifying the structure of tables */
-- 1. add new columns: sal number(7.2)
ALTER TABLE emp ADD sal int;

-- 2. dropping a column from a table:sal 
ALTER TABLE emp DROP COLUMN sal;

-- 3. modifying existing column:ename varchar2(15) 
ALTER TABLE emp MODIFY ename VARCHAR(15);

-- 4. renaming the tables: emp to emp1;
RENAME table emp to emp1;

-- 5. truncating the tables:emp1
TRUNCATE TABLE emp1;

-- 6 destroying tables:emp
DROP TABLE emp1;

/*3.Create a table stud with sname varchar2(20) primary key , rollno number(10) not null,dob date not null */
CREATE TABLE stud(sname varchar(20) PRIMARY KEY, rollno int NOT NULL, dob date NOT NULL);
SELECT * FROM stud;

/*4.Create a table student as regno number (6), mark number (3) check constraint (mark >=0 and mark <=100)); */
Create table student (regno int, mark int(3) constraint b check (mark >=0 and mark <=100));
SELECT * from STUDENT;

-- 1. In table student add check constraint(length(regno<=4))*/
Alter table student add regno check (length(regno<=4));

/*5.Create a table cust with(custid number(6) constraint  unique, name char(10)*/
CREATE TABLE cust(custid int(6) UNIQUE, name char(10));

/*6. Refer the table “stud” in table “ student”*/
