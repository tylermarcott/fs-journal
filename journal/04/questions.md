# Understanding Asynchronous Code, and API's
01. What is the difference between `asynchronous` code and `synchronous` code?

  > synchronous code runs line by line in a cascading sort of way. Asynchronous code does not run in a straight line. We have awaits, listeners, emits, things that may be called at different times depending on what kind of situation is happening.

02. What is an event listener?

  > An event listener is a method that waits for a change to happen in a specific set of data. Every time that change happens, it will do something.

03. What does *REST* stand for, and in simple terms what does it mean??

  > Representational state transfer, REST is an architectural design that allows a function to accept a certain amount of arguments in an array, such as from an API

04. What is a callback / higher order function?

  > Functions that don't necessarily immediately produce a result, AKA asynchronous functions/ programming

05. What is a `promise`? How do you capture an error from a `promise`?

  > A promise is something that is made when we have an await to fulfill some sort of task. We can capture an error from a promise using a try/catch

06. Name three processes used to make requests over `HTTP`?

  > put, post, get

07. What does the `API` acronym stand for?

  > Application Programming Interface

08. What must you do in order to `await` a promise inside of a function?

  > Declare your function where something is being awaited inside asynchronous. You must also give whatever you are awaiting on a way to either fulfill or not fulfill a promise.

09. What is the purpose of encapsulation in programming?

  > Encapsulation is a method of creating functions, classes and sets of data that are independent of eachother. The reasoning behind this is code reusability, ease of debugging, and when one thing breaks, everything that is linked to it doesn't also break. Encapsulation also hides data from the user that isn't necessary for them to see, in a 'capsule'

10. What is `HTTP` response code for a successful request?

  > code 200 ok

11. What is a 400 error?

  > a bad request error.
