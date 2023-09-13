# Vue

Readings notes:

Vue props:
* props are how we pass variables and other information between different components.

    - props are passed down the component tree to descendants
    - Props are read-only and cannot be modified

View uses a one way data flow; it can only flow from a parent into a child component

shortcut for v-bind is just :


-------------------


Notes 9/11: 

package.json keeps track of all of our dependencies, or things that we use in our code; plugins etc.

* when we do an npm i, it will install all of these dependencies

main.js <--- entrypoint to our application

a component is a controller and a view squished into one file.

^^^ single file components as opposed to multi-file components.



@click <--- this means an event is being fired. @click is short for v-bind: click

router-link :to="{ name: 'Account'}" <----- takes us to the Account page



rule of thumb is about 150 lines of code. If you are doing more than that in 1 file, it is too much. After around 150 lines of code, more abstraction is needed


NO MORE DRAW FUNCTIONS WITH VIEW FUCK YAH

* vue makes sure that when data changes, the view changes

* we do this by doing computed() in vue

 - data driven apps: if the data changes, we always need to make sure the view is in sync

 code snippet 'vt' <--- gives us a little template for vue



App.vue contains the header, main and footer inside of it. Inside the main we have the router view



if you want to use something from your script in your template, you have to return it.


using @click instead of onclick now



Creating reactive things in view.

* import ref from view, this makes something reactive


In your template, when you double bind something, you want to put the value on the screen?


Property "law" was accessed during render but is not defined on instance

* this error will be caused because you are trying to call something in your template that does not exist in your javascript.



a computed is a get


const health = computed(() => Appstate.health)   <---- drill into appstate and grab our health.



cmd + spacebar will do auto imports on things that need imports.



<FoodItem v-for="item in foodItems" />   <---- acts kind of like a for each in vue. This is just a template

in Vue, we call parameters/ arguments 'props' aka properties


our prop will be the singular item we are passing in.

{{}}   <---- this is a binding


fork vue-playground

run npm i




----------------------


Notes Sep 12th:

VUE Lifecycle hooks:

* onMounted() // when component is 'mounted' to the DOM
* onUpdated() // when component data is updated
* onUnmounted()  // when component is 'unmounted' from the DOM (removed)

^^^ can run specific functions at specific times by triggering these

if you need your code to run your function, have it outside your return. If you need the USER to run it, it has to be INSIDE the return

* this can also be both. You can define a function outside the return and add the definition inside the return


use a colon in our reactive appstate instead of an =

* movies : []

REVIEW: something has to be an array to use map method.


remember: {{ }} <----- interpolate data into html



NOTE: binding data inside tags uses :     binding tags in BETWEEN tags uses {{ }}


calling our tag template with whatever the vue file name is called

props: {movie: {type: Movie, required: true}} // this sets up component to take IN data from a parent component

        ^name   ^type


<MovieCard :movie="m">


bs5-modal-default <--- quick snippets for modal


data.genres?.map(g => g.name)   <---- if there is a genre that is defined, map it. Prevents undefined objects from being mapped.

.prevent works the same as event.preventDefault()

two way data binding: code changes page, and page can change code



NOTE: overflow-y: scroll   <-- makes it so overflow scrolls instead of making the page larger, say if it's on a card or something




check Sam's example for pagination on changing pages for checkpoint





--------


Notes 9/13:

we have components that are in a different folder and we call them pages, that's all it is.


to: home and to: about match the page ids, takes us to the given pages

router.push({name: 'Cars'}) <---- takes us to a new page, through the code itself. This is good for automatically navigating the user when certain code process are done

<router-link>  <--- should be used whenever clicking something should take you to a new page


^^ generally, you should work with router links


Note: remember, we can always start with a data dump on the page just to test if our get is working how it should.

***Remember, you can refer to Savannah's example she wrote out for you in your homepage I believe, in the gift view lab**

need your prop to pass data from the page to each individual component

* make sure to give your component tag an id <--- have to data bind this: eg

<CarCard :car="car"/>   <--- giving data for each iteration of the for loop



overflow: hidden; <---- cheating

g-3 <--- gap 3  <--- adds margin and padding to the columns, only works if your content is in a car in a box, creates more equal spacing between items

 putting router link around our whole card

 
can set up route parameter in our router, such as '/cars/:carId' <--- carId is just a placeholder for whatever we type here


can put params in router-link as well. Router links to pages with params, need the params filled out or you will get an error when the link tries to load. eg: 

useRoute() <---- the route is where you are in context of the app, your url

can grab the car ID out of the params in our route

const route = useRoute()


const cardId = route.params.carId <--- gives us the car Id that is in our url



** if something is not in your return, it can not be accessed in your html




for form creation in vue, use a ref set to an empty object in our setup, and v-model on all of our submissions. This will create an object that is populated with the data that is filled out in the form

* const carData = ref({})   <--- this is in our setup

remember push is needed to put the data back in our appstate after doing a post, so we can update the data on our local machine, not just in the api.



put our await carService in a const newCar, this will capture the value of the return in the service function, which in this case will be the id of the car that is created when retrieving the car from the api. We can then use this api to know where to route the user to once the create the car, pushes the user to the details of the new car they created instead of just taking them to the bottom of the list

^^^^ use a router.push

make sure to clone gregslist and run npm i!