---
markdown-version:
tool-type: theia
branch: lab-4181-instruction
version-history-start-date: '2023-01-19T10:41:24Z'
---

## SQL Cheat Sheet: Intermediate - LIKE, ORDER BY, GROUP BY

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
LIKE
</td>
<td style="width:30%">
<code>SELECT column1, column2, ...
FROM table_name
WHERE columnN LIKE pattern; </code>
</td>
<td style="width:30%">
<code>LIKE</code> operator is used in a WHERE clause to search for a specified pattern in a column.<br/>
There are two wildcards often used in conjunction with the LIKE operator which are percent sign(%) and underscore sign (_).

</td>
<td style="width:30%">
<code>SELECT f_name , l_name
FROM employees
WHERE address LIKE '%Elgin,IL%';</code>
</td>
</tr>

<tr>
<td style="width:10%">
BETWEEN
</td>
<td style="width:30%">
<code>SELECT column_name(s) 
FROM table_name
WHERE column_name BETWEEN value1 AND value2;</code>
</td>
<td style="width:30%">
The <code>BETWEEN</code> operator selects values within a given range. The values can be numbers, text, or dates. The <code>BETWEEN</code> operator is inclusive: begin and end values are included. 
</td>
<td style="width:30%">
<code>SELECT * FROM employees WHERE salary BETWEEN 40000 AND 80000;</code>
</td>
</tr>

<tr>
<td style="width:10%">
ORDER BY
</td>
<td style="width:30%">
<code>SELECT column1, column2, ...
FROM table_name
ORDER BY column1, column2, ... ASC|DESC; </code>
</td>
<td style="width:30%">
<code>ORDER BY</code> keyword is used to sort the result-set in ascending or descending order. The default is ascending.
</td>
<td style="width:30%">
<code>SELECT f_name, l_name, dep_id 
FROM employees
ORDER BY dep_id DESC, l_name;</code>
</td>
</tr>

<tr>
<td style="width:10%">
GROUP BY
</td>
<td style="width:30%">
<code>SELECT column_name(s)
FROM table_name
WHERE condition
GROUP BY column_name(s)
ORDER BY column_name(s); </code>
</td>
<td style="width:30%">
<code>GROUP BY</code> clause is used in collaboration with the SELECT statement to arrange identical data into groups.
</td>
<td style="width:30%">
<code>SELECT dep_id, COUNT(*)
FROM employees
GROUP BY dep_id;</code>
</td>
</tr>

</table>

## Author(s)

[Lakshmi Holla](https://www.linkedin.com/in/lakshmi-holla-b39062149/?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkDB0201ENSkillsNetwork22-2022-01-01)

## Changelog

| Date       | Version | Changed by    | Change Description |
| ---------- | ------- | ------------- | ------------------ |
| 2021-07-28 | 1.0     | Lakshmi Holla | Initial Version    |
