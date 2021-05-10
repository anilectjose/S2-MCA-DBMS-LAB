/*EXPERIMENT NO.5 : AGGREGATE FUNCTIONS*/

/*1.List total loan*/
SELECT SUM (AMOUNT) FROM BORROW;

/*2.List total deposit*/
SELECT SUM (AMOUNT) FROM DEPOSIT;

/*3.List total loan taken from KAROLBAGH branch*/
SELECT MAX(AMOUNT) FROM BORROW WHERE BNAME ='KAROLBAGH';

/* 4.List total deposit of customers having account date later than 1-Jan-96*/
SELECT SUM(AMOUNT) from deposit where adate>'1995-03-01';

/* 5.List total deposit of customers living in city NAGPUR*/
SELECT SUM(D1.AMOUNT) FROM DEPOSIT D1 , CUSTOMER C1 WHERE C1.CITY = 'NAGPUR' AND C1.CNAME = D1.CNAME;

/*6.List maximum deposit of customer living in Bombay*/
SELECT MAX(D1.AMOUNT) FROM DEPOSIT D1 , CUSTOMER C1 WHERE C1.CITY = 'Bombay' AND C1.CNAME = D1.CNAME;

/* 7.List total deposit of customer having branch in BOMBAY*/
SELECT SUM (AMOUNT) from deposit,BRANCH where city='BOMBAY';

/* 8.Count total number of branch cities*/
SELECT COUNT(DISTINCT (CITY)) FROM BRANCH ;

/*9.Count total number of customers cities*/
SELECT count(city) from CUSTOMER;

/* 10.Give branch names and branch wise deposit*/
SELECT BNAME , SUM(AMOUNT) FROM DEPOSIT GROUP BY BNAME;

/*11.Give city wise name and branch wise deposit*/
SELECT C1.CITY , SUM(D1.AMOUNT) FROM CUSTOMER C1 , DEPOSIT D1 WHERE D1.CNAME = C1.CNAME GROUP BY C1.CITY;

/*12.Give the branch wise loan of customer living in NAGPUR*/
SELECT BNAME , SUM(AMOUNT) FROM BORROW,CUSTOMER  WHERE city ='NAGPUR' GROUP BY BNAME;

/*13.Count total number of customers*/
SELECT count(cname) from CUSTOMER;

/*14.Count total number of depositors branch wise*/
SELECT BName, count (*)from DEPOSIT, CUSTOMER where deposit.CNAME = CUSTOMER.CNAME group by BNAME

/*15.Count total number of depositors branch wise*/
SELECT BName, count (*)from DEPOSIT, CUSTOMER where deposit.CNAME = CUSTOMER.CNAME group by BNAME

/*16.Give maximum loan from branch VRCE*/
SELECT MAX(AMOUNT) FROM BORROW WHERE BNAME ='VRCE';

/*17.Give  the number of customers who are depositors as well as borrowers*/
SELECT COUNT(DISTINCT (CNAME)) FROM CUSTOMER WHERE CNAME IN ((SELECT CNAME FROM DEPOSIT) INTERSECT (SELECT CNAME FROM  BORROW));




