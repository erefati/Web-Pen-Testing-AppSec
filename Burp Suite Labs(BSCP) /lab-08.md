Lab 08 - SQL injection attack, querying the database type and version on MySQL and Microsoft

SQL Injection - Product Category

End goal: Display the database version 

Analysis:

Determine the number of columns that are being returned by the query and which columns contain text data. Verify that the query is returning two columns, both of which contain text, using a payload like the following in the category parameter:

'+UNION+SELECT+'abc','def'#

Use the following payload to display the database version:

'+UNION+SELECT+@@version,+NULL#



