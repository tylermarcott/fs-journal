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



Key value pair:

when we create a query in the url,

  key         value
?planet = Water Planet

can also do the following for multiple searches:

?color=black&color=yellow

can use embedding in schema

{
  name: "blank",
  age: 24,
  address: {
    street: "blank rd.",
    city: Compton
  }
}       ^^^ embedded object

* in 1-to-1 relationship, embedding is preferred way to model the relationship


1-to-many relationship:

In this example, we have the blog which is 1, and comments which is many.

Embedding:

{
  title: "An awesome blog",
  url: "http://awesomeblog.com",
  text: "This is an awesome blog we have just started",
  comments: [{
    name: "Peter Critic",
    created_on: ISODate("2014-01-01T10:01:22Z"),
    comment: "Awesome blog post"
  }, {
    name: "John Page",
    created_on: ISODate("2014-01-01T11:01:22Z"),
    comment: "Not so awesome blog"
  }]
}

* this causes issues because the document can grow too large
* write performance issues

IMPORTANT
It’s important to note that this only matters for high write traffic and might not be a problem for smaller applications. What might not be acceptable for a high write volume application might be tolerable for an application with low write load.

Linking:

{
  _id: 1,
  title: "An awesome blog",
  url: "http://awesomeblog.com",
  text: "This is an awesome blog we have just started"
}


{
  blog_entry_id: 1,
  name: "Peter Critic",
  created_on: ISODate("2014-01-01T10:01:22Z"),
  comment: "Awesome blog post"
}
{
  blog_entry_id: 1,
  name: "John Page",
  created_on: ISODate("2014-01-01T11:01:22Z"),
  comment: "Not so awesome blog"
}

* benefit is additional comments will not grow, less likely that comments will run into max doc size of 16MB

* downside is if lots of comments, have to read all of those comments



Bucketing:

The third approach is a hybrid of the two above. Basically, it tries to balance the rigidity of the embedding strategy with the flexibility of the linking strategy.

{
  _id: 1,
  title: "An awesome blog",
  url: "http://awesomeblog.com",
  text: "This is an awesome blog we have just started"
}

{
  blog_entry_id: 1,
  page: 1,
  count: 50,
  comments: [{
    name: "Peter Critic",
    created_on: ISODate("2014-01-01T10:01:22Z"),
    comment: "Awesome blog post"
  }, ...]
}
{
  blog_entry_id: 1,
  page: 2,
  count: 1,
  comments: [{
    name: "John Page",
    created_on: ISODate("2014-01-01T11:01:22Z"),
    comment: "Not so awesome blog"
  }]
}

* The main benefit of using buckets in this case is that we can perform a single read to fetch 50 comments at a time, allowing for efficient pagination.



Many-to-Many relationship:

An author might have authored multiple books (1:N).
A book might have multiple authors (1:M).


embedding:


{
  _id: 1,
  name: "Peter Standford",
  books: [1, 2]
}
{
  _id: 2,
  name: "Georg Peterson",
  books: [2]
}

{
  _id: 1,
  title: "A tale of two people",
  categories: ["drama"],
  authors: [1, 2]
}
{
  _id: 2,
  title: "A tale of two space ships",
  categories: ["scifi"],
  authors: [1]
}





TIMEBOXING: seems useful!









-------------

Notes 9/7:

once opening a mvc-express project, go to workspace and hit open workspace. This will allow you to open client and server/ run them.

* in .env folder, fill out the bottom 3 tokens with the ones you got from auth0, they will be in slack.

* also have to do this in env.js in our client, copy paste the same tokens for domain, audience and client id

* don't forget your connection string!!!

start your server, add all of this, then make sure your server runs

after this, open the client and attempt to login

* out of the gate we should have these 3 things in the network tab: token, userinfo and account


Can delete the value folders in our project to make things less messy, but make sure you delete all references to those files or it will cause you issues.

in our virtual, have to set jusOne: true, so we don't get an array of 1 item back, justOne will turn this item into an object for simplicity

reporterId: don't want to trust ownership id from the client
* code like you are being attacked
* someone could misuse this ID

jwt.io <--- reads tokens

We have to use middleware
* .use()

^^^ we put this above our post put etc, it will run before these.

* we use next to get out of .use

we can make the middleware however we want, but we are going to use a provided one.

.use(Auth0Provider.getAuthorizedUserInfo)

^^^ this will attach the users token to the submitted data.

go to token --> preview, copy the access token. In postman, there is an auth tag, you can paste your bearer token in here. If in a collection, you can go to auth in the collection itself and put in the bearer token.

* postman will be acting on the behalf of the single user that is logged in. If you want postman to act as a different user, we will have to move the tokens around.

this attaches the user info to the request.

if we put our middleware for our authprovider below our get, it will allow the content to be displayed as an example before the user is actually logged in, in order to potentially attract new users!

can set postman get request to inherit auth or no auth.

in bird get, you can change the path variables. Ex, put the birds id in the path and keep birdId in the url instead? kind of the same thing as just changing the bird id lol.

NOTE: syntax in our populate .populate('-email') <--- this takes the email out of the data so other users can't see it.


we want to make sure we have a check that checks if the user making the request is the same as the birdwatchers account id who created the watched bird.
* do this in an if statement, put a throw new Forbidden() so it pops a 403 unauthorized.




create a .env file on our server, and add all the info that goes for the project


npm i

^^^ run this in your server to install dependencies

a good first step is to login with your project and see if everything works, check network tab and make sure you are getting 200s

Jeremy copied an object when we did a console log to display the objects pulled from our server. He then used this object to create our model.

pojo = plain old javascript object



***NOTE: click on line and cmd + x to delete whole line***

when in doubt on what you have to put for a url in your front end, check your urls in postman!




----------

AJ Presentation notes:


notes on animations:

animation: fadeIn 2s ease-in-out 2s forwards;

opacity: 0;


when creating an animation, have to use: 

@keyframes nameOfAnimationHere{
0%{
  opacity: 0;
}
100%{
  opacity: 1;
  pointer-events: none;   <--- makes the button unclickable after it dissapears
}

}



.animate{
  animation: slideIn 1s ease-in-out 1s forwards;
}

@keyframes slideIn{
  0%{
    transform: tanslateX(-100%)  <--- pulls the button from the left side of the screen. 100% wil make it from the right side
  }
  100%{
    transform: translateX(0)
  }
}


overflow-x: hidden;   <--- has to be on the parent, be careful using this, but it will take away side scroll in some situations.

^^^^
prevents overflow on x axis




background-repeat: no-repeat; <-- makes it so you don't get a bunch of boxes of images if the image is smaller on the background image you are setting


filter: blur(1em)   <--- blurs an object, don't need to make it too huge.

perspective skews the perspective of the element you are using

animatebackgrounds.me   <----

^^^^ when you're on this site, there's a bunch of free animation backgrounds. If you want to see how an animation is working, use dev tools inspect element and find what's doing something that you want.



if you start typing out animation and type ani, it will give you sort of a preset on how to set up stuff with animations.



NOTE: have to run npm i when you clone down a project or it will give you an issue with your .env