# Why we need Normalization in DBMS?

- Normalization is required for,

    - Eliminating redundant(useless) data, therefore handling data integrity, because if data is repeated it increases
      the
      chances of inconsistent data.

    - Normalization helps in keeping data consistent by storing the data in one table and referencing it everywhere
      else.

    - Storage optimization although that is not an issue these days because Database storage is cheap.

    - Breaking down large tables into smaller tables with relationships, so it makes the database structure more
      scalable
      and adaptable.

    - Ensuring data dependencies make sense i.e. data is logically stored.

# Problems without Normalization

- Insertion Anomaly: If we have to insert data in a table with multiple columns, and if we don't have data for all
  columns, then we have to insert NULL values which is not a good practice. Redundant data can also be inserted.
- Update Anomaly: If we have to update data in a table with multiple columns, then we have to update data in multiple
  places which can lead to inconsistency.
- Deletion Anomaly: If we have to delete data in a table with multiple columns, then we have to delete data in multiple
  places which can lead to loss of data.

# Normal Forms

- Normal forms are the rules that are applied to the database to normalize it. There are 5 normal forms, and each normal
  form has its own set of rules.

### 1NF (First Normal Form)

- A table is in 1NF if it has a Primary Key and all the columns are atomic i.e. they cannot be further divided.
- No multivalued attributes are allowed.
- Data in one column should be of the same type.
- Repeating groups are not allowed.

### 2NF (Second Normal Form)

- Each non-key attribute must depend on the entire primary key.

### 3NF (Third Normal Form)

- A table is in 3NF if it is in 2NF and no transitive dependency is allowed. Non-key attributes should not depend on
  other non-key attributes.
- Every non-key attribute should be directly dependent on the primary key, the whole primary key, and nothing but the
  primary.

### BCNF (Boyce-Codd Normal Form)

- A table is in BCNF if it is in 3NF and for every functional dependency `X -> Y`, `X` should be a super key.
- BCNF is a stronger version of 3NF.
- Every attribute should be directly dependent on the primary key.

### 4NF (Fourth Normal Form)

- A table is in 4NF if it is in 3NF and multivalued dependencies are not allowed.
- Solution to multi-valued dependencies is to create a separate table for multi-valued attributes.

### 5NF (Fifth Normal Form)

- A table is in 5NF if it is in 4NF, and it can be decomposed into smaller tables without losing any information.
- It can not be described as join of two or more tables.

