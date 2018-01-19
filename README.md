# Hospital-Database-Management-System

This was my solution to a Database course's project in a CS Bachelor program I am pursuing. I chose to build a hospital database management system, implemented in MySql and Java. It ended to be much smaller than an actual hospital, but in the same time, much more than the intructor asked for.

The ERD is available at `a`, UML at `b`, the script I used to fill (generate data) the database tables automatically at `c`, the initial crediantels to login to the system at `d`, Database backup (with creation instructions) that can be imported to MySql at `e`.

--> Note:  You need to enter your MySql server's username and password in the DatabaseAPI class(es), at `HDBMS/src/DatabaseAPI/DatabaseHandler.java`, the same at `DataScript/src/DatabaseHandler.java`.

* Features summary (listed the ones that may not be so obvious): 

1. Core Database API implemented.
2. Soft-deletion implemented - Nothing get deleted from the database - history-friendly.
3. Follows programming's and OOP's best practices.
4. Multiple user types with different privileges implemented.
5. Exceptions handled carefully.
6. All TableViews (in the GUI) span AT LEAST 2 HDBMS tables.
7. Material design Login Window.
8. Uses external enhanced, modern-looking JavaFX libraries.
9. Achieves each user's type's best needs, easy to use, and functional.
10. Offers a "Status" bar at the bottom of nearly each GUI window, to inform the user of the result of their requested operations (queries).
11. Uses a special icon for each GUI.
12. For all input fields' groups, it checks if ALL of them are filled with correct-format data at first, such as:
	A. Patient/Employee's name: 3 characters long at least, all of them are letters
	B. Patient/Employee's ID: 7 characters long at least, all of them are numbers
	C. Patient/Employee's birthdate: can't be from the future
	D. Patient/Employee's phone number: 7 characters long at least, all of them are numbers
	E. Appointment's Date and Time can't be from the past
	F. Checks for patient's patID existence before adding the appointment (or prescription)
	G. Checks if a time slot is free before adding an appointment into it
	H. Checks if a prescription's cost is in a valid positive numeric format before adding it to the records
	I. Employee's username: 5 characters long at least, must have 1 letter out of them at minimum, only letters and numbers allowed
	J. Checks if a new employee's username already exists at first before adding it
	K. Checks if the password and re-password match
	L. Employee's salary: must have a valid positive numeric value
	M. Adds a new address only if it's unique, otherwise it gets the existing address's adrID

*Security-Oriented:
1. Prepared Statements used, to improve performance, and prevent SQL Injection attacks.
2. Passwords get SHA384-hashed before entering the database (I know it's not that of a secure move, but it's only to repsresent that it must be there, using a better hashing technique of course, in a real world DBMS).
3. Accepted passwords format: "Password must have at least 9 characters [ 1 lowercase letter, 1 uppercase letter, and 1 digit are a MUST ]".
