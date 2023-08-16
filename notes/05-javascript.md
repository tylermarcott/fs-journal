# JavaScript

***EXTREMELY important to markup your code, taking notes, makes your code cleaner and easier to read.

***In Git, touch app.js to create JS file***

When you start a project, always make sure everything is linked up and working by creating a few test classes, and a console log in JS
- make sure this console log loads to console on web page

***use script tag to bring in javascript, add source app.js
- NOTE: scripts are typically loaded at the end of the body since they take the longest to load

// Primitive data types

//SECTION -  numbers (JS uses floats for their numbers)
- let jeremyLie = 6
- let otherNumber = -6
- let decimalNumber = 6.2
- let greeting = "hello"
- let otherGreeting = 'hello'
-let anotherGreeting = `Jeremy's lie was: "I have 6 cats"` <- backticks to escape both quotes and apostrophies
- let boolean = true
- let otherBoolean = true

// no values

let noValue //undefined
let unknownValue = undefined // writing this out is WHACK

let knownNothing = null // no value, NOT undefined

//NOTE - reference data types

// arrays, store value by position (index)
let arr = ['Jack Sparrow', 'Black Beard', 'Luffy', null]
let nums = [1, 3, 6, 8]
let mixed = ['howdy', 589, true]

//SECTION -  object store data using KEY : VALUE pairs

let obj = {
  cat: 'Georgie',
  dog: 'Dipper',
  bird: 'Kevin',
  weasel: 'Briggs'
}

can add stuff to objects or arrays by being like obj = 'fluff', adds another string to the object

//truthy falsey

let falseNumber = 0

let trueNumber = -5 // literally any other number than 0

let falseString = '' // nothing between quotes

let trueString = ' ' //any string with any character becomes true

//SECTION - functions
// are blocks of code to store and run later

function sayHello(){

}

//Parameters, temporary variables accessible to only this function while it is executing


function addNumbers(x,y) {
  console.log(x + y)
  return x + y // returns give back a value
}

//NOTE - in html, using onclick, we can have a button activate our JS function

can use //#region regionName and //#regionEnd or something like that to create a bunch of collapsible code or text

//SECTION - app time

DOM: document object model

use d-none and remove('d-none') for removing or revealing stuff in dom

---------------

***!SECTION: NOTES 8/15***

NOTE: Mick put 4 col-6s in a single row instead of making 2 rows

const creates a variable that is immutable (cannot be changed)

***can create an array of objects!

Easy to use an alias to access an array:
- let animal = animal[i]


animals.forEach() // this method only exists on arrays

*anonymous/ no named function is a function that is called and destroyed/ not reusable
- anonymous is a METHOD

- animals.forEach((entity) => {
    console.log(entity.name)
    console.log(entity.name, entity.favoriteFood)
    }
  )


  a predicate function is a callback function that has to return something


filter method

areas.forEach(area) =>  {
  console.log(area)

  animals.filter((animal => animal.currentArea == area)) // filter creates an array of elements that match the condition

  let animalEmojis = inArea.map((animal) => animal.emoji + animal.name) // map creates an array of transformed results specified. Makes a copy of the array based on the transformations we apply

  document.getElementById(area).innerText = animalEmojis.join(', ') // Join turns the elements in the array into a string, inserting ', ' in between them
}


animals.find(animals => animal.emoji == 'lobsteremoji')

arrays can have objects, and said objects can have arrays within them too


----------

//SECTION - Notes Wed 8/16

Note: the forEach loop is array specific, can't use it for more simple loops like you can with just a regular for loop

*** don't forget there are span tags, Sam used them to create a kind of footer, price and name on a picture of a sandwich in the lecture project today

try using px instead of % for border-radius, seems to give a better effect, I have been having issues lately with weird custom css borders lol

//NOTE: single responsibility discipline: one function, one responsibility. If your function does more than one thing, abstract data out of that function and create another function.

//NOTE: code small, test small. console.log() all of your functions and related stuff so you know it's working first, before you move on and make it more complicated

.menu-item:hover{
  cursor: 
  transform: 
}


//REVIEW - look at ALL the sandwiches, and FIND the one sandwich => where it's name == 'caprese'

^^
let caprese = sandwiches.find(sandwich => sandwich.name == 'caprese')


caprese.quantity++ //increases the value of our caprese sandwich quantity

*********
//NOTE: cmd + D allows you to highlight same names multiple times for replacement
********

