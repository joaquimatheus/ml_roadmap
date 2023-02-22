---
markdown-version:
tool-type: theia
branch: lab-4180-instruction
version-history-start-date: '2023-01-19T10:41:19Z'
---

## SQL Cheat Sheet: FUNCTIONS and Implicit JOIN

<img src="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork/labs/Module%202/images/IDSNlogo.png" width="200" height="200">

<table>
<tr>
<th style="width:10%">
Command
</th>
<th style="width:30%">
Syntax
</th>
<th style="width:30%">
Description
</th>
<th style="width:30%">
Example
</th>
</tr>

<tr>
<td style="width:10%">
COUNT
</td>
<td style="width:30%">
<code>SELECT COUNT(column_name)
FROM table_name
WHERE condition;</code>
</td>
<td style="width:30%">
<code>COUNT</code>  function returns the number of rows that matches a specified criterion.
</td>
<td style="width:30%">
<code>SELECT COUNT(dep_id) FROM employees;</code>
</td>
</tr>

<tr>
<td style="width:10%">
AVG
</td>
<td style="width:30%">
<code>SELECT AVG(column_name)
FROM table_name
WHERE condition;</code>
</td>
<td style="width:30%">
<code>AVG</code> function returns the average value of a numeric column.
</td>
<td style="width:30%">
<code>SELECT AVG(salary) FROM employees;</code>
</td>
</tr>

<tr>
<td style="width:10%">
SUM
</td>
<td style="width:30%">
<code>SELECT SUM(column_name)
FROM table_name
WHERE condition; </code>
</td>
<td style="width:30%">
<code>SUM</code> function returns the total sum of a numeric column. 
</td>
<td style="width:30%">
<code>SELECT SUM(salary) FROM employees;</code>
</td>
</tr>

<tr>
<td style="width:10%">
MIN
</td>
<td style="width:30%">
<code>SELECT MIN(column_name)
FROM table_name
WHERE condition;</code>
</td>
<td style="width:30%">
<code>MIN</code> function returns the smallest value of the SELECTed column.
</td>
<td style="width:30%">
<code>SELECT MIN(salary) FROM employees;</code>
</td>
</tr>

<tr>
<td style="width:10%">
MAX
</td>
<td style="width:30%">
<code>SELECT MAX(column_name)
FROM table_name
WHERE condition; </code>
</td>
<td style="width:30%">
<code>MAX</code> function returns the largest value of the SELECTed column.
</td>
<td style="width:30%">
<code>SELECT MAX(salary) FROM employees;</code>
</td>
</tr>

<tr>
<td style="width:10%">
ROUND
</td>
<td style="width:30%">
<code>SELECT ROUND(2number, decimals, operation) AS RoundValue;</code>
</td>
<td style="width:30%">
<code>ROUND</code> function rounds a number to a specified number of decimal places.
</td>
<td style="width:30%">
<code>SELECT ROUND(salary) FROM employees;</code>
</td>
</tr>

<tr>
<td style="width:10%">
LENGTH
</td>
<td style="width:30%">
<code>SELECT LENGTH(column_name) 
FROM table;</code>
</td>
<td style="width:30%">
<code>LENGTH</code> function returns the length of a string (in bytes).
</td>
<td style="width:30%">
<code>SELECT LENGTH(f_name) FROM employees;</code>
</td>
</tr>

<tr>
<td style="width:10%">
UCASE
</td>
<td style="width:30%">
<code>SELECT UCASE(column_name) FROM table;</code>
</td>
<td style="width:30%">
<code>UCASE</code> function that displays the column name in each table in uppercase.
</td>
<td style="width:30%">
<code>SELECT UCASE(f_name) FROM employees;</code>
</td>
</tr>

<tr>
<td style="width:10%">
DISTINCT
</td>
<td style="width:30%">
<code>SELECT DISTINCT(column_name) FROM table;</code>
</td>
<td style="width:30%">
<code>DISTINCT</code> function is used to display data without duplicates.
</td>
<td style="width:30%">
<code>SELECT DISTINCT(UCASE(f_name)) FROM employees;</code>
</td>
</tr>

<tr>
<td style="width:10%">
DAY
</td>
<td style="width:30%">
<code>SELECT DAY(column_name) FROM table  </code>
</td>
<td style="width:30%">
<code>DAY</code> function returns the day of the month for a given date 
</td>
<td style="width:30%">
<code>SELECT DAY(b_date) FROM employees where emp_id = 'E1002'; </code>
</td>
</tr>

<tr>
<td style="width:10%">
CURRENT DATE
</td>
<td style="width:30%">
<code>SELECT (CURRENT DATE - COLUMN) FROM table; </code>
</td>
<td style="width:30%">
<code>CURRENT DATE</code> is used to display the current date.This can be subtracted from the previous date to get the difference.
</td>
<td style="width:30%">
<code>SELECT YEAR(CURRENT DATE - b_date) As AGE, CURRENT_DATE, b_date FROM employees;</code>
</td>
</tr>

<tr>
<td style="width:10%">
Subquery
</td>
<td style="width:30%">
<code>SELECT column_name [, column_name ]
FROM   table1 [, table2 ]
WHERE  column_name OPERATOR
   (SELECT column_name [, column_name ]
   FROM table1 [, table2 ]
   [WHERE]) </code>
</td>
<td style="width:30%">
<code>Subquery</code> is a query within another SQL query and embedded within the WHERE clause.

A subquery is used to return data that will be used in the main query as a condition to further restrict the data to be retrieved.

</td>
<td style="width:30%">

<code>SELECT emp_id, fmame, lname, salary
FROM employees
where salary
< (SELECT AVG(salary)
FROM employees);</code> <br/> <code>          SELECT \* FROM ( SELECT emp_id, f_name, l_name, dep_id FROM employees) AS emp4all; </code>

<br/>
<code>          SELECT * FROM employees WHERE job_id IN (SELECT job_ident FROM jobs);
</code>

</td>
</tr>

<tr>
<td style="width:10%">
Implicit Inner Join
</td>
<td style="width:30%">
<code>SELECT column_name(s)
FROM table1, table2
WHERE table1.column_name = table2.column_name; </code>
</td>
<td style="width:30%">
<code>Implicit Inner Join</code> combines the two or more records but displays only matching values in both tables.
Inner join applies only the specified columns.
</td>
<td style="width:30%">
<code>SELECT * FROM employees, jobs where employees.job_id = jobs.job_ident;</code>
</td>
</tr>

<tr>
<td style="width:10%">
Implicit Cross Join
</td>
<td style="width:30%">
<code>SELECT column_name(s)
FROM table1, table2; </code>
</td>
<td style="width:30%">
<code>Implicit Cross Join</code> defines as a Cartesian product where the number of rows in the first table multiplied by the number of rows in the second table..
</td>
<td style="width:30%">
<code>SELECT * FROM employees, jobs;</code>
</td>
</tr>

</table>

## Author(s)

[Lakshmi Holla](https://www.linkedin.com/in/lakshmi-holla-b39062149/?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkDB0201ENSkillsNetwork22-2022-01-01)

## Changelog

| Date       | Version | Changed by    | Change Description |
| ---------- | ------- | ------------- | ------------------ |
| 2021-07-28 | 1.0     | Lakshmi Holla | Initial Version    |
