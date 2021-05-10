/*EXPERIMENT NO.7 : JOIN OR CARTESIAN PRODUCT*/

/*1.Give name of customers having living city BOMBAY and branch city NAGPUR*/
SELECT D1.CNAME,D1.BNAME,C1.CNAME,C1.CITY,B1.CITY,B1.BNAME FROM DEPOSIT D1,CUSTOMER C1,BRANCH B1 WHERE C1.CITY = 'BOMBAY' AND B1.CITY = 'NAGPUR' AND D1.CNAME = C1.CNAME AND D1.BNAME = B1.BNAME;

/*2.Give names of customers having the same living city as their branch city*/
SELECT distinct(customer.CNAME), BRANCH.CITY FROM BRANCH, customer WHERE BRANCH.city = customer.city;

/*3.Give names of customers who are borrowers as well as depositors and having city NAGPUR.*/
SELECT C1.CNAME FROM CUSTOMER C1,DEPOSIT D1,BORROW B1 WHERE C1.CITY='NAGPUR'  AND C1.CNAME=D1.CNAME  AND D1.CNAME = B1.CNAME;

/*4.Give names of borrowers having deposit amount greater than 1000 and loan amount greater than 2000.*/
SELECT BR1.CNAME, BR1.AMOUNT, D1.CNAME, D1.AMOUNT  FROM BORROW BR1,DEPOSIT D1 WHERE D1.CNAME = BR1.CNAME AND D1.AMOUNT > 1000 AND BR1.AMOUNT > 2000;

/*5.Give names of depositors having the same branch as the branch of Sunil*/
SELECT D1.CNAME FROM  DEPOSIT D1 WHERE D1.BNAME IN (SELECT  D2.BNAME FROM DEPOSIT D2 WHERE D2.CNAME = 'SUNIL');

/*6.Give names of borrowers having loan amount greater than the loan amount of Pramod*/
SELECT BR1.CNAME,BR1.AMOUNT FROM BORROW BR1 WHERE BR1.AMOUNT > ALL (SELECT BR2.AMOUNT FROM BORROW BR2 WHERE BR2.CNAME = 'PRAMOD');

/*7.Give the name of the customer living in the city where branch of depositor Sunil is located.*/
SELECT C.CNAME FROM CUSTOMER C WHERE C.CITY IN (SELECT B.CITY FROM BRANCH B WHERE B.BNAME IN (SELECT D.BNAME FROM DEPOSIT D WHERE D.CNAME='SUNIL'));

/*8.Give branch city and living city of Pramod*/
SELECT B1.CITY , C1.CITY FROM BRANCH B1,CUSTOMER C1, DEPOSIT D1 WHERE C1.CNAME = 'PRAMOD' AND C1.CNAME = D1.CNAME AND D1.BNAME = B1.BNAME;

/*9.Give branch city of Sunil and branch city of Anil*/
SELECT B1.CITY FROM DEPOSIT D1, BRANCH B1 WHERE D1.BNAME = B1.BNAME AND D1.CNAME IN ('SUNIL' ,'ANIL');

/*10.Give the living city of Anil and the living city of Sunil*/
SELECT C1.CNAME, C1.CITY FROM CUSTOMER C1 WHERE C1.CNAME = 'ANIL' OR C1.CNAME = 'SUNIL';




























