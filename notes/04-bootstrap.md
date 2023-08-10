# Bootstrap

Notes Wednesday 8/9:

Bootstrap Notes

Link b5 ABOVE link for style.css to link bootstrap to project. Take link from bootstrap and put it in link on project

**MAKE SURE STYLE.CSS LINK COMES ***AFTER*** BOOTSTRAP LINK

Note: control+shift+ ~ open terminal shortcut

Can find all of bootstrap files in source on inspect


body data-bs-theme="dark"
- this gives dark theme from BS, this theme and other themes are found in source

Use class="container" or class="container-fluid"

Make class rows "sections", and columns buttons, divs, p tags

- rows are display: flex by default

- rows broken up into 12 parts

  -rows have to exist inside a container

To create mobile responsiveness, you can create your columns over different segments, ex col12 col-md-6 col-lg-4

- you should always have a base col size with no infix, ex above is our col12

section.row is a shortcut to make a section with class row

.col-4 will make a div with a column of size 4

section.row.bg-primary tab will do something like this as well, just shortcuts

- can do *5 or something similar to multiple the number of shortcuts you make of the same type
- automatically a div if you do not specify

p-2 --> padding 2


fw-bold --> font weight bold

span is an inline element, creating classes inside a section of div or something like that

mdi + tab will create link for mdi icons I think?

then i + tab will make icon tag

BS has built in btn class that's good for using with buttons

***Have to apply justify-content to whatever is flexible or d-flex***

- a row automatically inludes d-flex

text-end will put text at the end (right) me thinks?

**NOTE: all bootstrap is documented on their site. The most important part to learn from this is rows and columns

offset-2 class: takes up 2/12 of our 12 row column to offset buttons or images or text

ms-3 class: margin start 3, gives us a little margin

ps-5 class: padding start 5, adds padding

can consider an image as a background, so that we can put content on top of it

pd-3 rounded: rounds boxessssssssss

justify contents goes horizontally, align items goes vertically

align-items-end moves box to bottom of container

background-image: paste image url from wherever you get the picture from, background photo

background-size: cover; lets the image just cover the page, sizes it properly

can lower opacity on background colors to put them on top of a background image

lorem comes up with random placeholder latin to fill out containers

pe-0: padding end 0, if you want end size padding to be zero and have the container be flush with the end of the page

img-fluid class: applies width 100% to image so it fits properly in your container
- could also put w-50, makes width 50%

Can add a STUB note that will mark what you need to add to your project/ description of work you need to do.

object-fit: contain; makes an image fit and not go any larger than the size of the container that it's in

Note: on the right sidebar on VScode, we have little dots that show where various anchors and notes are

py-5: adds padding 5 to top AND bottom

px-5: adds padding 5 to beginning and end

object-fit: cover; crops the image to the size given

g-5: allows you to add gap to your columns. Also has gx and gy

can use padding in the same way as col, can have it be mobile adjustable, so when the screen gets smaller, take padding away. It looks like you can do this with a lot of different classes.

in BS, you can reorder how your HTML is displayed in flex boxes

-have to put the order on column class

-order zero through 5

default order is our mobile screen


can put order 0-5, order 0 is first, order 5 is last and so on

- also have to put in a line where the order will change just like col-md-6 sex, md being medium screen line

to overwrite bootstrap, you can use customized classes and !important after the class


***ANOTHER BIG NOTE: JUSTIFY CONTENT ADJUSTS THINGS ON X AXIS, ALIGN ITEMS ADJUSTS THINGS ON THE Y AXIS

The frogs need to get in the same order as their lilypads using flex-direction. This CSS property defines the direction items are placed in the container, and accepts the following values:

row: Items are placed the same as the text direction.
row-reverse: Items are placed opposite to the text direction.
column: Items are placed top to bottom.
column-reverse: Items are placed bottom to top.

Use justify-content again to help these frogs get to their lilypads. Remember that this CSS property aligns items horizontally and accepts the following values:

flex-start: Items align to the left side of the container.
flex-end: Items align to the right side of the container.
center: Items align at the center of the container.
space-between: Items display with equal spacing between them.
space-around: Items display with equal spacing around them.

Now use align-items to help the frogs get to the bottom of the pond. This CSS property aligns items vertically and accepts the following values:

flex-start: Items align to the top of the container.
flex-end: Items align to the bottom of the container.
center: Items align at the vertical center of the container.
baseline: Items display at the baseline of the container.
stretch: Items are stretched to fit the container.

Sometimes reversing the row or column order of a container is not enough. In these cases, we can apply the order property to individual items. By default, items have a value of 0, but we can use this property to also set it to a positive or negative integer value (-2, -1, 0, 1, 2).

Use the order property to reorder the frogs according to their lilypads.

eg: order 2 on yellow will move yellow to the right

Another property you can apply to individual items is align-self. This property accepts the same values as align-items and its value for the specific item.

***code snippet to auto link BS: ----> link: b5***

****creating a site is all about, rows, columns and boxes!!!!!!********


Difference between container and container fluid


container will put a little bit of spacing and margin, VS container fluid will got all across the page without any margin

Mobile first design: design a web app first for mobile, then make it work for desktop, note the other way around. This is called mobile first design

- when building out columns, throw in some dummy text

BS breakpoints, check out this writeup to see page breakpoints used

**style:debug** snippet adds borders for laying out an app. Make sure to add to body. Just used for building

put comments in code to indicate sections. Can use SECTION anchor, this makes it easier to navigate HTML

Note: don't just have floating text inside a div. Always wrap it in a p, header, bold tag, something like that.

css-tricks.com: great resource for flex properties and whatnot, check it out, have a tab open for it lol

Very useful to use devtools on browser to mess with heights and stuff. Like on a card, add width: 50vh (view height) to make the section o card larger

- that's what I was trying to figure out about changing height. That's how you can change the size of various boxes on the app. Before I was using padding to change size. Can change width or height view height using the above syntax

bg: shortcut for BS background colors

Note: keyboard shortcut: cmd + d and up or down arrow allows you to highlight multiple items

Note: p tags inherantly has margin. If you don't want this margin, make a css custom class targetting all p tags with margin: 0;

***very important to be using devtools and highlight to figure out what is going on in our app**