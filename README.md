# Hazrat Ali

# Software Enginering 

# Database Management Command : 

#                     ORACLE

# 1. alter session set " _Oracle_Script" = true;

# 2. session altered;

# 3. create username || UserName identified by pass ; ( Both Same)

# 4. create table lesson (id number);

# 5. desc lesson;

# 6. alter table lesson add ( Name Varchar (10), email Varchar (20));

# 7. desc lesson; ( For See him)

# 8. insert into lesson values ( 1, 'Hazrat','CSE','hazrat@gmail.com');

# insert into lesson values ( 2, 'Rahim','CSE','rahim@gmail.com');


# 9. select * from lesson; 

# 10. select * from lesson where id =1;

# 11. select email from lesson; (see him email).

# 12. update lesson set email = 'alihazrat.com', where id =1 ; ( Mail Changed ).

# select *from lesson;

# 13. update lesson set name = 'ali', where id = 1,2. etc ; 

# 14. delete from lesson where id = 2;

# Select *from lesson;

# Single Condition.  

# 15. select id,name from lesson id>1 and <10; 

# ORDER By.

# 16. select *from lesson ORDER By id ASCi,

# 17. select *from lesson ORDER By id DESC;

# Multiple Condition. 

# 18.  select *from lesson ORDER By id DESC, name ASC;

# 19.  select *from lesson ORDER By name DESC, id ASC;

# 20. SET SERVEROUTPUT ON;

# 21. BEGIN

# 22. DBMS_OUTPUT.PUT_LINE('HAZRAT ALI');

# 23. END;

# 24. /

# 25.  
    CREATE TABLE employees (
    2      EMPNO     NUMBER(4) PRIMARY KEY,
    3      ENAME     VARCHAR2(10),
    4      JOB       VARCHAR2(10),
    5      MGR       NUMBER(4),
    6      HIREDATE  DATE,
    7      SAL       NUMBER(7, 2),
    8      DEPTNO    NUMBER(2)
    9  );

# 26. 
    INSERT INTO employees(EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, DEPTNO)2  VALUES (7369, 'SMITH', 'CLERK', 7902, TO_DATE('17-DEC-80', 'DD-MON-YY'), 800, 20);

    INSERT INTO employees (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, DEPTNO) 2  VALUES (7499, 'ALLEN', 'SALESMAN', 7698, TO_DATE('20-FEB-81', 'DD-MON-YY'), 1600, 30);

    INSERT INTO employees (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, DEPTNO) 2  VALUES (7521, 'WARD', 'SALESMAN', 7698, TO_DATE('22-FEB-81', 'DD-MON-YY'), 1250, 30);

    INSERT INTO employees (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, DEPTNO) 2  VALUES (7698, 'BLAKE', 'MANAGER', NULL, TO_DATE('01-MAY-81', 'DD-MON-YY'), 3850, 30);

    INSERT INTO employees (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, DEPTNO) 2  VALUES (7902, 'FORD', 'ANALYST', 7566, TO_DATE('03-DEC-81', 'DD-MON-YY'), 3000, 10);

# 27. SELECT * FROM employees;
  
    EMPNO ENAME      JOB               MGR HIREDATE         SAL     DEPTNO
---------- ---------- ---------- ---------- --------- ---------- ----------
      7369 SMITH      CLERK            7902 17-DEC-80        800         20
      7499 ALLEN      SALESMAN         7698 20-FEB-81       1600         30
      7521 WARD       SALESMAN         7698 22-FEB-81       1250         30
      7698 BLAKE      MANAGER               01-MAY-81       3850         30
      7902 FORD       ANALYST          7566 03-DEC-81       3000         10

# 28. 
    DECLARE

    29. EMP_NO VARCHAR(100);

    30. EMP_SAL EMPLOYEES.SAL%TYPE:=20000;

    31. IF EMP_SAL>20000 THEN

    32. DBMS_OUTPUT.PUT_line('he is Rich);

    33. else
 
    34. DBMS_OUTPUT.PUT_line('he is poor);

    35. END IF;

    36. END;

    37. /

# 38.
    DECLARE
    2  EMP_NO VARCHAR2(100);
    3  EMP_SAL EMPLOYEES.SAL%TYPE:=20000;
    4  BEGIN
    5  IF EMP_SAL>20000 THEN
    6  DBMS_OUTPUT.PUT_line('he is Rich');
    7  ELSE
    8  DBMS_OUTPUT.PUT_line('he is POOR');
    9  END IF;
    10  END;
    11  /

 # 39.
    DECLARE
    2  CURSOR EMP_CURSOR IS
    3  SELECT EMPNO FROM EMPLOYEES
    4  WHERE SAL>1250;
    5  BEGIN
    6  FOR EMP IN EMP_CURSOR LOOP
    7  DBMS_OUTPUT.PUT_LINE('EMPLOYEE ID: ' || EMP.EMPNO);
    8  END LOOP;
    9  END;
    10  /

 # 40.  
    DECLARE
    2  COUNTER NUMBER:=1;
    3  BEGIN
    4  WHILE COUNTER<=5 LOOP
    5  DBMS_OUTPUT.PUT_LINE('NUMBER:'||COUNTER);
    6  COUNTER:=COUNTER+1;
    7  END LOOP;
    8  END;
    9  /


 # 41. 
    select * from employees

       EMPNO ENAME      JOB               MGR HIREDATE         SAL     DEPTNO
---------- ---------- ---------- ---------- --------- ---------- ----------
      7369 SMITH      CLERK            7902 17-DEC-80        800         20
      7499 ALLEN      SALESMAN         7698 20-FEB-81       1600         30
      7521 WARD       SALESMAN         7698 22-FEB-81       1250         30
      7698 BLAKE      MANAGER               01-MAY-81       3850         30
      7902 FORD       ANALYST          7566 03-DEC-81       3000         10
# 42 

    SET SERVEROUTPUT ON;


# 43 
     DECLARE
     V_EMP_ID EMPLOYEES.EMPNO%TYPE:=7499;
     V_EMP_NAME EMPLOYEES.ENAME%TYPE;
     V_SALARY EMPLOYEES.SAL%TYPE;
     BEGIN
     SELECT ENAME, SAL
     INTO V_EMP_NAME,V_SALARY
     FROM EMPLOYEES
     WHERE EMPNO=V_EMP_ID;
     DBMS_OUTPUT.PUT_LINE('EMP NAME:' || V_EMP_NAME || 'SALARY:'|| V_SALARY);
     END;
     /

# 43 

     create user: 
     create user c##HR_USER identified by root; 
     grant all privileges c##HR_USER; 

# 44   

    DEPARTMENT TABLE 
    creating department table: 
    create table department( 
    department_id number(2) primary key, 
    department_name varchar2(20)); 

# 45     
    
    insert into department table: 
    insert all  
    into department values (1,'Sales') 
    into department values (2,'Maerketing') 
    into department values (3,'Engineering') 
    select 1 from dual; 


    EMPLOYEE TABLE 
    creating employee table: 
    create table employee( 
    emp_id number(3) primary key, 
    first_name varchar2(20), 
    last_name varchar2(20), 
    hire_date date, 
    salary number(6), 
    department_id number(2), 
    constraint FK_Employee_department_id 
    foreign key(department_id) references department(department_id)); 

# 46 
     
     insert into employee 
     insert all 
     into employee values(101,'John','Doe', TO_DATE('2020-01-15', 'YYYY-MM-DD'), 5000, 1) 
     into employee values(102,'Jane','Smith', TO_DATE('2019-05-22', 'YYYY-MM-DD'), 6000, 1) 
     into employee values(103,'Michael','Johnson', TO_DATE('2018-07-30', 'YYYY-MM-DD'), 
     5500, 2) 
    into employee values(104,'Emily','Davis', TO_DATE('2021-09-10', 'YYYY-MM-DD'), 6500, 2) 
    into employee values(105,'Sarah','Wilson', TO_DATE('2017-03-12', 'YYYY-MM-DD'), 7000, 
    3) 
    select 1 from dual; 


# 47 

      JOB TABLE 
    Creating job table 
    create table job ( 
    job_id number(2),  
    job_title varchar2(20), 
    constraint PK_Job_Job_id primary key (job_id)); 
    insert into job table: 
    insert all 
    into job values (1,'Manager') 
    into job values (2,'Sales Representative') 
    into job values (3,'Marketing Specialist') 
    into job values (4,'Software Engineer') 
    select 1 from dual; 

# 48  ================= SET 01 =================== 
     
1) Retrieve the list of employees who were hired between January 1, 2019, and December 
     31, 2020, and have a salary greater than 5500.

    Ans: 
    select * from employee where hire_date between TO_DATE('January 1, 
    2019','MONTH DD, YYYY') and TO_DATE('December 31, 2020','MONTH DD, YYYY') 
    and salary > 5500;

# 49 

    2) Display the average salary for each department, but only for those departments where the 
     average salary is greater than 6000.   
    Ans: 
     select avg(salary) from employee group by department_id having 
     avg(salary)>6000; 
     
# 50 
    3) List employees along with their department names and job titles, ordered by salary in 
       descending order, showing only those earning more than 6000. 
    Ans: 
    select * from employee e,department d where salary>6000 and 
    e.department_id=d.department_id order by salary desc; 
    


