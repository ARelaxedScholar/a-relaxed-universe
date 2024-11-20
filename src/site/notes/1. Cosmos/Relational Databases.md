---
{"dg-publish":true,"permalink":"/1-cosmos/relational-databases/","created":"2024-08-31T23:47:14.962-04:00","updated":"2024-07-20T03:37:44.883-04:00"}
---

202407200337
Status: #idea
Tags: [[Database\|Database]]
State: #nascient
# Relational Databases

Basically excel spreadsheets with unique identifiers for each row.

Unique ID (Primary key): an ID that identifies a row. It must be UNIQUE. It can be inherent to the data (usernames for user accounts), or totally fabricated (Student IDs for students.) 

As long as it's unique, it can be **anything**.

Primary Keys which do not map to the real word are called *surrogate keys*.

Those that DO map to something in real life (inherent to the entries being stored ) are called *natural keys*.

Row : one element/object/thing stored in DB.

Column: attribute that an object in the DB can have.

So the crossing between a given row and a given column represents the location in DB where the value for that given attribute is stored for the object represented by the row.

## How to connect tables?

We use foreign keys. They are primary Keys of another table that are used as attributes if entries in some table. In this way we *connect* the two tables.

Hence we have a **relational** database. 

Note: the relation can go both ways, and two tables could have foreign-keys that connect one another. Also the foreign keys don't necessarily have to be unique. Furthermore a table can have as many foreign keys as it makes sense.

Like in SEG we could have reflexive associations, which connect a table to itself.

## Composite Key? Wazzat?
Sometimes we have situations where one attribute dies not uniquely identify a row, and it does not make sense to create a new id BUT together there are columns which identify a row uniquely.

In such cases our primary key will be composed of two (or more?) columns such keys are called **composite keys**. 

#sql #machinelearning

## References
