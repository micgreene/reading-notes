# **Reading Assignment 8 - Access Control (ACL)**

## When is Basic Authorization used vs. Bearer Authorization?
  + ### Definition
    + Database normalization is a process used to organize a database into tables and columns.  The main idea with this is that a table should be about a specific topic and only supporting topics included.
    + By limiting a table to one purpose you reduce the number of duplicate data contained within your database. This eliminates some issues stemming from database modifications.
    + There are three common forms of database normalization: 1st, 2nd, and 3rd normal form. They are also abbreviated as 1NF, 2NF, and 3NF respectively. 
    + The forms are progressive, meaning that to qualify for 3rd normal form a table must first satisfy the rules for 2nd normal form, and 2nd normal form must adhere to those for 1st normal form:
      1. First Normal Form – The information is stored in a relational table with each column containing atomic values. There are no repeating groups of columns.
      1. Second Normal Form – The table is in first normal form and all the columns depend on the table’s primary key.
      1. Third Normal Form – the table is in second normal form and all of its columns are not transitively dependent on the primary key
    + **Reasons for Database Normalization**  
      + There are three main reasons to normalize a database.  The first is to minimize duplicate data, the second is to minimize or avoid data modification issues, and the third is to simplify queries. 
    + **Data Duplication and Modification Anomalies**
      + Duplicated information presents two problems:
        1. It increases storage and decrease performance.
        1. It becomes more difficult to maintain data changes.
      + These situations are modification anomalies. Database normalization fixes them. There are three modification anomalies that can occur:
        1. **Insert Anomaly**
          + There are facts we cannot record until we know information for the entire row. Why? Because in order to create the record, we need provide a primary key. This is typically labelled as our 'id'.
    + **Update Anomaly**
      + In this case we have the same information in several rows. For instance if one column changes, then there are multiple updates that need to be made.  If we don’t update all rows, then inconsistencies appear.
    + **Deletion Anomaly**
      + Deletion of a row causes removal of more than one set of facts.  For instance, if just one piece of info in a row needs to be removed, then deleting that row causes us to lose information in the other columns associated with it.

## What does the JSON Web Token package do?

## What considerations should we make when creating and storing a SECRET?

## Document the following Vocabulary Terms
  + **Term**
  + **encryption**
  + **token**
  + **bearer**
  + **secret**
  + **JSON Web Token**
