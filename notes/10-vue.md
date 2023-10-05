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





---------


Notes 9/14:

bs5-modal-default  <---- modal

<slot></slot> tag <--- using these slots to insert data on a different component





------------

FULL STACK REVIEW:

postman tests

USE express.vue    <---- this is what we need to use fo our checkpoint

open workspace <--- go to workspace file and you will get a button

We are responsible for front AND backend now, so we have to use our own ENV credentials now. Find these in slack to yourself.

next, start client and server


tests in postman



lowercase: true; <--- in an enum, makes it so the string that is taken in is always lowercase.

toJSON: {virtuals: true} <-- allows us to create virtuals on the given object



in variables, put in you auth token <---- get this from our token in our console -->> network --> token

* put it in both hit save (on auth, not evil_auth)

can open console bottom left corner of postman to see errors and such



***can drop down to test results to see which of the tests it passes or fails



any time you use a find, have to tag on .populate() at the end.



'/:something'   <----- req.params.something e.g. for findById


soft delete: kind of like an archive, where you aren't actually deleting something, but you still have it in the DB


runs a function from the albumService in picturesService just to verify if we have a proper album id or not.

***NOTE: services can call to other services!

cannot have a controller talk to another controller though.

<AlbumCard :album="a"/>
            ^^^^--- this is how we pass our props.

*** remember, you can have nested css classes!!



can expand our computed to make it multiple lines and put in if/ else statements

bs5-modal-default


use <slot name="body">  <--- or something similar to pass in ids so we can put unique bits of information in here


we can open up a component and start defining what goes in the slots we created in the component

<ModalWrapper>
<template #body>      <---- we target the body slot we made in the component here to pass info to it.
    something here
</template>

</ModalWrapper>


****const albumData = ref({})  <---- add v-model on all form inputs, this captures the data and puts it into the ref so we can use it.

option in form <---- good if you have an enum value in your data, it will allow you to choose from different values in your enum

option animals
option pugs
options games

etc etc...


we can see in vue console our object changing as we input data into our form!


can add imported photo preview, see syntax in Mick's code. Nice touch!


v-if="user.isAuthenticated" <--- way to hide buttons if users are not logged in



when we use const route = useRoute(), then pass route.params.albumId to a fxn, our app knows what albumId is because we specify it when we include it in our router.


*** mapping is for arrays of things, not a single object.


width: 100% <--- if the object is in a col-3 or something like that, it will make the width the size of the column
aspect ratio: 1/1 <--- css styling to make an object squared



masonry format <--- like grids

<div class="masonry-container">

remember to remove .js if you still have this on.


$gap: 0.25 em <---- this is a variable in css

collabBody.accountId = req.userInfo.id <--- grabbing id from info on .use(Auth0Provider. whatever)



{accountId: userId} <-- key: value pair. comparing userId to accountId. Use case for changing userId into something a class with accountId can use



foreignField is what you are looking at on the other document,
localField is what you are looking at on the document where the virtual is being created.



NOTE: in AuthService.js  <--- we want to wait accountService.getMyCollaboration()

* this makes sure we wait for the user to be logged in before the collaborations are fetched. Can't use the normal way to do this because we will get a 401 error



props: {album: {type: Album || Object, required: true}} <---- quick fix



watchEffect instead of onMount <---- gets everything WHENEVER the route changes. We were having an issue on create wasn't taking us to the newly created album





BEFORE OYU START PROJECT: in Postman: tower ---> variables ---> log in to 2 accounts and get the auth tokens from them


^^^^ ------- for postman, go in the order of these tests. Also, don't just got and do all of the postman tests immediately. Can do some, go do some front end, and come back.




tower event is going to work like the archive of an album, except it's a cancelled event






FINAL CHECKS FOR TOWERS CHECKPOINT:

- The EventDetails page displays all event properties, the comments for that event, and images/ names of all ticket holders ✅

- Comments show their authors name and image ✅

- Events can have comments added and removed on the EventDetails page ✅

- UI prevents users from joining an event (create ticket) if an event is canceled or does not have the available capacity remaining ✅

- User can choose to 'attend' an event, creating a relationship (ticket) between user and event ✅

- UI prevents user from creating multiple tickets for an event ✅

- Users can see all the events they are attending (have tickets to) ✅

- Users can delete their ticket for an event ✅

- API passes all Postman Tests (NOTE: passed all before, have 1 that doesn't work now, go back and retest) ✅

- Application UI adheres to Minimum release standards and web UI standard of the BCW design doc







TESTING MINI LECTURE 10/4  

can create a test with pm.test()



Vue-tour:

cd into client folder

npm install vue3-tour

import Vue3Tour from "vue3-tour"
import 'vue3-tour/dist/vue3-tour.css'

.use(Vue3Tour)

note, she is doing this in main.js (HAS to be done in main.js because the tour needs to happen when app is instantiated)



<v-tour></v-tour> tag

in return, :

steps:[
    {
        head:{title:'Hey hey look at this!'},
        content: 'Here is our super cool step component',
        actions:{next: '<button>What does this look like?</button>'},
    }
],


<v-tour name="myTour": steps="steps">


^^^ this won't work yet, need to select an element that we want the popup to happen on.


<section id="v-step-0">


Add target to our steps:

steps:[
    {
        target: '#v-step-0'
        head:{title:'Hey hey look at this!'},
        content: 'Here is our super cool step component',
        actions:{next: '<button>What does this look like?</button>'},
    }
],


inside script tag but outside of setup, create this:

saying: when this component mounts, start my tour



mounted: function(){
    this.$tours['myTour'].start()
}


add params:


steps:[
    {
        target: '#v-step-0'
        head:{title:'Hey hey look at this!'},
        content: 'Here is our super cool step component',
        actions:{next: '<button>What does this look like?</button>'},
        params: {placement: 'top'}
    }
],


add another id, this one can be on something else:

<section id="v-step-1">


add another step:

steps:[
    {
        target: '#v-step-0'
        head:{title:'Hey hey look at this!'},
        content: 'Here is our super cool step component',
        actions:{next: '<button>What does this look like?</button>'},
        params: {placement: 'top'}
    },
    {
        target = '#v-step-1',
        header{title: 'View an Album'},
        content: "Click on a card to view its details"
    }
],



add a callback right below steps:


tourCallbacks:{
    onFinish: (()=> {
        router.push({name: 'Album Details', params: {albumId: Appstate.albums[0].id}})       <--- make sure this is registered router link
    })
}



make sure to add const router = userRouter()

make sure to add callbacks to our tag that is calling it I think?

:callbacks="callbacks" <---  I think this goes in that section?


add our v-tour in a new component


<v-tour :steps="steps" :callbacks="callbacks">




props: {
    steps: {type: Array, required: true},
    callbacks: {type: Object}
}


call under setup:

mounted: function(){
    this.$tours['myTour'].start()
}

put id="v-step-2"  on whatever tag you want it to appear at.

so basically you can just keep adding steps, as many as you want


make sure to pass props on tour tag.


We don't want our tours to happen every single time, so we are going to fix this.
Going to add a boolean on account model something like needsTour

needsTour: {type: Boolean, default: true} <--- server side

already have a method we can use in account service front end, but we have to make it in the controller



updateAccount(req, res, next){
    try{
        const account = await accountService.updateAccount(req.userInfo, req.body)
        return res.send(account)
    }
}



add edit in account service in client:


async editAccount(){
    const res = await api.put('account', body)
    logger.log([UPDATING ACCOUNT])
}



tourCallBacks: {
    onFinish(()=> {
        //NOTE: flip the bool on the account to false, send a put request to the server to update
        await accountsService.editAccount({needsTour: false})
    })
}


pass :callbacks="tourCallbacks" on our <v-tour tag

<v-tour :steps="steps" :callbacks="tourCallBacks">



save in appstate now. Want to say if needsTour is false, don't even render the tour

this.needsTour = data.needsTour in front end model for account

AppState.account = new Account(res.data) <---- add this syntax to editAccount fxn on front end



add to v-tour on home page, v-if="account.needsTour" <--- only render if this is true


compute our accounts as well so we can read from appstate

add our own tour tag


<Tour v-if="account.needsTour" etc... <--- changes the hierarchy. If we use the v-tour tag like we have above, it will not work



onSkip: (async()=> {
    await accountService.editAccount({needsTour: false})
})

^^^ this makes it so onskip, it skips the tutorial. Say if you are making a new account but don't want the tour.



in sanitizeBody() function in accountsService:

add needsTour: body.needsTour   <---- have to add this after body is sanitized, because if you don't do this, this function gets rid of this value.








