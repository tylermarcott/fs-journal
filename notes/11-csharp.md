# CSharp

Day 1 C# notes:

We use this for our server language replacing node.

The new best practice is to declare everything strictly with data types.

ex: int y = 10;

float z = 4.5f;

double a = 5.55;

decimal b = 6.80912m;

string greeting = "hello"; <-- strings have to be instantiated with double quotes now

char g = 'g'; <--- single character

bool ok = true;

bool no = false;

Array<int>[3] = new Array<int>[3]{1,2,3}; <-- this might or might not be the right syntax lol

List<string> cats = new List<string>(){"Iron Man", "Georgie"}; <--- lists work exactly like arrays do in JS, unlike the Array above which is fixed and bad                  ^^ starting off our list with a few values inside of it.

cats.Add("Gopher");
cats.Add("Bean");
cats.Add("Garfield");
cats.Add("11");
Console.WriteLine(cats.Count);
string catsToRemove = cats.find(c => c == "11");
cats.Remove(catToRemove); <--- we name the item we want to remove and remove it.

cats.ForEach(c => {
  Console.WriteLine(c)
});

Console.WriteLine(cats.Count);

If you fix an error, the error remains until the program is re-compiled and the compiler can see that the problem is fixed.

The 'debug anyways' button will run the PREVIOUS version compile of your code that worked, not the current. 


A dictionary is a data type that takes in a key: value pair

Dictionary<string, int> codeWorksCats = new Dictionary<string, int>();
codeWorksCats.Add("Jeremy, 7");
codeWorksCars.Add("Sam", 1);
codeWorksCats.Add("Savannah", 3);


            |can have a dictionary with key as a list of strings that take in a string.
Dictionary<List<string>, string> actualCats = new Dictionary<List<string>, string>();
actualCats.Add(cats, "Jeremy's babies");
actualCats.Remove(cats);


//NOTE: Members are created with CAPITOL letters, variables and params are lowercase
* can use cmd + . on Cat class after declaring our string or values for our class, and intellisense will make our public for us.


namespace catRoundUp.Models;


class Cat{

  // this is essentially a constructor
  public Cat(string name, int age, string color){
    Name = name;
    Color = color;
    Age = age;
  }
}

//NOTE: list of our class Cat

List<Cat> catsTheMovie = new List<Cat>();





in bcw create, use dotnet-auth



model in C#: we need to define what our data is going to look like.

public class Cat{
  public int Id;
  public string Name;   <--- public says that this name can be used by anybody, set by anybody
  public string Color;
  public readonly int Age;   <--- anyone can see it, but you can't change it's value. Basically like a const that exists on an obj
  private bool Feisty;   <--- 

<!-- NOTE: remember, you can do cmd + . shortcut to add these to the public constructor. -->
  public Cat(int id, string name, string color, int age, bool feisty){
    Id = id;
    Name = name;
    Color = color;
    Age = age;
    Feisty = feisty;
  }
}




now we will make our controller.


<!-- NOTE: data decorators/attributes effect the next definition, making our class an API CONTROLLER with the route ".../api/cats" -->
[ApiController]
[Route("api/cats")]
public class CatsController : ControllerBase{


  private readonly CatsService catsService

  public CatsController(catsService cs){
    _catsService = cs;  <---- private things have an underscore on the front to notate they are private
  }



[HttpGet("test")] <--- how you can add onto the endpoint
public string GetTest(){
  return "hey it worked";
}


[HttpGet]
<!-- NOTE: an ActionResult is C# version of passing errors such as 401, 404, whatever else. -->
<!--  -->
public ActionResult<List<Cat>> GetCats(){
  try{
    List<Cat> cats = _catsService.getCats();
    return Ok(cats);
  } catch(Exception e){
    return BadRequest(e);
  }
}


}

go to debug section, Add config for server in dropdown, .NET core type

localhost:7045 <--- this is what dotnet defaults to.



create service:


CatsService.cs

public class CatsService{

  internal List<Cat> GetCats(){
    throw new NotImplementedException();
  }

}


in Globals.cs <--- can specify things for all of our files to be able to use.

ex: global using catRoundUp.Models;






next, call a repository in our service


using catRoundUp.Models;

namespace catRoundUp.Services;


public class CatsRepository _repo{

  public CatsService(CatsRepository repo){
    _repo = repo;
  }

  <!-- NOTE: internal means this can only be used in THIS project -->
  internal List<Cat> GetCats(){
    List<Cat> cats = _rep.....
  }
}





create file CatsRepository.cs

namespace catRoundUp.Repositories;

public class CatsRepository{

  private List<Cat> _FakeDb;

  public CatsRepository{
    _FakeDb = new List<Cat>();
    _FakeDb.Add.......



  }

  internal List<Cat> GetAllCats.....
}



we have to register our dependencies that our api is going to need in our Startup.cs file. In this case we have to add the following:

service.AddScoped<CatsService>();

        ^^^^^ AddScoped allows us to create a CatsService whenever one is required.

        if you don't do this, we will get a dependency injection error in localhost:7045

buttttt, CatsService has dependencies as well


also add:


<!-- NOTE: order DOES matter. Have to make sure you put CatsRepo below CatsService, since one is used inside the other. -->

services.AddScoped<CatsRepository>();

CatsRepository goes at the TOP of CatsService


//NOTE: refer to Mick's notes, I was not able to get all of his stuff that he changed on here lol.



void <---- when we have a function that is not actually returning a value.


remember: OVERLOADING methods: methods with the same name but different params.

can add a singleton in Startup instead of a scoped, which will solve the problem with our fake DB and having data come back lol.






-------------

NOTES ON MYSQL


use SELECT to choose different types of data from a table, such as name and description of a hotdog on hotdog table

ex: SELECT name, price FROM hotdogs WHERE 'hasKetchup' = true AND price < 6;

^^ this is saying exactly what it sounds like from our hotdog table, SQL is kind of nice because it kind of speaks in plain english

//NOTE: general practice is that any syntax that is brought in from SQL is CAPITALIZED, and anything we bring in is lowercase. See example above.

SELECT name, price FROM hotdogs WHERE description LIKE '%jalapeno%'; <--- percent signs are wildcard characters, means anything can come after it and anything can come before it.
   example: 'that is a spicy jalapeno yo' would still grab jalapeno, even though it is between other words.


SELECT name, price FROM hotdogs WHERE name LIKE '%mustard%' OR description LIKE '%mustard%';

SELECT name, price FROM hotdogs ORDER BY name;

SELECT name, price FROM hotdogs LIMIT 2 OFFSET 1; <--- gets limits to 2 items, skips the first position in the table.

order DOES matter in the way you put these. If you mix up the order, it will usually give us an error when we execute


go to MySQLTutorial.org for tips and tricks, especially if you need help with errors. Also gives you places to practice.



set up id in the following way in a CREATE TABLE

id INT AUTO_INCREMENT PRIMARY KEY,    <---- primary key will make it so our hotdogs are organized by this id
        ^^^^^ ---- auto increment makes it so an id is added to every hotdog that we create.


DELETE FROM hotdogs WHERE id = 1;

UPDATE hotdogs
SET price = 20
WHERE id = 1;



UPDATE hotdogs
set price = price /2
WHERE price > 5;

----------------------

***MYSQL info:

database: first-database-ever

credentials:

  username: sgroot

  password: NOBCayPeC+E06HYv

master endpoint: SG-Sandbox-7900-mysql-master.servers.mongodirector.com

***

-----------------------

go to appsettings.development, fill out connection string so our app can connect to the database.

^^^^^ Mick will slack this out to us to fill in, just change what he gives to us with the stuff above from your actual db.



//NOTE: shortcut to making a c# class. Right click on folder, click new C# class 

^^^^^ this can be done with controllers and a bunch of other stuff as well, we come with a bunch of pre-populated code.


new --->>> class --->>> CarsService

REMEMBER TO ADD DEPENDENCIES IN Startup.cs


in repository, write a string with SQL inside

string sql = @"



";


^^^^^ this syntax allows for us to have multiple lines in our string.



//NOTE: we can really just copy paste stuff from our db setup into our C# repo. If it works in the setup, it should work in the C# as well. This would be in our string sql


RIP GOBLIN-THRASHER

original.ImgUrl = updateData.ImgUrl ? updateData.ImgUrl : original.ImgUrl;

original.ImgUrl = updateData.ImgUrl ?? original.ImgUrl;

                                    ^----- null coalescence operator, does the same as a ternary, takes the non null





-------------

Doing Post-it now in C#:

appsettings.Development.json

^^^ this is our new version of .env

still have to fill out env.js in front end

//NOTE: make sure to change base URL to the correct port on env.js, should be an https://7045 something

if you want something to default to tree, put DEFAULT 0 <-- 0 being false


creatorId VARCHAR(255) NOT NULL
FOREIGN KEY (creatorId) REFERENCES accounts(id) <---- signifies this value is going to come from another table

//NOTE: when you see an error that says 'near', typically look at the line before it.



since we provide a default in our table, we don't need to include archived in our 'insert into' command



ON DELETE CASCADE  <---- in this case, if my account gets deleted, cascade that down to the next table

SELECT * FROM albums JOIN accounts; <---- selects everything from albums table and joins it to accounts table


SELECT * FROM albums;
SELECT * FROM albums JOIN accounts;



SELECT* FROM albums alb JOIN account act ON act.id = alb.creatorId;
                    ^^^ this is just aliasing out albums to alb, so we can perform the syntax above to make things a little more clear. Need to do this as syntax gets a little more complicated


* to create model:
 - can user the prop snippet to populate for c#!SECTION


  //NOTE: works backwards in C#: model ---> repository ------> service -----> controller


in repo, hover over _db and cmd + . to generate constructor, little shortcut. This works on any file actually lol


can add an instance of another model onto a model.

ex: on our Album model, can have a data type of type Account. This replaces virtuals lol


List<Album albums = _db.Query<Album, Account, album>(sql).ToList()


whenever we use async in C#, we must accompany it with 'task'



add [Authorize] above your [Http] thingy, says you must be authorized before making this request.



----------------------------------------------


NOTES OCT 12:


make sure to check out postman endpoints and use them your road map for where your CRUD route needs to go

services can talk to other services, but a service should never talk to a different kind of repository. Ex: picture service talking to album repo.


we have view models, which still point to where we need to go for many-to-many relationships.


WHERE collab.accountId = @accountId
                            ^^^^^ this is being pulled from the parameter.




Unable to copy file "obj/Debug/net6.0/AllspiceCheckpoint.pdb" to "bin/Debug/net6.0/AllspiceCheckpoint.pdb". The process cannot access the file '/Users/tylermarcott/source/codeworks/AllspiceCheckpoint/AllspiceCheckpoint/bin/Debug/net6.0/AllspiceCheckpoint.pdb' because it is being used by another process. [/Users/tylermarcott/source/codeworks/AllspiceCheckpoint/AllspiceCheckpoint/AllspiceCheckpoint.csproj]


^^^^ if having issues, in terminal type: killall dotnet

***NOTE: make sure to change variables to the right thing, endpoint and add auth variables

***NOTE: delete toString() syntax in test/ prerequest script if you are having the following issue in postman:

TypeError: Cannot read properties of undefined (reading 'toString')







-----------------------------------------------

NOTES 10/16:

instaCult

can change the class creation template so that it has a semi-colon after the namespace instead of the curly brackets, look up how to do this*********


NOTE: can use add parameter on readonly by right clicking, try to start using this!

MAKE SURE TO ADD YOUR SCOPES!!!!

public class Account : RepoItem<Tid>   <---- Tid allows us to take in the specific data type when we run into the problem of using this extended model on multiple other models, where one might have a string of type VARCHAR, and another might have type INT

Can extend models to hide certain things on a model, see example.


Error: Object reference not set to an isntance of an object <--- something was null but you drilled into it and treated it like an object


have to use userInfo?.Id  <---- this compensates for if it's null, won't give us an error



route middleware in router.js in client <---- beforeEnter: authGuard
 * this will create an issue, blocks non logged in users from accessing the page, will prompt them to log in first thing

^^^^^ another thing to use: authSettled <---- waits for the automatic login process before entering.

If getting errors from using this, just wait like 30-60sec if you refresh a ton or something lol.



forms review:



NOTES 10/17:

Making additional class extensions on Account, allows us to relate to accounts, but only get specific types of data, instead of getting ALL of the data from accounts back when you join an account to another model.

ex:

cultist extends profile. These are EXTENSIONS of a model.

public class Cultist: Profile{
  public int CultMemberId {get; set;} <---- this is an item that is added so we can add the cult member id in our repo.
  public int CultId {get; set;}
}


NOTE: could potentially have a dependency injection issue, just go an mess with the order of the scopes in startup. Kind of vague but Mick says that this is the solution.



when we want to send the cultId, we have to send it as an object. If we don't, we will get the error like 'unsupported media type'. The server doesn't know what a single number like '5' is

const cultMember = {cultId: route.params.cultId} <---- this gives is a key value so it knows what it's looking at.

NOTE: better to use user when it's something that can use both user and account to check same information. User is slightly quicker when loading page though.





NOTES 10/18:

interfaces: what we refer to as a contract, where we can define what we want a class to have

IRepository.cs

                              ⬇️ T is instance of whatever type we define
public interface IRepository<T, Tid>;
{
  List<T> Get();

  T GetById(Tid id);

  T Create(T newData);

  public int Update(T updateData);  <--- int for how many rows we are updating

  public int Delete(Tid id);
}

                                                                                  ⬇️ here we define T and Tid from interface
now, in one of our repos, we type: public class RestaurantRepository : IRepository<Restaurant, int>

now, command period use interface command, and it populates all the CRUD method methods in your repo.

we will break this interface if we take away one of the methods in our repository, but we can add as many additional functions as we want without breaking the contract. <------ this is just used to streamline creating our backend.

*** interfaces should never be responsible for actually instantiating things, so EG we can't put private readonly IDbConnection _db; into our interface


NOTE: when typing our IDbConnection readonly, cmd . and say create constructor as a little shortcut



SHORTCUT: return _repo.Create(restaurantData); <---- easier than doing the 2 line way lol.



original.Name = updateData.Name ?? original.Name;

^^^ this means set original.Name to updateData.Name. If that doesn't work, set original.Name to original.Name
get or another method firing off before accounts

NOTE; beforeEnter: authSettled <--- this goes in the router, see Sam's notes on how to do it. This will solve issue with 





NOTES 10/19:  


kits cats and mats




SELECT 
*
FROM reports

^^^ this means select all INFORMATION from reports

NOTE: we can take our sql syntax in our repo and try to run it in our dbSetup, in order to debug *****

^^^ might have to change a few things when doing this debug, such as changing the @parameter


LEFT JOIN <--- take this table and join another table onto it. Instead of JOIN, it is 'join 2 tables onto each other'

restaurants.*,
COUNT (reports.id) AS reportCount,
accounts.*

^^^ if we put the count AFTER accounts, the count as reportCount will be added to the accounts table instead of the restaurant table.



