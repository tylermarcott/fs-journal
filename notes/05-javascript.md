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

Refactoring is a very important process in our learning right now. Learning what parts of a function we can pull out to refactor and create another function, in order to simplify our code

** use backticks `` to inject javascript values in a string, use ${} to injector javascript into the string

***forEach loop inside function is an anonymous function itself

.find function is a forEach under the hood.

title-tag -> indicate a title when a button or something else is hovered over



--------

Notes 8/17: Game Logic Build

//NOTE: main>section.row

-->> targeting main tag all sections with the class "row"



//sets function with fixed time interval that goes off every so many seconds or whatever you want to set it as

***NEW FUNCTION: 

setInterval(decreaseOsloHunger, 1000)   <-- NOTE: 1000 is 1 seconds, because it's in milliseconds

- this is saying that decreaseOsloHunger will be called every second

If we only have one line of logic, we don't always have to split it up:

if(oslo.hunger <= 0) oslo.hunger = 0     <<--- this is a clamp for our setInterval method

***type debugger in your code to allow you to step through your code in VScode


can use //#region



//#endregion

and created blocks of code that can be collapsed 


switch(animal.status){
  case: ''
}

marquee tag lets our icons bounce around in there container

---------

*** query selector



----

Dungeon project notes:

function attackBoss(){

  let heroDamage = 0

  heroes.forEach(hero =>{

  })


}


----

Week 2 reading notes:

difference between var and let: let is block scoped

* let is available to be used within a block of code (between a set of curly braces)
* let cannot be re declared within a scope

const

* const cannot be updated or re-declared, unlike let and var
* the value of a variable declared with const remains the same within the scope
* also block scoped like let

var declarations are globally scoped or function scoped while let and const are block scoped.

var variables can be updated and re-declared within its scope; let variables can be updated but not re-declared; const variables can neither be updated nor re-declared.

They are all hoisted to the top of their scope but while varvariables are initialized with undefined, let and const variables are not initialized.

While var and let can be declared without being initialized, const must be initialized during declaration.

***Difference between parameters and arguments:***
const arg1 = true;
const arg2 = false;

function twoParams(param1, param2) {
 // function statements
}
twoParams(arg1, arg2);


------

<!-- NOTE: option + cmd + j to quick open dev tools on google! -->