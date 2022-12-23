HW2: 6 points
For this hw, you will add (your own) data to tables you'd create, based on your database design from HW1, then write SQL queries to run on those tables :)
You'll be using 'Oracle Live SQL' to do your work, and submit links to - so you don't need to install anything, or directly submit any code on D2L! You'll simply be submitting links...[eg: https://livesql.oracle.com/apex/livesql/s/c1v3mbw9y8jnivrr0fb85cjxq]
Here are a couple of pages to get you started on Live SQL: https://www.thatjeffsmith.com/archive/2016/03/a-place-to-learn-oracle-no-setup-required/ and https://csveda.com/structured-query-language/sql-using-oracle-live-sql/
-----------------------------------------
Q1 (2 points). Given a time range (eg. Jan 1 to Jan 31, 2021), in that interval, what is the average amount a procedure cost, and how long did it take on the average?

Ans) https://livesql.oracle.com/apex/livesql/s/lf6bc5h1kjblll5m25dkdwp46

As per HW1, the patient's medical record consists of procedures performed on him/her. So, there is a 'Patient' table having details like ID, Name and State(Which as per HW1 should be any of the following : contacted, scheduled, recently visited, up for next visit, dormant.
The Medical_Record table consists of patient and procedure details. Patient_ID is the foreign key which references PID from Patient table. Details like name of procedure, its cost, date performed on and the duration. The unit of duration here is minutes and for cost it is $.

To calculate the average amount the procedure cost and average time taken, I used AVG function on Procedure_Amount and Procedure_Duration columns. The date range can be specified with the Procedure_Date attribute.

-----------------------------------------
Q2 (2 points). Given a date, what is the income for that date, from all the procedures performed that day? The owners could run this daily, to chart income, cumulative income, etc.

Ans) https://livesql.oracle.com/apex/livesql/s/lf6e0hq2q50rhmcrbeohbhsco

For this, I have used the same 2 tables as used in Q1. The query differs which is to calculate the income for that date for all the procedures performed that day. For this I used SUM function on the Procedure_Amount column and specifying a date with Procedure_Date attribute.
-----------------------------------------
Q3 (1 point). The owners have asked you to create a new table, after you'd built the original db - this is a simple 'capabilities' table, with just two columns: EMPLOYEE ID, SKILL. With this table, they hope to have, in a single place, what each employee (staff, surgeons... everyone) can do, eg. throw a party, file taxes, administer injections, extract teeth, talk to the press... [each employee would pick from a giant list of tasks, one or more of the items - this is to prevent variations and typos].
Write a query that will pick out only the employees who can do every task in a table such as the one below:
File taxes
Meet the press
Organize spring cleaning
Do teeth cleaning
Reorder inventory
Why do this? The owners want to plan a 'light week' that is staffed with a limited number of employees who can do all the above, and rotate tasks - while giving the rest of the staff, paid time off (the ones who come to work get 1.5x pay for that week - cool!).

Ans) https://livesql.oracle.com/apex/livesql/s/lgip7b1bdbkzmyiwtagabptot

For this question, I understood that SQL Division Operation is the way for the solution. I created 2 tables. One is capabilities table (Employee_ID, Skill) and the other one is Task_query table which has the required tasks that can be done by the employees fetched by our query. I am ending up with ORA-00933 error (SQL command not properly ended). Not sure where I am going wrong.

I even used LISTAGG function to club the multiple skills of the employee into one single row.
But unable to find a way to compare th output obtained with the task query table.
-----------------------------------------
Q4 (1 point).
Come up with a(nother) reasonable query that the owners would want to make, using all the data in their db, and write SQL for it. Explain in your submission README, what the query is, in plain English, and also how your SQL code works (ie what it does to carry out the query). You can even include (create, and fill) new tables that were not asked for in HW1. Be creative, have fun with this 'roll your own' question!

Ans) https://livesql.oracle.com/apex/livesql/s/lgh965h8c32wbwlloafb8e10v

The scenario here is to get a view of a day's schedule. The owners would want to view it everyday morning (As specified in HW1). For this I used the Patient Table as earlier.A table Doctor has been created which will have details of doctor. A third table ROOM_SCHEDULE will map a patient and a doctor to one of the 8 rooms present once their appointment is fixed.
The final query from the ROOM_SCHEDULE table gives the details of the patient (ID, Name) and the details of doctor he/she is consulting (Staff ID, Doctor Name) along with the appointment date and the room number for the consultation.
The owners can query with a specific date to see the day's schedule every morning since appointments could be fixed beforehand.
-----------------------------------------
Submission checklist:
• your four livesql.oracle.com/<> links (which you'd save as 'unlisted' so that it's not publicly available) - one each for Q1, Q2, Q3, Q4, placed in a README.txt
• assumptions etc. clearly stated in the README
You can post questions (and answer others' :)) on Piazza, under 'hw2'.
Enjoy SQL coding!
-----------------------------------------
