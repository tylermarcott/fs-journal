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



