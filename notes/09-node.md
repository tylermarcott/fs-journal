# Node

NOTES SEP 5:

Bulk of our code this week will happen in side the code folder

Don't confuse server router with the router that changes pages.

Acting as a middle man between the client who is requesting the data, and the database itself.

On run and debug menu on VS code, we will see 'Start Serve' at the top of the page. This will run our server.

A super constructor tells the base controller to also run.

* export class CatsController extends BaseController{

    constructor(){
      super('api/cats') //NOTE: super calls the constructor of the BaseController
      
      this.router //talking about the small hallway off the big hallway (baseController router)

      .get('', ()=> this.getCats)
  }

  //NOTE: request, is an object representing the incoming request from a user
  //NOTE: response, is an object for you to manipulate and use to send responses to requester
  //NOTE: next, is how we kick people back to the hallway

  getCats(request, response, next){
    logger.log(request)   //logger prevents message from being eaten like console.log does. Logger elevates the console to a layer that reaches your debug console, and only console logs when in a dev environment
    response.send('you got cats') //the response is like 200 OK, the send is what we are giving back as the body to the requester
  }

}

//NOTE: debugger start/stop with server running, if you want your changes to take place, either stop and start, or restart the server with this widget tool.

* will find server console logs in the debug console on VS code

//NOTE: we write out the service file the same way we usually do.





here's what I need to put in .env under connection string:

mongodb+srv://tylerjmarcott:<password>@cluster0.ytvgbzj.mongodb.net/?retryWrites=true&w=majority

password:

H0St1d6evZMrTULm




We create schemas instead of models for databases

* we have to register our schemas to use them. Have to register them in file 'DbContext.js'

request.body <---- body that user sent in their request

mongoose is a way for project to talk to the document based database (Mongo)

find() in mongoose land returns everything, where as in JS it just returns one thing. A little bit of confusing syntax lol.


http://localhost:3000/api/cats



--------


NOTES WED 9/6:

Lucid charts: good for building UML diagrams


start first thing by adding connection string in .env file

Make sure to register you schema in DbContext.js

In Postman, new collection, can create individual gets or puts or whatever you want tha act as like shortcuts to performing each of the tasks.

to post an object, select body, raw, JSON, then create your object with the following syntax: "name": "Rainforest Cabana"


const query = req.query



- grab the query that is coming in from  our url, pass the query into your service, so our service can take the query and pass it up to our database.

* get exhibits WILL work as a get all if you don't pass in an additional query in Postman.

* in postman get, she writes http://localhost:3000/api/exhibits?biome=tropical&name=Fijian+Tundra  <-- multiple query parameters

?biome=tropical&biome=desert <--- this syntax will give us all of our animals in the tropic AND desert biomes

  Note: maybe I should practice that package finder game to practice how to use queries a little better


**Can use break points by clicking on the left of the numbered rows in or code. Respin server, create a response/ request, then go back to your code and step through your code in the widget.


Virtual - allows us to populate some kind of additional property that is returned from the object in the database.

(toJSON: {virtuals: true}) <---- goes outside where we declare the schema


take exhibit id, reference collection, return me with that one object

AnimalSchema.virtual('exhibit', {
  localField: 'exhibitId',
  reference: 'Exhibit',
  foreignField: '_id',
  justOne: true
})

reference this in our getAnimals() in service with adding .populate('exhibit') at the end of our await dbContext

- note: should be able to do this on a separate line.

populate('exhibit', 'biome emoji') <--- grabs biome and emoji from exhibit object


one to many relationship: 


RESTful apis are just a best practice for naming conventions for an api

/: <--- passed value syntax

.get('/:exhibitId/animals') <--- get the id from a specific exhibit, and get the animals from that exhibit.

      ^^^ make sure to get rid of colon when you actually put the id in.


<!-- NOTE NOTE: cmd + shift + arrow to highlight the WHOLE long of code -->


start with galaxy first in the lab!

//NOTE: make sure to comment out line 22-27 on Startup.js




