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

