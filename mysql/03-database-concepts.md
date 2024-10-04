# What is a Database?

- A Database is a collection of related data organised in a way that data can be easily accessed, managed and updated.
  Database can be software based or hardware based, with one sole purpose, storing data.

# What is DBMS?

- A DBMS is a software that allows creation, definition and manipulation of database, allowing users to store,
  process and analyse data easily. DBMS provides us with an interface or a tool, to perform various operations like
  creating database, storing data in it, updating data, creating tables in the database and a lot more
- DBMS also provides protection and security to the databases. It also maintains data consistency in case of multiple
  users.

# Characteristics of Database Management System

- Data stored into Tables:  Data is never directly stored into the database. Data is stored into tables, created inside
  the database. DBMS also allows to have relationships between tables which makes the data more meaningful and
  connected. You can easily understand what type of data is stored where by looking at all the tables created in a
  database.
- Reduced Redundancy: In the modern world hard drives are very cheap, but earlier when hard drives were too expensive,
  unnecessary repetition of data in database was a big problem. But DBMS follows Normalisation which divides the data in
  such a way that repetition is minimum.
- Data Consistency: On Live data, i.e. data that is being continuosly updated and added, maintaining the consistency of
  data can become a challenge. But DBMS handles it all by itself.
- Support Multiple user and Concurrent Access: DBMS allows multiple users to work on it(update, insert, delete data) at
  the same time and still manages to maintain the data consistency.
- Query Language: DBMS provides users with a simple Query language, using which data can be easily fetched, inserted,
  deleted and updated in a database.
- Security: The DBMS also takes care of the security of data, protecting the data from un-authorised access. In a
  typical
  DBMS, we can create user accounts with different access permissions, using which we can easily secure our data by
  restricting user access.
- DBMS supports **transactions**, which allows us to better handle and manage data integrity in real world applications
  where
  multi-threading is extensively used.