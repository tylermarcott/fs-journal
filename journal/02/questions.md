# Intro to JavaScript
01. Which keywords are used to declare a variable in JavaScript?

    > var, let and const

02. What is the definition of a function?

    > A function is a subprogram designed to perform a particular task.

03. What are the `SOLID` principles?

    > Single responsibility, open-closed, liskov substitution, interface segregation and dependency inversion

04. Given this array: How could you remove the `pineapple`?

    ```js
    let fruit = ['apple', 'banana', 'pineapple', 'orange', 'strawberry']
    ```

    > I did a little research, and it looks like the easiest way is to use .filter(). Syntax below:

    let removeItem = 'pineapple'

    let alteredFruit = fruit.filter(remove => remove == removeItem)

05. Given these two objects: How could you add each to the others friends arrays?

    ```js
    let you = {
        name: "You",
        hair: true,
        friends: []
    }
    let them = {
        name: "Them",
        hair: false,
        friends: []
    }
    ```

    > Did a little research, and it looks like we can use the .push() syntax to accomplish this. Code below:

    let addYouToThem = you.friends

    let addThemToYou = them.friends

    addYouToThem.push(you)

    addThemToYou.push(them)

06. Give an example of a JavaScript `Conditional`:

    > An example of a JS conditional would be an if/ if else statement

07. What is the main difference between `parameters` and `arguments`?

    > parameters are values passed to a function, where arguments declared or used to pass values into a function call

08. Instead of writing everything to the console, what is a better way to debug your code?

    > use the devtools debugger and step through your code in your browser devtools

09. What is the difference between a `primitive` value and a `reference` value?

    > primitive data types are data types such as a number, string, bool value etc. Reference data types are data types such as objects and arrays, that can be highly manipulated and store other sets of data within them.

10. Demonstrate a loop that prints the numbers between -100 and 100?

    > for(let i = -100; i <= 100; i++){
        console.log(i)
    }
