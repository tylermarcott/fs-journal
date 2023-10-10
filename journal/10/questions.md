# CSharp and SQL Fundamentals
01. What is the purpose of a `namespace`?

A namespace is a declarative region that provides a scope to the identifiers inside it.

02. What is the difference between a `class` and an `interface`?

A class is a blueprint for creating an object, where as an interface is a contract that defines the behavior of a class.

03. What is the method that returns an instance of a class, yet it has no return type?

Void

05. In the Car example what is the access modifier of the `Start()` method?

  ```c#
  abstract class Car
  {
    public string Start()
    {

      return "Vroooom";

    }
  }
  ```

Public, which means everyone has access to it.

06. In the Car example what is `string` an indication of?

String tells us what data type the method is.

07. In the Car example what is `abstract` preventing?

An abstracted class is a class that cannot be instantiated.

08. In a SQL table, what is the difference between information in a row and information in a column?

Data in a row contains information that describes a single entity, while data in a column describes a field of information all entities possess.

09. Demonstrate the necessary SQL for creating a table called `characters` with the values `name, age, description` as strings, and an `int` id.

CREATE TABLE characters (
  name VARCHAR(50),
  age VARCHAR(20),
  description VARCHAR(500),
  id int NOT NULL 
)

10. In SQL how can you query more than a single table? Provide an example.

By providing the appropriate foreign keys, EG:
FOREIGN KEY (license_plate)
  REFERENCES vehicles(license_plate),
FOREIGN KEY (license_number)
  REFERENCES customers(license_number)
