# Single Page Applications with Vue
01. What is the entrypoint of an application?

  > main.js

02. What is the difference between a vue `component` and `page`?

  > a component is an individual module. Many components can exist on a single page. A page is a whole page with lots of things on it

03. What is ***Component-Based Architecture***?

  > Component based architecture focuses on encapsulation and reusability of code. Each component can exist within the same space, but they all interact independently. Also, CBA splits responsibilities vertically, whereas MVC splits them horizontally

04. What are the three tags that make up a Vue component?

  > template, script, style

05. What are ***lifecycle hooks***? What are lifecycle hooks used for?

  > They are a window into how the library you're using works behind the scenes. They allow you to know when a component is created, added to the DOM, updated or destroyed.

06. Which component in Vue does the vue-router use to mount pages onto?

  > the router view

07. What is the difference between the `AppState` and the state object within a component?

  > The state lives within the component, the AppState does not

08. What is the responsibility of `Services` in our Vue projects?

  > dealing with data in apis, models and the appstate, similar to how it was in MVC

09. What are ***props*** and how are they used? Provide an example

  > Props are how we pass variables and other information around between different components in Vue. From what I can see, props have to be exported at the top of the page. They are defined in this export default, where the information is included. In the example in the readings, we have the name, image and rating of a type of camera.

10. What is the Vue method used to create watchable objects such as `state` or `AppState`?

  > compute()
