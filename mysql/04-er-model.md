# ER model

- Entity-relationship model is a model used for design and representation of relationships between data.

- The main data objects are termed as Entities, with their details defined as attributes, some of these attributes are
  important and are used to identity the entity, and different entities are related using relationships.

## Components of ER Model

- **Entity**: Represents a real-world object or concept, such as a person, place, or event. Entities have attributes
  that
  describe their properties.
- **Attributes**: Characteristics or properties of an entity. Attributes are used to describe entities and are stored as
  columns in a database table.
    - Simple attribute: The attributes with values that are atomic and cannot be broken down further are simple
      attributes. For example, student's age.
    - Composite attribute: A composite attribute is made up of more than one simple attribute. For example, student's
      address will contain, house no., street name, pincode etc.
    - Derived attribute: These are the attributes which are not present in the whole database management system, but
      are derived using other attributes. For example, average age of students in a class.
    - Single-valued attribute: As the name suggests, they have a single value.
    - Multi-valued attribute: And, they can have multiple values.
- **Keys**: Keys are used to uniquely identify an entity within a table. There are different types of keys:
    - **Super key**: A super key is a set of one or more attributes that, taken collectively, allow us to identify a
      unique record in a table.
    - **Candidate key**: A candidate key is a minimal super key, meaning it is a super key without any redundant
      attributes.
    - **Primary key**: A primary key is a candidate key that is chosen as the main method of uniquely identifying
      records in a table.
- **Relationships**: Relationships define how entities are related to each other. They can be one-to-one, one-to-many,
  or many-to-many.
    - **One-to-One**: A single entity in one table is related to a single entity in another table.
    - **One-to-Many**: A single entity in one table is related to multiple entities in another table.
    - **Many-to-Many**: Multiple entities in one table are related to multiple entities in another table.

## ER Diagram

- ER Diagram is a visual representation of data that describes how data is related to each other. In ER Model, we
  disintegrate data into entities, attributes and setup relationships between entities, all this can be represented
  visually using the ER diagram.

