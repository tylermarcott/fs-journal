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


