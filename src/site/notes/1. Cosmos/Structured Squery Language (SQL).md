---
{"dg-publish":true,"permalink":"/1-cosmos/structured-squery-language-sql/","created":"2025-01-22T11:17:14.065-05:00","updated":"2024-05-28T12:02:49.274-04:00"}
---

202405281026
Status: #idea
Tags: [[Database\|Database]], [[Relational Database\|Relational Database]]
State: #nascient
# Structured Query Language (SQL)
Structured Query Language or SQL (pronounced sequel) which is a language that allows the interested to create databases that work with [[Relational Database Management System\|Relational Database Management System]].

It's called a [[Relational Database\|Relational Database]] because your [[Database\|database]] will be composed of multiple tables, akin to collections of class instances in programming. And tables will be connected to each other through [[Primary Keys\|primary keys]] and [[Foreign Keys\|foreign keys]]. The former is a column filled with unique values to identify specific rows, the latter is the same thing except it points to elements of other tables.

Important to note that SQL is not key sensitive for its keywords therefore:
seLect, SELECT, select, selEcT, etc. are all equivalent. 

But by convention we use the second one, since column names and row names will typically be in lowercase.

Also in SQL statements are closed with ';', it will ignore line breaks and whatnot and will only consider a statement over when it encounters ';'.
## Some Keywords
**SELECT** : Keywords which selects stuff. It will always be used as SELECT *things you want to select* FROM *database*
**CREATE**:  A keyword used to create new things. Usage: CREATE *OBJECT TYPE name*
**DROP**: A keyword to delete things. Usage: DROP *OBJECT TYPE name*;
**USE**: Specifies to SQL which database to put in scope for the commands (select, insert, ...) Usage: USE *database*
**INSERT INTO**: Basically the how you add rows to a table. Usage: INSERT INTO *table* (*parameters) VALUES (*parameters), (*parameters), ...(*parameters)**;**
**UPDATE**: This how you modify rows, you will typically couple it with a **WHERE** statement to whittle down to specifically the rows you want to modify. If you **SET** some column to a new value without beforehand filtering with, you will modify the entire table. Usage: UPDATE *table* SET *value* WHERE *condition*;
**ALTER**: The keyword we use to modify an object that already exists. Usage: ALTER *OBJECT TYPE name*
**AS**: Used to alias, the same thing and use as in python. Typically going to be useful if you're doing  a join and the tables have conflicting column names.
**JOIN**: Joins two tables together, this is what makes relational databases so powerful. Without specifying the type of JOIN, MySQL defaults to Inner Join.

**NOT NULL**: Enforces that a column cannot contain null values
**PRIMARY KEY**: Self explanatory
**FOREIGN KEY**: Self explanatory
**AUTO_INCREMENT**: Will automatically increment numerical values when new elements are added to a table, typically used with an "id" column that is used as PRIMARY KEY, to allow us to add elements without having to keep track of the latest id. To do so we will add objects without passing the id. If we do pass whatever we used AUTO_INCREMENT on, it will automatically increment from this new value.

## Type of Joins
Put in its own thing, because Joins are going to be used in many places from Excel to pandas to Firebase (I think?), so having it coupled with the SQL note doesn't really make sense.

For SQL this is the correct syntax:
```SQL
SELECT * FROM left_table
JOIN right_table ON condition
```

This is the general syntax, as stated by default, JOIN is an [[Inner Join\|inner join]].

For example:
```SQL
SELECT * FROM left_table
JOIN right_table ON left_table.id = right_table.id
```
[[1. Cosmos/Types of Joins\|Types of Joins]]

## Aggregates
We can use select to select rows in the data, but sometimes we do not actual rows but instead we want to compute to statistics about that data to get more information. IN that case we will need to use aggregate functions.

They are typically straightforward, COUNT() counts, SUM() sums, AVG() averages, etc.

Often when doing aggregates we will want to return multiple "columns" and group the data in away that it makes sense. 

For example if I am taking the average of grades given students had within a semester, I would want to select both student_id, and AVG(grade) FROM grades.
It wouldn't make much sense to take a global average of the grades (well no it would actually make sense), but here since we're considering student_id as well it is fair to assume we want per student. Therefore we'd use GROUP BY *category* to indicate what to group by. The category has to be something that someone cannot be both at the same time. For example, gender would be a good choice since you wouldn't store someone as both male and female. I do not have a counterexample in mind as I am writing this, but you want the groups to be disjoint.

This would be the code you write for the above example
```SQL
SELECT student_id, AVG(grade) FROM grades
GROUP BY student_id
```


## References
[[SQL ~ Flashcards\|SQL ~ Flashcards]]
[Learn SQL in 60 Minutes](https://www.youtube.com/watch?v=p3qvj9hO_Bo)