# MVC

Design Patterns

new command from BCW:

 * bcw create 

 * choose: mvc

 * make a name for the project

 * initialize git repo

 ----

 A character ***class*** is a blueprint for what a character is(a data object), not a character itself
 * saying new Character is telling the IDE that we are creating a new instance of our character class

constructor() <-- special method that runs every time you make a class

key word: this
* this is a context for a class instance to look at itself

NOTE: shortcut. For whatever you want to import on your JS file, just type out the name of the class you want to import and hit tab!

* DOUBLE NOTE: for intellisense auto complete on above, the tab HAS to be open in VScode


Controllers are there to make it so the user only gets from your program what you want them to get, not everything. 

Mick uses 'this' to pull values from the inside of a character.js and use it in the class itself

'get' key word, special method that will take in no parameters and no arguments, and always returns something.
* getters are like computed properties, when you access them, they run "calculating" the value

REVIEW: order to build in (most of the time):

1: Build the model and properties (don't need an html template yet)

2: Create data using that model in the appstate

3: Create a controller, and have the controller, draw the data to the page (either with html templates or just string concat)

4: Add interactions to page elements

5: the rest of it......


--------

NOTE: Week 3 readings notes

a module refers a small unit of independent, reusable code

With ES6 modules, you can concatenate all scripts in one main script by marking some of them as exports, then other modules can import them.

foundations of OOP: encapsulation and message passing