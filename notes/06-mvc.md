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



---------

Notes 8/22:

Note: after you create your controller, we have to define our view in the router. In this case, we added GachamonsController to path ''

he has this order in tabs: index -> router -> controller -> appstate -> class

NOTE: when the page loads, it looks at the browser's URL and matches it with a PATH< then loads the corresponding CONTROLLERS, and injects the VIEW into the index.html router-view

NOTE: controller constructors run when a view page is loaded:
* this is something that I missed yesterday. Have to call our function that we create in our class that's in our controller


In our service:

* we export an instance of the service, instead of a definition of the class so another one cannot be created, or redefined.

In this instance, we are passing the data from the click into our service call.

Can put a comment that our IDE reads: /** @type (Gachamon) */

activeGachamon = null

It's telling us that activeGachamon is GOING to be of type Gachamon, even though it is null when it's defined

Appstate.on('activeGachamon', this.drawActiveGachamon)

above statement is saying listen to when activeGachamon is activated, call this.drawActiveGachamon, which will call the draw function for whatever the name of the gachamon is

* part of the constructors job is to 
* this type of statement is a listener statement, it's listening for when activeGachamon is called

role="button" notifies the browser that your div or whatever is a button, even if it's not a button tag

cmd + . to create a method in your service you are referencing from another file. If you are referencing something that doesn't exist, you can usually use this method.

AppState.myGochamon.push(randomGochamon) <- pushing a new gochamon into our array of gochamons

AppState.emit('myGachamons') <- this forces the listener for the property to the trigger



-------------

Notes 8/23:

In this current project, we use the #/about in ur router view in order to display some text.

Anything inside of a class is considered a member. Anything outside that references the class makes it private

* An industry standard to indicate a function is private is something like this: _drawCars()

* underscore this indicated that the function is private


When a function is declared outside of the class, we don't use the "this" syntax.

in view, if you put /*html*/, it will look like HTML as far as the color structure looks (still won't be able to use intellisense)

so how Sam puts the draw function on the page is by using setHTML('id', content) sort of thing. This is setting an id in our router, and calling the id and setting the template created in our controller.

Our template that is pulled from are controller that is linked to our get template in our model, is being called by id in our router

NOTE: got to bootstrap docs for their forms section to refer to for building forms.

BS Collapse: it's basically like a button that you click that hides or unhides a form.

floating labels are cool too, look into this.

***NOTE NOTE::: hold shift and arrow forward or backward to highlight things with your cursor. This is super useful when being used with cmd + d to highlight multiple things to change text.***

***NOTE: remember that you can drag a file next to another file in VScode so you can see them both at the same time. This is super useful for comparison fo shooooo***

ignore shortcut: cmd + i while hovering on some error or squiggly to get rid of it.

- have to add our name attributes in our html for out form in order to get our syntax that we have put in to work for submission.

putting required in our input tag makes the field have to be filled out before the form can be submitted


When you want to start using local storage, 

save and load utilities are doing get and set/ parse and stringify stuff for us under the hood.

NOTE: I think if you for example create a function in the controller that is going to call something in the service, but you don't have the function created yet in the service, you can cmd + click the function in controller and it will create it in your service.

"Pop" in our library, it's like a popup double checking if you want to delete something

- on this popup, we label the function as async, and we put await in our if statement, so that it waits for the user to confirm before actually deleting.




----

NOTES 8/24:

selectable class, changes your cursor and makes a highlight on the tag

this.ComputeReportedDateView, grabbing this from a getter function, does not use the parenthesis when called, because we are just using the return value of this getter function, not actually calling the function itself

get ComputeReportedDateView(){
  return something
}

* getters are methods pretending to be properties.

