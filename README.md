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

# 51 

    ================== SET 02 ================== 
    1) Find the department with the highest total salary expense and display the total salary of 
      that department. 
     Ans: 
     select d.department_name, emp.total_sal from (select department_id, 
    sum(salary) total_sal from employee group by department_id order by 
    total_sal desc fetch first 1 row only) emp, department d where 
    d.department_id=emp.department_id;


# 52     
    
    2) Display the average salary for each department, but only for those departments with more 
    than 2 employees. 
    Ans: 
    select d.department_id,d.department_name,emp.avg_sal from( 
    select department_id,avg(salary) avg_sal from employee group by 
    department_id having count(department_id)>2) emp, department d where 
    d.department_id=emp.department_id;


# 53 
    3) List employees along with their department names and job titles, ordered by salary in 
     descending order, showing only those earning more than 6000. 
    Ans: 
    select * from employee e, department d where 
    e.department_id=d.department_id and e.salary>6000 order by e.salary desc; 

# 54 

     1. Table Needed: 

    Table: Employees 
    CREATE TABLE Employees ( 
    Emp_ID INT PRIMARY KEY, 
    Name VARCHAR2(100), 
    Dept_ID INT, 
    Salary NUMBER, 
    Hire_Date DATE 
    ); 
    INSERT INTO Employees (Emp_ID, Name, Dept_ID, Salary, Hire_Date)  
    VALUES (101, 'John Doe', 101, 50000, TO_DATE('2023-01-01', 'YYYY-MM-DD')); 
    INSERT INTO Employees (Emp_ID, Name, Dept_ID, Salary, Hire_Date)  
    VALUES (102, 'Jane Smith', 102, 60000, TO_DATE('2023-02-01', 'YYYY-MM-DD')); 
    INSERT INTO Employees (Emp_ID, Name, Dept_ID, Salary, Hire_Date)  
    VALUES (103, 'Bob Brown', 103, 55000, TO_DATE('2023-03-01', 'YYYY-MM-DD'));

# 55

     Table: Departments 
    CREATE TABLE Departments ( 
    Dept_ID INT PRIMARY KEY, 
    Dept_Name VARCHAR2(100) 
    ); 
    INSERT INTO Departments (Dept_ID, Dept_Name)  
    VALUES (101, 'HR'); 
    INSERT INTO Departments (Dept_ID, Dept_Name)  
    VALUES (102, 'IT'); 
    INSERT INTO Departments (Dept_ID, Dept_Name)  
    VALUES (103, 'Finance');


# 56 

    Table: Projects 
    CREATE TABLE Projects ( 
    Project_ID INT PRIMARY KEY, 
    Project_Name VARCHAR2(100) 
    ); 
    INSERT INTO Projects (Project_ID, Project_Name)  
    VALUES (201, 'Project A'); 
    INSERT INTO Projects (Project_ID, Project_Name)  
    VALUES (202, 'Project B'); 
    INSERT INTO Projects (Project_ID, Project_Name)  
    VALUES (203, 'Project C');

# 57  

     Table: Orders 
     CREATE TABLE Orders ( 
     Order_ID INT PRIMARY KEY, 
     Customer_ID INT, 
     Order_Date DATE, 
     Order_Amount NUMBER, 
    Order_Status VARCHAR2(50), 
    FOREIGN KEY (Customer_ID) REFERENCES Customers(Customer_ID) 
     ); 
    INSERT INTO Orders (Order_ID, Customer_ID, Order_Date, Order_Amount, Order_Status)  
    VALUES (301, 101, TO_DATE('2025-02-01', 'YYYY-MM-DD'), 500, 'Shipped'); 
    INSERT INTO Orders (Order_ID, Customer_ID, Order_Date, Order_Amount, Order_Status)  
    VALUES (302, 102, TO_DATE('2025-02-02', 'YYYY-MM-DD'), 1000, 'Pending'); 
    INSERT INTO Orders (Order_ID, Customer_ID, Order_Date, Order_Amount, Order_Status)  
    VALUES (303, 103, TO_DATE('2025-02-03', 'YYYY-MM-DD'), 200, 'Delivered');

# 58 

    Table: Customers 
    CREATE TABLE Customers ( 
    Customer_ID INT PRIMARY KEY, 
    Name VARCHAR2(100), 
    Email VARCHAR2(100), 
    Phone VARCHAR2(15) 
    ); 
    INSERT INTO Customers (Customer_ID, Name, Email, Phone)  
    VALUES (101, 'John Doe', 'john.doe@email.com', '123-456-7890'); 
    INSERT INTO Customers (Customer_ID, Name, Email, Phone)  
    VALUES (102, 'Jane Smith', 'jane.smith@email.com', '987-654-3210'); 
    INSERT INTO Customers (Customer_ID, Name, Email, Phone)  
    VALUES (103, 'Bob Brown', 'bob.brown@email.com', '555-666-7777');

# 59 

     Table: TeamMembers 
     CREATE TABLE TeamMembers ( 
     Emp_ID INT, 
     Project_ID INT, 
     Role VARCHAR2(50), 
     PRIMARY KEY (Emp_ID, Project_ID), 
     FOREIGN KEY (Emp_ID) REFERENCES Employees(Emp_ID), 
     FOREIGN KEY (Project_ID) REFERENCES Projects(Project_ID) 
    ); 
     INSERT INTO TeamMembers (Emp_ID, Project_ID, Role)  
     VALUES (101, 201, 'Manager'); 
     INSERT INTO TeamMembers (Emp_ID, Project_ID, Role)  
     VALUES (102, 202, 'Developer'); 
     INSERT INTO TeamMembers (Emp_ID, Project_ID, Role)  
     VALUES (103, 203, 'Analyst');


# 60 

     SET SERVEROUTPUT ON; 
     DECLARE 
     message VARCHAR2(100); 
     BEGIN 
     message := 'Hello, welcome to Oracle PL/SQL!'; 
     DBMS_OUTPUT.PUT_LINE(message); 
     END; 
     /

# 61    
   
    SET SERVEROUTPUT ON; 
    DECLARE 
    emp_id NUMBER := 101; 
    emp_name VARCHAR2(50); 
    BEGIN 
    SELECT Name INTO emp_name 
    FROM Employees 
    WHERE Emp_ID = emp_id; 
    DBMS_OUTPUT.PUT_LINE('Employee Name: ' || emp_name); 
    EXCEPTION 
    WHEN NO_DATA_FOUND THEN 
    DBMS_OUTPUT.PUT_LINE('Employee not found.'); 
    END; 
    / 

# 62 

    SET SERVEROUTPUT ON; 
    DECLARE 
    user_input VARCHAR2(100); 
    BEGIN -- Input taken as an assignment (SQL*Plus doesn't  support direct user input in a PL/SQL block) 
    user_input := 'This is a test message'; 
    DBMS_OUTPUT.PUT_LINE('User Input: ' || user_input); 
    END; 
    / 

# 64
    # SET SERVEROUTPUT ON; 
    DECLARE 
    original_salary NUMBER := 50000; 
    bonus_percentage NUMBER := 10; 
    final_salary NUMBER; 
    BEGIN 
    final_salary := original_salary + (original_salary * bonus_percentage / 100); 
     DBMS_OUTPUT.PUT_LINE('Final Salary After Bonus: ' || final_salary); 
     END; 
    /     


# 65     
    
    SET SERVEROUTPUT ON; 
    DECLARE 
    CURSOR emp_cursor IS 
    SELECT Name FROM Employees WHERE Dept_ID = 101; 
    emp_name Employees.Name%TYPE; 
    BEGIN 
    OPEN emp_cursor; 
    LOOP 
    FETCH emp_cursor INTO emp_name; 
    EXIT WHEN emp_cursor%NOTFOUND; 
    DBMS_OUTPUT.PUT_LINE('Employee Name: ' || emp_name); 
    END LOOP; 
    CLOSE emp_cursor; 
    END; 
    / 

# 66 

      SET SERVEROUTPUT ON; 
      DECLARE 
      CURSOR salary_cursor IS 
      SELECT Emp_ID, Salary FROM Employees WHERE Dept_ID = 101; 
      emp_id Employees.Emp_ID%TYPE; 
      emp_salary Employees.Salary%TYPE; 
      BEGIN 
      FOR emp_record IN salary_cursor LOOP 
      UPDATE Employees 
    SET Salary = emp_record.Salary * 1.10 -- 10% increase 
    WHERE Emp_ID = emp_record.Emp_ID; 
    DBMS_OUTPUT.PUT_LINE('Updated Salary for Emp_ID: ' || emp_record.Emp_ID); 
    END LOOP; 
    END; 
     / 


# 67 

      SET SERVEROUTPUT ON; 
      DECLARE 
      CURSOR project_cursor IS 
      SELECT e.Name, p.Project_Name 
      FROM Employees e 
      JOIN TeamMembers tm ON e.Emp_ID = tm.Emp_ID 
      JOIN Projects p ON tm.Project_ID = p.Project_ID; 
      emp_name Employees.Name%TYPE; 
      project_name Projects.Project_Name%TYPE; 
      BEGIN 
      OPEN project_cursor; 
      LOOP 
      FETCH project_cursor INTO emp_name, project_name; 
      EXIT WHEN project_cursor%NOTFOUND; 
       DBMS_OUTPUT.PUT_LINE(emp_name || ' is assigned to project: ' || project_name); 
      END LOOP; 
      CLOSE project_cursor; 
    END; 
    / 
    
# 68 


     SET SERVEROUTPUT ON; 
     CREATE OR REPLACE PROCEDURE FetchEmployeeDetails(emp_id_in IN NUMBER) IS 
     CURSOR emp_cursor IS 
     SELECT Emp_ID, Name, Dept_ID FROM Employees WHERE Emp_ID = emp_id_in; 
    emp_id Employees.Emp_ID%TYPE; 
     emp_name Employees.Name%TYPE; 
    dept_id Employees.Dept_ID%TYPE; 
    BEGIN 
    OPEN emp_cursor; 
    FETCH emp_cursor INTO emp_id, emp_name, dept_id; 
    IF emp_cursor%FOUND THEN 
    DBMS_OUTPUT.PUT_LINE('Emp_ID: ' || emp_id || ', Name: ' || emp_name || ', Dept_ID: ' || dept_id); 
    ELSE 
    DBMS_OUTPUT.PUT_LINE('Employee not found!'); 
    END IF; 
    CLOSE emp_cursor; 
    END; 
    /


# 69 

      SET SERVEROUTPUT ON; 
      DECLARE 
      num1 NUMBER := 10; 
      num2 NUMBER := 0; 
      result NUMBER; 
      BEGIN 
      result := num1 / num2; 
      DBMS_OUTPUT.PUT_LINE('Result: ' || result);  
      EXCEPTION 
      WHEN ZERO_DIVIDE THEN 
      DBMS_OUTPUT.PUT_LINE('Error: Cannot divide by zero!'); 
      END; 
      / 

# 70

    SET SERVEROUTPUT ON; 
    DECLARE 
    emp_id NUMBER := 999; -- Assume this ID doesn't exist 
    emp_name VARCHAR2(50); 
    BEGIN 
    SELECT Name INTO emp_name FROM Employees WHERE Emp_ID = emp_id; 
    DBMS_OUTPUT.PUT_LINE('Employee Name: ' || emp_name); 
    EXCEPTION 
    WHEN NO_DATA_FOUND THEN 
    DBMS_OUTPUT.PUT_LINE('Employee not found with ID: ' || emp_id); 
    WHEN OTHERS THEN 
    DBMS_OUTPUT.PUT_LINE('An unknown error occurred!'); 
    END; 
    / 



#  71 

     SET SERVEROUTPUT ON;  
     DECLARE 
     emp_id NUMBER := 101; -- Duplicate Emp_ID 
     BEGIN -- Trying to insert a duplicate primary key 
     INSERT INTO Employees (Emp_ID, Name, Dept_ID, Salary) 
     VALUES (emp_id, 'John Doe', 101, 50000); 
    COMMIT; 
    EXCEPTION 
    WHEN DUP_VAL_ON_INDEX THEN 
    DBMS_OUTPUT.PUT_LINE('Error: Duplicate employee ID ' || emp_id); 
    WHEN OTHERS THEN 
    DBMS_OUTPUT.PUT_LINE('An unknown error occurred!'); 
    END; 
    /

# 72 

      SET SERVEROUTPUT ON; 
      DECLARE 
      emp_id NUMBER := 101; -- Duplicate Emp_ID 
      BEGIN -- Trying to insert a duplicate primary key 
      INSERT INTO Employees (Emp_ID, Name, Dept_ID, Salary) 
      VALUES (emp_id, 'John Doe', 101, 50000); 
     COMMIT; 
     EXCEPTION 
     WHEN DUP_VAL_ON_INDEX THEN 
     DBMS_OUTPUT.PUT_LINE('Error: Duplicate employee ID ' || emp_id); 
     WHEN OTHERS THEN 
     DBMS_OUTPUT.PUT_LINE('An unknown error occurred!'); 
     END; 
     /

# 73 

     
        SET SERVEROUTPUT ON; 
        CREATE OR REPLACE FUNCTION CalculateBonus(emp_id IN NUMBER) RETURN NUMBER IS 
        emp_salary Employees.Salary%TYPE; 
        bonus NUMBER; 
        BEGIN 
        SELECT Salary INTO emp_salary FROM Employees WHERE Emp_ID = emp_id; 
        bonus := emp_salary * 0.10; -- 10% bonus 
        RETURN bonus; 
        END; 
        / -- To test the function 
        DECLARE 
        emp_bonus NUMBER; 
        BEGIN 
        emp_bonus := CalculateBonus(101); 
         DBMS_OUTPUT.PUT_LINE('Bonus for Emp_ID 101: ' || emp_bonus); 
        END; 
        /

# 74   

     SET SERVEROUTPUT ON; 
     CREATE OR REPLACE FUNCTION CalculateBonus(emp_id IN NUMBER) RETURN NUMBER IS 
    emp_salary Employees.Salary%TYPE; 
    bonus NUMBER; 
    BEGIN 
    SELECT Salary INTO emp_salary FROM Employees WHERE Emp_ID = emp_id; 
    bonus := emp_salary * 0.10; -- 10% bonus 
    RETURN bonus; 
    END; 
    / -- To test the function 
    DECLARE 
    emp_bonus NUMBER; 
    BEGIN 
    emp_bonus := CalculateBonus(101); 
     DBMS_OUTPUT.PUT_LINE('Bonus for Emp_ID 101: ' || emp_bonus); 
    END; 
    /     

# 75 

     SET SERVEROUTPUT ON; 
     CREATE OR REPLACE FUNCTION CalculateBonus(emp_id IN NUMBER) RETURN NUMBER IS 
     emp_salary Employees.Salary%TYPE; 
     bonus NUMBER; 
     BEGIN 
     SELECT Salary INTO emp_salary FROM Employees WHERE Emp_ID = emp_id; 
     bonus := emp_salary * 0.10; -- 10% bonus 
     RETURN bonus; 
     END; 
     /


     -- To test the function 
     DECLARE 
     emp_bonus NUMBER; 
     BEGIN 
     emp_bonus := CalculateBonus(101); 
     DBMS_OUTPUT.PUT_LINE('Bonus for Emp_ID 101: ' || emp_bonus); 
     END; 
     /


# 76 

     SET SERVEROUTPUT ON; 
    CREATE OR REPLACE PROCEDURE UpdateSalary(emp_id IN NUMBER, salary_increase IN NUMBER) IS 
    emp_salary Employees.Salary%TYPE; 
    BEGIN 
    SELECT Salary INTO emp_salary FROM Employees WHERE Emp_ID = emp_id; 
    UPDATE Employees 
    SET Salary = emp_salary + (emp_salary * salary_increase / 100) 
    WHERE Emp_ID = emp_id; 
    DBMS_OUTPUT.PUT_LINE('Salary updated for Emp_ID: ' || emp_id); 
    END; 
    / -- To test the procedure 
    EXEC UpdateSalary(101, 10); -- 10% increase


# 77 
    SET SERVEROUTPUT ON; 
     CREATE OR REPLACE PROCEDURE DeleteEmployee(emp_id IN NUMBER) IS 
     BEGIN 
     DELETE FROM Employees WHERE Emp_ID = emp_id; 
     COMMIT; 
     DBMS_OUTPUT.PUT_LINE('Employee with Emp_ID ' || emp_id || ' has been deleted.'); 
     EXCEPTION 
     WHEN OTHERS THEN 
     DBMS_OUTPUT.PUT_LINE('Error occurred: ' || SQLERRM); 
     ROLLBACK; 
    END; 
    / 
     -- To test the procedure 
     EXEC DeleteEmployee(101); -- Deletes the employee with Emp_ID 101
   










  









     


