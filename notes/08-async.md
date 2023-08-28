# Async


NOTES: MON aug 28th


asynchronous code

let prom = new Promise()    //functions can make promises to do something, just like people make promises to each other IRL

* if we console log this promise, it will say Promise pending

can use resolve() in our promise, which will fulfill our promise

we can also use reject(), which will deny the promise

an uncaught error is an error that happens out of a try/catch

try{
  put your code here

} catch(error){
  console.error(error)
  //the error that comes into the catch is the error that was provoked

  Pop.toast('an error occurrredddd')
}

*   ^ this allows us to direct our code down certain paths
* if an error occurred here, let's go down a different path

A promise creates a function to pause the standard asynchronous running of code.


APIs: Application Program Interfaces

*This is how one application talks to another, an API interface in order to talk to a database

When we use our API, we are going to first created a controller, service and model for the API. For example: monster

* NOTE: can cmd + click on a function call to take you to the location of the function

HTTP.cat to learn about web response codes: https://http.cat/

BS has a class just called card, which makes your tag look like a card

g-1: gap 1, gap between stuff idk lol


need the axios script to use axios

script:axios

* one of the shortcuts with axios is it allows us to pull JSON text and it automatically converts it for us.