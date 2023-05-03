Download Link: https://assignmentchef.com/product/solved-cs3431-project-phase-3-complete-hospital-application
<br>
<span class="kksr-muted">Rate this product</span>

Description:

In this phase you will complete the design of the Hospital System by ensuring that the application requirements and constraints are all met.

Part 1 : Views

<ul>

 <li>Create a view named CriticalCases that selects the patients who have been admitted to Intensive Care Unit (ICU) at least 2 times. The view columns should be: Patient_SSN, firstName, lastName, numberOfAdmissionsToICU.o Hint: ICU is a service that is stored in table ‘RoomService’</li>

 <li>Create a view named DoctorsLoad that reports for each doctor whether this doctor has an overload or not. A doctor has an overload if they have more than 10 distinct admission cases; otherwise, the doctor has an underload. Notice that if a doctor examined a patient multiple times in the same admission, that still counts as one admission case. The view columns should be: DoctorID, graduatedFrom, load.o The load column should have either of these two values ‘Overloaded’, or ‘Underloaded’ according to the definition above.</li>

 <li>Use the views created above (you may need the original tables as well) to report the critical-case patients with number of admissions to ICU greater than 4.</li>

 <li>Use the views created above (you may need the original tables as well) to report the overloaded doctors that graduated from WPI. You should report the doctor ID, firstName, and lastName.</li>

</ul>

1

• Use the views created above (you may need the original tables as well) to report the comments inserted by underloaded doctors when examining critical-case patients. You should report the doctor Id, patient SSN, and the comment.

Part 2 : Triggers [5 Points each requirement)

Given the following requirements, create one or more triggers that ensure that these requirements are always satisfied. Think of the three events Insert, Update, and Delete because you may need triggers on one or more of these events to meet the requirements below.

Hint: You are allowed to combine several requirements into one trigger

<ul>

 <li>If a doctor visits a patient who has been in the ICU during their current admission, they must leave a comment. An example of this could be a patient whose admission involved a 1 day stay in a room designated as an Emergency Room, a 2 hour stay in an operating room, and a 1 day stay in a room designated as an ICU. If a doctor was to visit the patient during this admission then they must leave a comment.</li>

 <li>The insurance payment should be calculated automatically as 65% of the total payment. If the total payment changes, then the insurance amount should also change.o If in your DB you store the insurance payment as a percent, then it should be always set to 65%.</li>

 <li>Ensure that regular employees (with rank 0) must have their supervisors as division managers (with rank 1). Also, each regular employee must have a supervisor at all times.</li>

 <li>Similarly, division managers (with rank 1) must have their supervisors as general managers (with rank 2). Division managers must have supervisors at all times. General Managers must not have any supervisors.</li>

 <li>When a patient is admitted to an Emergency Room (a room with an Emergency service) on date D, the futureVisitDate should be automatically set to 2 months after that date, i.e., D + 2 months. The futureVisitDate may be manually changed later, but when the Emergency Room admission happens, the date should be set to default as mentioned above.</li>

 <li>When a new piece of equipment is purchased and it has not been inspected for over a month, check if there is an equipment technician who can service it. If there is, update the inspection date.</li>

 <li>When a patient leaves the hospital (admission leave time is set), print out the patient’s first and last name, address, all of the comments from doctors involved in that admission, and which doctor (name) left each comment.o Hint: You can print from a trigger using the function dbms_output.put_line(). Before it works you need to make sure to run the following line in SQLPlus</li>

</ul>

Sql&gt; set serveroutput on;

2

Hint: If you are faced with error “Table xxxx is mutating….”, then try to change either the trigger timing “Before→After” and/or the triggerlevel “Row→Statement levels”.

Part 3 : Access DB using JDBC [8 Points each requirement)

You are required to write a java program that accesses the database, performs some insertions and updates, executes some queries, and prints results on the screen.

Your program will be the interface to perform some simple functionality over the database. Your database should already contain data.

You are required to do the following:

Assume your program is called “Reporting.java”. The program will always take two parameters, e.g., username, and Password to connect to the DB. (Pass them as parameters such that the TAs can easily set them as needed without recompilation).

(0) When your program is executed without any additional arguments, e.g., &gt; java Reporting &lt;userName&gt; &lt;Password&gt;

Then the program should output the following options, and then terminate:

(1) When the program is executed with an argument 1 as follows: &gt; java Reporting &lt;userName&gt; &lt; Password &gt; 1

Then, we are now in the “Reporting Patients Basic Info.” mode. The program should print out the following line:

Enter Patient SSN: &lt;and wait for user’s input&gt;

When the user enters a SSN, the program should execute a query over the patient table and print on the screen the patient’s information as follows:

Then the program terminates.

1- Report Patients Basic Information 2- Report Doctors Basic Information 3- Report Admissions Information4- Update Admissions Payment

Patient SSN: …. Patient First Name: … Patient Last Name: … Patient Address: …

3

<table>

 <tbody>

  <tr>

   <td colspan="2" rowspan="1"></td>

   <td colspan="1" rowspan="4"></td>

  </tr>

  <tr>

   <td></td>

   <td></td>

  </tr>

  <tr>

   <td colspan="2" rowspan="1"></td>

  </tr>

  <tr>

   <td></td>

   <td></td>

  </tr>

  <tr>

   <td colspan="1" rowspan="3"></td>

   <td colspan="2" rowspan="1"></td>

  </tr>

  <tr>

   <td colspan="2" rowspan="1"></td>

  </tr>

  <tr>

   <td colspan="2" rowspan="1"></td>

  </tr>

  <tr>

   <td colspan="3" rowspan="1"></td>

  </tr>

  <tr>

   <td colspan="1" rowspan="4"></td>

   <td colspan="2" rowspan="1"></td>

  </tr>

  <tr>

   <td colspan="2" rowspan="1"></td>

  </tr>

  <tr>

   <td colspan="2" rowspan="1"></td>

  </tr>

  <tr>

   <td colspan="2" rowspan="1"></td>

  </tr>

 </tbody>

</table>

(2) When the program is executed with an argument 2 as follows: &gt; java Reporting &lt;userName&gt; &lt; Password &gt; 2

Then, we are now in the “Reporting Doctors Basic Info.” mode. The program should print out the following line:

Enter Doctor ID: &lt;and wait for user’s input&gt;

When the user enters an ID, the program should query the doctor table and print on the screen the following information, and then terminate:

Doctor ID: ….Doctor First Name: … Doctor Last Name: … Doctor Gender: …Doctor Graduated From: … Doctor Specialty: …

(3) When the program is executed with an argument 3 as follows: &gt; java Reporting &lt;userName&gt; &lt; Password &gt; 3

Then, we are now in the “Reporting Admissions Info.” mode. The program should print out the following line:

Enter Admission Number: &lt;and wait for user’s input&gt;

When the user enters a number, the program should query the admission table and print on the screen the following information, and then terminate:

Admission Number: ….

Patient SSN: …

Admission date (start date): …..

Total Payment: … Rooms:

RoomNum: … RoomNum:…

…

FromDate:…. ToDate:…..

FromDate:…. ToDate: ….

Doctors examined the patient in this admission:

Doctor ID: … Doctor ID: … ….

4

Notice that we need to print the room(s) that the patient has stayed in during this admission. Also make sure the printed doctor IDs are unique (no repetition).

(4) When the program is executed with an argument 4 as follows: &gt; java Reporting &lt;userName&gt; &lt; Password &gt; 4

Then, we are now in the “Updating Admission Payment” mode. The program should print out the following line:

Then your program should update the total payment value for the specified admission number in the database.

//Now if you execute option 3 again, you should get the new payment value.

Grading:

The maximum grade is 100 Points. No late submissions.

Deliverables:

Each team should deliver three files as follows:

<ol>

 <li>1)  Text file (.sql) that contains all SQL commands from Part1 and Part2 above. Also,ensure that the file includes the creation of all needed tables (copy it from the submission of Phase 2). The file must be executable from SQLplus on the CCC.wpi.edu server using command:SQL &gt; @&lt;fileName&gt;Sometimes code that runs in SQLDeveloper or LiveSQL does not work on the server. Please make sure your code works there, that is how we will grade your assignment.The file must run correctly, creating all tables and then the views and triggers. If the file’s syntax is not correct (and the file did not run), you will lose 20 points in addition to any other deductions.</li>

 <li>2)  A java file containing Part 3. Submit the code (.java) file. The TA will compile your file on the CCC.wpi.edu server. So, make sure your file compiles on these machines.</li>

 <li>3)  Any comments or assumptions that you have, you can write them to a separate .pdf file.Important: For each of the requirements in Part 2, include what trigger(s) you created to enforce this requirement. You need to state the event type (Before or After), the operation (Insert, Update, or Delete), and the granularity (For each row, or For each statement) and on which table. No code should be included here.</li>

</ol>

Enter Admission Number: &lt;and wait for user’s input&gt; Enter the new total payment: &lt;and wait for user’s input&gt;

4) Put the three files in a single zip file that will be submitted as described below.

Submission (Each team gives one submission):

<ul>

 <li>Submit electronically by the due date via canvas.wpi.edu website. Make sure your three files (the text file .sql, the java file .java, and your report .pdf) are zipped, and you upload one file.</li>

 <li>Each team submits one copy (from either of the team members).</li>

 <li>Make sure your names and group id are written inside your report.</li>

 <li>No hard copy submissions</li>

</ul>

5