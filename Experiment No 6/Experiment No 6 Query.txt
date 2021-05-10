/*EXPERIMENT NO.6 : SET OPERATIONS*/

/*1. List all the customers who are depositors but not borrowers.*/
SELECT CNAME FROM DEPOSIT  MINUS SELECT CNAME FROM BORROW;

/*2. List all the customers who are both depositors and borrowers*/
SELECT CNAME FROM DEPOSIT  UNION  (SELECT CNAME FROM BORROW);

/*3. List all the depositors having deposit in all the branches where Sunil is having Account*/
SELECT D1.CNAME FROM DEPOSIT D1 WHERE D1.BNAME IN (SELECT D2.BNAME FROM DEPOSIT D2 WHERE D2.CNAME = 'SUNIL' );

/*4. List all the customers living in city NAGPUR and having branch city BOMBAY or DELHI*/
SELECT C1.CNAME FROM CUSTOMER C1,DEPOSIT D1, BRANCH B1 WHERE C1.CITY = 'NAGPUR' AND C1.CNAME = D1.CNAME AND D1.BNAME = B1.BNAME AND B1.CITY IN ('BOMBAY','DELHI');

/*5. List all the depositors living in city NAGPUR*/
SELECT Distinct(CUSTOMER.CNAME) from CUSTOMER,DEPOSIT WHERE City='NAGPUR';

/*6. List all the depositors living in the city NAGPUR and having branch in city BOMBAY*/
SELECT C1.CNAME FROM CUSTOMER C1,DEPOSIT D1, BRANCH B1 WHERE C1.CITY = 'NAGPUR' AND C1.CNAME = D1.CNAME AND D1.BNAME = B1.BNAME AND B1.CITY IN ('BOMBAY');

/*7. List the branch cities of Anil and Sunil*/
SELECT B1.CITY FROM DEPOSIT D1, BRANCH B1 WHERE D1.BNAME = B1.BNAME AND D1.CNAME IN ('SUNIL' ,'ANIL');

/*11. List all the cities where branches of Anil and Sunil are locate*/
SELECT B1.CITY FROM BRANCH B1 WHERE B1.BNAME IN (SELECT D1.BNAME FROM DEPOSIT D1 WHERE D1.CNAME IN ('ANIL','SUNIL'));
















