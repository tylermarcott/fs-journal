# Intro to Server side concerns with JavaScript
01. What do the letters of the acronym `CRUD` stand for?

  > | Create, Read, Update, Delete

02. Each action that `CRUD` represents maps to an HTTP request. What HTTP request does each `CRUD` action correspond to?

  > create = post, read = get, update = put, delete = delete

03. What does `ORM` stand for? Which `ORM` do we use when interacting with MongoDB

  > Object Relational Mapping. We use the Mongoose ORM when interacting with MongoDB

04. Which two `HTTP` request types include a body?

  > a put and a create

05. In a/an _______ coding model, when you call a function, it returns only when the action has finished and stops your program for the time the action takes. Likewise in a/an _______ coding model, multiple things are allowed to happen at one time. When you perform an action, your program continues to run.  Fill in the blanks.

  > asynchronous, synchronous

06. What are the three types of data relationships? Provide an example of each.

  > 1-to-1: an author to an address. 1 author has 1 address, 1-to-many: an author to books. 1 author may have many books. Many-to-many: Authors to books. Some authors may have worked on multiple of the same books/ some books may have multiple authors

07. What is middleware?

  > Middleware is something that we use that acts as the middle man between apps and systems. Such as Mongoose acting as a middleman between Mongo and Node!

08. The ______ pipeline delivers information from the client while the ______ pipeline returns it. Fill in the blanks. 

  > I'm honestly not quite sure lol. I bet one is data.

09. Demonstrate the pattern that is used to include a request query with the client's `HTTP` request providing the property `tag` and the value `winter`.

  > http://web_address?tag=winter

10. What is a ***virtual property***?

  > a virtual property is basically like Mongoose's version of a getter and setter. It provides additional fields for a given model, where the additional fields do not persist in the database.
