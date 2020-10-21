
# **Reading Assignment 8 - SQL**

1. ## SQL Overview
  + ### Definition
    + Before learning the SQL syntax, it's important to have a model for what a relational database actually is. A relational database represents a collection of related (two-dimensional) tables. Each of the tables are similar to an Excel spreadsheet, with a fixed number of named columns (the attributes or properties of the table) and any number of rows of data.

    + For example, if the Department of Motor Vehicles had a database, you might find a table containing all the known vehicles that people in the state are driving. This table might need to store the model name, type, number of wheels, and number of doors of each vehicle for example. methods.
    + **Select Statements (Queries)**  
      + Given a table of data, the most basic query we could write would be one that selects for a couple columns (properties) of the table with all the rows (instances).
      + Select query for a specific columns
        + `SELECT column, another_column, …`
        + `FROM mytable;`
        + The result of this query will be a two-dimensional set of rows and columns, effectively a copy of the table, but only with the columns that we requested.
      + If we want to retrieve absolutely all the columns of data from a table, we can then use the asterisk (*) shorthand in place of listing all the column names individually.
        + Select query for all columns
        + `SELECT *` 
        + `FROM mytable;`
        + This query, in particular, is really useful because it's a simple way to inspect a table by dumping all the data at once.
      + In order to filter certain results from being returned, we need to use a WHERE clause in the query. The clause is applied to each row of data by checking specific column values to determine whether it should be included in the results or not.
        + Select query with constraints
        + `SELECT column, another_column, …`
        + `FROM mytable`
        + `WHERE condition`
          + `AND/OR another_condition`
          + `AND/OR …;`
      + More complex clauses can be constructed by joining numerous AND or OR logical keywords (ie. num_wheels >= 4 AND doors <= 2). And below are some useful operators that you can use for numerical data (ie. integer or floating point):
        + **Operator	        Condition	                                            SQL Example**
        + =, !=, < <=, >, >=	Standard numerical operators	                        col_name != 4
        + BETWEEN … AND …	    Number is within range of two values (inclusive)	    col_name BETWEEN 1.5 AND 10.5
        + NOT BETWEEN … AND …	Number is not within range of two values (inclusive)	col_name NOT BETWEEN 1 AND 10
        + IN (…)	            Number exists in a list	                              col_name IN (2, 4, 6)
        + NOT IN (…)	        Number does not exist in a list	                      col_name NOT IN (1, 3, 5)
      + When writing WHERE clauses with columns containing text data, SQL supports a number of useful operators to do things like case-insensitive string comparison and wildcard pattern matching. We show a few common text-data specific operators below:
        + **Operator	Condition	                                                                                            Example**
        + =	          Case sensitive exact string comparison (notice the single equals)	                                    col_name = "abc"
        + != or <>	  Case sensitive exact string inequality comparison	                                                    col_name != "abcd"
        + LIKE	      Case insensitive exact string comparison	                                                            col_name LIKE "ABC"
        + NOT LIKE	  Case insensitive exact string inequality comparison	                                                  col_name NOT LIKE "ABCD"
        + %	          Used anywhere in a string to match a sequence of zero or more characters (only with LIKE or NOT LIKE)	col_name LIKE "%AT%"(matches "AT", "ATTIC", "CAT" or even "BATS")
        + _	          Used anywhere in a string to match a single character (only with LIKE or NOT LIKE)	                  col_name LIKE "AN_"(matches "AND", but not "AN")
        + IN (…)	    String exists in a list	                                                                              col_name IN ("A", "B", "C")
        + NOT IN (…)	String does not exist in a list	                                                                      col_name NOT IN ("D", "E", "F")
      + Even though the data in a database may be unique, the results of any particular query may not be – take our Movies table for example, many different movies can be released the same year. In such cases, SQL provides a convenient way to discard rows that have a duplicate column value by using the DISTINCT keyword.
        + Select query with unique results
          + `SELECT DISTINCT column, another_column, …`
          + `FROM mytable`
          + `WHERE condition(s);`
      + Unlike our neatly ordered table in the last few lessons, most data in real databases are added in no particular column order. As a result, it can be difficult to read through and understand the results of a query as the size of a table increases to thousands or even millions rows.
      + To help with this, SQL provides a way to sort your results by a given column in ascending or descending order using the ORDER BY clause.
        + Select query with ordered results
          + `SELECT column, another_column, …`
          + `FROM mytable`
          + `WHERE condition(s)`
          + `ORDER BY column ASC/DESC;`
        + When an ORDER BY clause is specified, each row is sorted alpha-numerically based on the specified column's value. In some databases, you can also specify a collation to better sort data containing international text.
      + Another clause which is commonly used with the ORDER BY clause are the LIMIT and OFFSET clauses, which are a useful optimization to indicate to the database the subset of the results you care about.
      + The LIMIT will reduce the number of rows to return, and the optional OFFSET will specify where to begin counting the number rows from.
        + Select query with limited rows
          + `SELECT column, another_column, …`
          + `FROM mytable`
          + `WHERE condition(s)`
          + `ORDER BY column ASC/DESC`
          + `LIMIT num_limit OFFSET num_offset;`
