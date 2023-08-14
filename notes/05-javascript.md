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