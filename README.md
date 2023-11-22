# Applying filters to SQL queries


-------

# Description <a name="description">

A fictional company is attempting to strengthen the security of its system. It is my responsibility to make sure the system is secure, look into any possible security flaws, and update staff computers as necessary. I've included examples of how to use SQL with filters for security-related tasks in the following steps. This assessment was completed as a component of my cybersecurity portfolio and as part of the <a href='https://www.coursera.org/google-certificates/cybersecurity-certificate'>Google Cybersecurity Professional Certificate</a> on Coursera, specifically in the  <a href='https://www.coursera.org/learn/linux-and-sql'> "Tools of the Trade: Linux and SQL" </a> Course.


# Retrieve after hours failed login attempts  <a name="scenario">
A possible security incident happened after business hours, specifically after 18:00. Every unsuccessful attempt to log in after hours needs to be looked into. I created a SQL query to filter for unsuccessful login attempts that happened after business hours, as you can see by looking at the code below.

<p align="center">
Code: <br/>
<img src="https://i.imgur.com/uABvcJI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

My query appears in the first section of the screenshot, and some of the output appears in the second. This search looks for unsuccessful attempts at login that took place after 18:00. I began by pulling all of the information out of the log_in_attempts table. I then filtered my results using a WHERE clause and an AND operator to only show login attempts that were unsuccessful and happened after 18:00. Login attempts made after 18:00 are filtered out by the first condition, login_time > '18:00'. Success = FALSE is the second condition, which excludes unsuccessful login attempts. 

------------------------
   
Retrieve login attempts on specific dates  <a name="control-assessment">
===================
The date of the suspicious event was 2022-05-09. It is necessary to look into any login activity that occurred on 2022-05-09 or the day before.

I created a SQL query to filter for login attempts that happened on particular dates, as you can see from the code below.

<p align="center">
Code: <br/>
<img src="https://i.imgur.com/SeJbKwg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

My query appears in the first section of the screenshot, and some of the output appears in the second. All login attempts made on 2022-05-09 or 2022-05-08 are returned by this query. I began by pulling all of the information out of the log_in_attempts table. Next, I filtered my results to only show login attempts made on either 2022-05-08 or 2022-05-09 using a WHERE clause and an OR operator. Login_date = '2022-05-09' is the first condition that filters for logins on 2022-05-09. Login_date = '2022-05-08' is the second condition that filters for logins on 2022-05-08.

Retrieve login attempts outside of Mexico  <a name="control-assessment">
===================

It appears there is a problem with the login attempts that happened outside of Mexico after looking into the organization's login attempt data. A investigation into these login attempts is necessary.

I created a SQL query to filter for login attempts that happened outside of Mexico, as you can see from the code below. 

<p align="center">
Code: <br/>
<img src="https://i.imgur.com/wgXKPmC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

My query appears in the first section of the screenshot, and some of the output appears in the second. All login attempts made in nations other than Mexico are returned by this query. I began by pulling all of the information out of the log_in_attempts table. Subsequently, I employed a WHERE clause with NOT to exclude all nations except Mexico. Since the dataset refers to Mexico as MEX and MEXICO, I chose LIKE with MEX% as the pattern to match. When used with LIKE, the percentage sign (%) represents any number of unspecified characters. 

Retrieve employees in Marketing  <a name="control-assessment">
===================

The marketing department's staff members' computers need to be updated, according to my team. I need information on which employee machines to update before I can accomplish this.

The code that follows shows how I constructed a SQL query to look for employee machines among the staff members of the East building's Marketing department.

<p align="center">
Code: <br/>
<img src="https://i.imgur.com/opvVni9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

My query appears in the first section of the screenshot, and some of the output appears in the second. This search yields the names of every worker in the East building's Marketing division. I began by choosing every piece of information from the employees table. I then filtered for workers who are employed by the Marketing division and in the East building using a WHERE clause with AND. Since the data in the office column shows the East building with the particular office number, I used LIKE with East% as the pattern to match. The department = 'Marketing' part, which filters for staff members in the Marketing department, is the first condition. The office LIKE 'East%' part, which filters for workers in the East building, is the second requirement.

Retrieve employees in Finance or Sales  <a name="control-assessment">
===================
It's also necessary to update the machines used by the staff members of the finance and sales departments. I can only get employee data from these two departments because I need a different security update.

How I created a SQL query to filter for employee machines from employees in the Finance or Sales departments is shown in the code below.

<p align="center">
Code: <br/>
<img src="https://i.imgur.com/4Q793sP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

My query appears in the first section of the screenshot, and some of the output appears in the second. All of the employees in the Finance and Sales departments are returned by this query. I began by choosing every piece of information from the employees table. I then filtered for workers in the Finance and Sales departments using a WHERE clause with OR. Because I want all employees who are in either department, I used the OR operator rather than the AND operator. To filter for employees in the Finance department, the first condition is department = 'Finance'. Department = 'Sales' is the second condition that selects workers in the Sales department.

Retrieve all employees not in IT  <a name="control-assessment">
===================
For staff members who do not work in the information technology department, my team needs to update security one more time. I need to gather information about these employees before I can make the update.

The following shows how I constructed a SQL query to exclude employees who are not part of the IT department from the employee machine filter.

<p align="center">
Code: <br/>
<img src="https://i.imgur.com/63mtsHv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

My query appears in the first section of the screenshot, and some of the output appears in the second. All employees who are not in the information technology department are returned by the query. I began by choosing every piece of information from the employees table. I then filtered for employees who weren't in this department using a WHERE clause with NOT.

Summary  <a name="control-assessment">
===================
I used SQL query filters to obtain particular data about employee computers and login attempts. I made use of the employees and log_in_attempts tables. I filtered for the precise information required for each task using the AND, OR, and NOT operators. In order to look for patterns, I also used LIKE and the wildcard percentage sign (%).

