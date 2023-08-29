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




-----------

NOTES AUG 29TH:

NOTE: can right click on arrow in our inspect element console log for our api data to copy an are. We can then paste one into our model to refer to when we are creating our model.

can take the data from our api and adapt it into something else, like so: this.creatorName = data.creator.name <---- this grabs the name of the creator, out of the creator object in our api data

* this is referred to as flattening out a data object. We are 'adapting' the data object properties into our own property on our class

***remember, we use map() to create new instances of our model class for each of the objects in the data object that we pass from the api.***

* passing the data objects from the API through our car class

the @type import notes just give us more intellisense on our code.

note: use elevation to elevate card from page!!!!!!!!

go to 'collapse' in BS to get a collapsible form/item

api post: this is kind of like a create

* any time we do a post request, we will be supplying some kind of body. The body is what we are trying to insert into the API

* post needs 2 arguments: an endpoint, and a data body


NOTE: make sure to be checking out the network tab for issues when using API

env.js is our environment variables.

* want to change the baseURL in env.js, make it the same baseURL for our sandboxApi

NOTE: want to do any kind of form requests inside of a try/catch 

NEW FUNCTIONALITY: static

* a static exists on the class itself, as opposed to instances of the class. EG for our form in Gregslist, creating out car form as static allows it to persist.

* we have to invoke static functions, as opposed to getter functions which are automatically invoked

NOTE: if you click on a line and copy, it will copy the whole line even though it's not highlighted.

our edits will look extremely similar to our creates

***put request***

* const res = await api.put('api/cars')

res shorthand = response

findIndex() function finds index of an item in an array

crud: create read update delete

splice takes the old and replaces it with the new

