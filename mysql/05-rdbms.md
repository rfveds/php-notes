# RDBMS

- Relational Database management System(RDBMS) is a database management system based on the relational model introduced
  by
  E.F Codd. In relational model, data is stored in relations(tables) and is represented in form of tuples(rows).

- RDBMS is used to manage Relational database. Relational database is a collection of organized set of tables related to
  each other, and from which data can be accessed easily. Relational Database is the most commonly used database these
  days.

## Table

- In Relational database model, a table is a collection of data elements organised in terms of rows and columns. A table
  is also considered as a convenient representation of relations. But a table can have duplicate row of data while a
  true relation cannot have duplicate data. Table is the most simplest form of data storage. Below is an example of an
  Employee table.

## Tuple

- A single entry in a table is called a Tuple or Record or Row. A tuple in a table represents a set of related data. For
  example, the above Employee table has 4 tuples/records/rows.

  Following is an example of single record or tuple.
- **Employee Table**
- | EmpID | EmpName | EmpSalary | EmpDept |
          |-------|---------|-----------|---------|
  | 101   | John    | 50000     | IT      |

## Attributes

- A table consists of several records(row), each record can be broken down into several smaller parts of data known as
  Attributes. The above Employee table consist of four attributes, ID, Name, Age and Salary.

- **Attribute Domain**
  When an attribute is defined in a relation(table), it is defined to hold only a certain type of values, which is known
  as Attribute Domain. Hence, the attribute Name will hold the name of employee for every tuple. If we save employee's
  address there, it will
  be violation of the Relational database model.

### What is a Relation Schema?

A relation schema describes the structure of the relation, with the name of the relation(name of table), its attributes
and their names and type.

### What is a Relation Key?

- A relation key is an attribute which can uniquely identify a particular tuple(row) in a relation(table).

- Every relation in a relational database model should abide by or follow a few constraints to be a valid relation,
  these
  constraints are called as Relational Integrity Constraints.

- The three main Integrity Constraints are:
    - Key Constraints
    - Domain Constraints
    - Referential integrity Constraints

**Key Constraints**
We store data in tables, to later access it whenever required. In every table one or more than one attributes together
are used to fetch data from tables. The Key Constraint specifies that there should be such an attribute(column) in a
relation(table), which can be used to fetch data for any tuple(row).

The Key attribute should never be NULL or same for two different row of data.

For example, in the Employee table we can use the attribute ID to fetch data for each of the employee. No value of ID is
null and it is unique for every row, hence it can be our Key attribute.

**Domain Constraint**
Domain constraints refers to the rules defined for the values that can be stored for a certain attribute.

Like we explained above, we cannot store Address of employee in the column for Name.

Similarly, a mobile number cannot exceed 10 digits.