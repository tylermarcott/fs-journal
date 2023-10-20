# A bit more CSharp and SQL
1. What does ***inheritance*** accomplish for us in C#?

Inheritance enables you to create new classes that reuse, extend and modify the behavior defined in other classes

2. How does ***member inheritance*** work in C#? Does a `Class` inherit all members of the base `Class`?

When you define a class to derive from another class, the derived class implicitly gains all the members of the base class, except for its constructors and finalizers.

3. How does ***accessibility*** affect inheritance?

Private members are visible only in derived classes that are nested in their base class.

4. What is the difference between a `PRIMARY KEY` and a `FOREIGN KEY`

A primary key is a unique identifier for each record in a table. A foreign key establishes a relationship between tables by referencing the primary key of another table.

5. What is an ***alias***?

An alias is a shortening of the name of a table, column etc. in SQL, makes the code shorter

6. Demonstrate how you would query a join statement that would get all of a doctors patients from the following collections:

  ```SQL
  CREATE TABLE doctors (
    id INT NOT NULL AUTO_INCREMENT,
    -- CODE OMITTED
    PRIMARY KEY (id)
  )

  CREATE TABLE patients (
    id INT NOT NULL AUTO_INCREMENT,
    -- CODE OMITTED
    PRIMARY KEY (id)
  )

  CREATE TABLE patient_doctors (
    id INT NOT NULL AUTO_INCREMENT,
    doctorId INT NOT NULL,
    patientId INT NOT NULL,

    FOREIGN KEY (doctorId)
      REFERENCES doctors(id),
    FOREIGN KEY (patientId)
      REFERENCES patients(id),
  )

  ```

  > | ANSWER HERE |
