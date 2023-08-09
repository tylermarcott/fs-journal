# Git

Monday 8/7

To commit changes from VScode:

- Write a message, hit commit, and save changes. This will upload your commit to GitHub

To open command pallet, cmd + shift + p
  - allows you to open the search bar to interact with extensions and all that good stuff, like adding pets hehe


---

Tuesday 8/8:

How to produce generic boilerplate for Html:
- ! and tab

Difference between stuff like body, main, section doesn't make any difference, just a way to label stuff and make sense of it.

Always have to link style sheet to HTML, put css name in href

Drag files to create left and right view in VScode

--

In inspect, you will see something in style like style.css:1. This will indicate that the style is coming from file style.css on line one

--

Header goes at top, footer goes at bottom

.d-flex usually indicates a css rule with one property I think? d.flex orients things left and right. It makes boxes a column not a row. Type out display: flex;

Can add same property to 2 different rules like so:

.d-flex, 

row {
  
}

--

Holding option and clicking will allow you to create multiple cursors to place on the screen in VScode

--

On element inspect in the browser, extra space in flex would be displayed by a bright purple or green on inspection of a box or something like that.

Can turn commented out styles on and off with checkbox in inspect element

Box next to display flex, looks like 6 little boxes, allows you to change styling temporary to help with design

***Justify-content is used for spacing selections

--

a tab, this will create an anchor tag, which creates a link, something you can click on that's kinda highlighted on the page

an alt is something that displays if the image doesn't load for some reason

When working on a webpage, just create the basic layout, then come back to it later with creating specifics

--

padding creates whitespace on the inside of your element, margin creates whitespace on the outside of your element. Margin for moving things away from each-other, padding for filling up space inside the box

To fix stretching of images because of d-flex, out your image in another tag, like section

align-items: center; effects height property, puts elements in the middle vertically, height property

--

To change size of imported images, add a class to the img tag and make a property in css, adjust width and height. If the image is in a container, it will adjust it relative to what container it's in, not relative to the page itself

padding: 2em 1em; applies padding to top/bottom and left/right (in that order). One em value applies to all sides

--

Create variables in CSS using:


root {

  --dark: color etc..
}

Then use var(--dark) instead of choosing individual colors for everything

--

Can drag and change colors on inspect with any element, to mess around and see what colors work the best

***In body, put margin: 0; to get rid of pre-built in margin on browser

Font Awesome, MDI (material design icons) to add icons to the page. To get these icons from mdi, type in mdi, which creates a link to the stylesheet for mdi

  - on MDI, it will give you a code snippet to add in to your code to create the icon
  - link.mdi:i code snippet starts your cursor on the icon, and starting to type something out, seems to have many different icons and you can select from one. MDI intellisense extension adds the little icon into your actual HTML code for clarity
  - icons are displayed as fonts, so you can change the color of them, and alter them in any other way that you would alter a font. Can change, size, color etc.

To fix issues with switching site to different devices. These classes will be applied until the max width is reached
// media rule

@media (max-width: 600px){

    .d-flex{

      flex-direction: column;

    }
}


Can use Git Initialize button in VScode to automatically initialize your project 

