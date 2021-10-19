---
title: HTML, CSS, JavaScript (Note Part1)
---

## React, Redux (Note Part2)
https://github.com/hanwenzhang123/frontend-note/blob/main/02-note/README.md

## Performance, Testing (Note Part3)
https://github.com/hanwenzhang123/frontend-note/blob/main/03-note/README.md

## Boilerplate Code (Note Part4)
https://github.com/hanwenzhang123/frontend-note/blob/main/04-note/README.md

## Table of Contents
- [HTTP](#http)
- [HTML](#html)
- [CSS](#css)
- [Sass](#sass)
- [JavaScript](#javascript)
- [ES6](#ES6)
- [This](#this)
- [JS Methods](#JS-Methods)
- [DOM Event](#DOM-event)

## HTTP

#### What is HTTP?
- HTTP stands for Hyper Text Transfer Protocol
- WWW World Wide Web is about communication between web clients (often browsers) and servers (often computers in the cloud)
- Communication between client computers and web servers is done by sending HTTP Requests and receiving HTTP Responses

#### HTTP Methods
- GET requests data from a specified resource
- POST send data to a server to create/update a resource - always contains a body
- PUT means "insert, replace if already exists", similar to POST, but same PUT request multiple times will always produce the same result
- HEAD is almost identical to GET, but without the response body.
- PATCH is making partial changes to an existing resource.
- DELETE deletes the specified resource.

#### HTTP response status codes
- Informational responses (100–199)
- Successful responses (200–299)
- Redirection messages (300–399)
- Client error responses (400–499)
- Server error responses (500–599)

#### HttpRequest & HttpResponse
- HttpRequest: HttpVersion, URL, content
- HttpResponse: HttpVersion, StatusCode, ReasonPhrase, content
- Browser - Internet - Server - Internet - Broswer

#### cookie, sessionStorage and localStorage
- `cookie` - primarily for server-side, stored data needs to be sent back to server, expiration can be set from either server-side or client-side when manually set, 4KB Max
- `sessionStorage` - client side, use when you need to store somthing temporary, will only be accessible while the window is open, expires when tab closes, 5MB Min
- `localStorage` - client side, store data on the client computer, save key/value pairs in web browser, store data with no expiration date, last until the user deletes it, 5MB Min

#### local storage
- let now = new Date() || new Date().getTime();
- let userData = JSON.parse(localStorage.getItem('storedData'))
- localStorage.setItem('key', 'value')
- localStorage.getItem('key')
- localStorage.removeItem('key')
- localStorage.clear()

Handle expiration of storage on the browser
- localStorage.setItem(key, JSON.stringify(item))

setWithExpiry and getWithExpiry
- setWithExpiry("myKey", inputSet.value, 5000)
- const value = getWithExpiry("myKey")
- valueDisplay.innerHTML = value

## HTML

#### What does a DOCTYPE do?
- when we have a doctype, it is an "information" to the browser about what document type to expect. 
- Not case-sensitive.

#### href & target in `<a>` tag.
- `_blank` (new tab) and `_self` (current tab)
- `<a href=“https://www.youtube.com/” target="_blank"></a>`

#### why using semantic tags?
- we want to know what does it exactly means in the HTML, we can know it directly by its name 
- `<div>` is too broad, we do not know what does it mean. 
- semantic elements carry accessibility by itself, proper reading
  
#### web a11y accessibility
- computer accessibility, for people with disability using screen reader 
- mac machine, window, 3rd party tool, it will read out the web contents for you
- you want to have your website good with accessibility features

#### div and span
- `<div>` - anything can be putting within a div, it is a block element
- `<span>` - like a div but only for inline container, which div is block level element

#### canvas
- `<canvas>` element is used to draw graphics on a web page.
- only a container for graphics. use JavaScript to actually draw the graphics.

#### Video and Audio Tag
- the text between the tags only appears when audio is not working
```html
<video width="320" height="240" controls>
  <source src="movie.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

<audio controls>
  <source src="horse.mp3" type="audio/mpeg">
  Your browser does not support the audio tag.
</audio>
```

#### SEO (Search engine optimization)
- the process of improving the quality and quantity of website traffic to a website or a web page from search engines.
- Publish Relevant, Authoritative Content. Update Your Content Regularly. 
- Metadata. Improve Title Tags. Use alt tags.

#### What is the `<meta>` tag in the head tag? Why do we need it?
- `<meta>` - metadata about an HTML document, is data (information) about data. 
- `<meta>` tags always go inside the `<head>` element, and are used to specify character set, page description, keywords, author, and viewport settings.
- `<meta>` is important for SEO (search engine optimization). we do not visually see any of the code in the browser, but the browser will analyze the information.

#### What is the `<iframe>` tag
- An inline frame is used to embed another document within the current HTML document.
- represents a nested browsing context, embedding another HTML page into the current one.

#### Difference between `<script>`, `<script async>` and `<script defer>`.
- `<script>` - HTML parsing is blocked, the script is fetched and executed immediately, HTML parsing resumes after the script is executed.
- `<script async>` - in parallel to HTML parsing and executed as soon as it is available (potentially before HTML parsing completes)
- `<script defer>` - in parallel to HTML parsing and executed when the page has finished parsing, ensuring that the HTML is fully parsed before executing. There's not much difference in putting a normal `<script>` at the end of `<body>`.

#### Web Workers
- HTML5 new feature
- we can off load some ccomputer heavy task to web work, they will execute in parallel
- give developers a way of instructing the browser to process large tasks in the background
- preventing the UI from freezing up
- for web content to run scripts in an isolated thread in the browser (background threads)

[[↑] Back to top](#table-of-contents)

## CSS

#### specificity
- !important - overrides any other declarations
- id selector `#`
- class selector `.`
- Type selectors `p`
- Universal selector `*`

#### px, em and rem
specify sizes or lengths of elements using various units of measure

- px: You get what you asked for. Pixels may be good at spacing and layout, but are not good fit for font-size.
- em: Relative to the parent element
- rem: Relative to the root element (HTML tag)

#### Three ways to insert CSS
- external CSS (better choice, a separate css file)
- internal CSS (putting css directly in the html page)
- inline CSS (not recommended)

#### The CSS Box Model
- margin, border, padding, content
- goes from outside to the inside

#### margin
- 4 value order: top right bottom left 
- 3 value order: top left&right bottom
- 2 value order: top&bottom left&right

#### what is margin collapse?
- Top and bottom margins collapse into a single margin when it comes in contact with one another
- take the greater value, only top and bottom margins!

#### box-sizing property
- `content-box`: using content as the basis, default, only care about your content
- `border-box`: using border as the basis, like when we put a padding

#### display
- 'block' - full width, force a line break
- 'inline' - just for inline, you can set margin and padding left-right, but not top-bottom, no width and height
- 'inline-block' - allow elements to sit to left & right, top & bottom margins and padding, height and width

#### position
- `static` - default, follow the flow
- `relative` - almost same as static, but you can change the position relatively to the docs (its normal position), can even overflow
- `absolute` - other elements render as this absolute element does not even exist, relative to the nearest positioned ancestor 
- `fixed` - fixed based on the doc and always stick to where it is
- `sticky` - combination of relative and relative stick to the position based on the users scroll position

#### Difference Between Relative and Absolute
- `position: relative` - starts from where the element would be in the normal document flow
- `position: absolute` - removed from the normal document flow, placed in an exact location where you tell it to go on the page, relative to the nearest positioned ancestor 

#### media queries
- for responsive design, change the styling once the size reaches a certain value
- <source srcset="img_smallflower.jpg" media="(max-width: 600px)">
```css
@media only screen and (max-width: 600px) {
  body {
    background-color: lightblue;
  }
}
```

#### combinators
- descendant selector (space) - all elements that are descendants of a specified element.
- child selector (>) - all elements that are the children of a specified element
- adjacent sibling selector (+) - immediate, an element that is directly after another specific element
- general sibling selector (~) - all elements that are next siblings of a specific element

#### pseudo-class
- class like specific state, this sentence is like when this happens, under what kind of condition
- `a:hover` - mouse over; `a:visited/:focus` - visited, mouse focused
- `:nth-child()` - pseudo-class, value like odd, even, a specific number etc

#### pseudo-element
- referring specific for that element
- `p::first-line/::last-letter`
- `::after/::before`
- capitalize first letter: `p:first-letter { text-transform:capitalize; }`

#### invisible from the page
- `display:none` - does not occupy space or consume clicks, hide the whole element and remove that from layout, gone from the DOM tree, disappear from UI
- `visibility:hidden` - occupies space, but does not consumes clicks, hides an element but take up the same space as before
- `opacity:0` - occupies space and consumes clicks, create transparency or fade effect

#### flexbox
- `display: flex`
- A flexible layout must have a parent element with the diplay property set to flex.
- direct child elements if the flexible container automatically becomes flexible items. 
- `flex-grow | flex-shrink | flex-basis`

#### center both vertically and horizontally using flexbox
- `display: flex`
- `justify-content: center` - horizontally or vertically depends on the main axis
- `align-items: center` - center in the middle

#### what is image sprite?
- a collection of images put into a single image -> (reduce requests)
- a way to reduce the number of HTTP requests made for image resources, by combining images in a single file
- A web page with many images can take a long time to load and generates multiple server requests, using image sprites will reduce the number of server requests

#### Cross Browser Compatibility
- The ability of a website, application or script to support various web browsers identically.
- For example, we can check if CSS animation features support equally under various web environments
- We can use CrossBrowserTesting for testing and check on Can I use website

[[↑] Back to top](#table-of-contents)

## Sass

#### What is Sass?
- CSS can get messy when the code gets large, Sass is an extension of CSS3 that does things CSS do not
- for exmple, adding nested rules, mixins, variables, selector inheritance, etc.
- Broswer reads CSS but Sass, we write Sass code to Sass file and compile the code to css code using npm or Watch Sass in VS Code.
- We link the regular CSS file in the HTML file; `<link ref:"stylesheet" href="./style.css">`

#### Syntax
- Sass syntax: no curly braces, no semicolons
- SCSS syntax: with curly braces, with semicolons
- `@import "./header";` - import the sub-scss in style.scss
- naming for the sub-file: _heaader.scss

#### Key Features for Sass
Full CSS3-compatible along with language extensions and useful functions, well-formatted, customizable output
- Variables: `$primaryBtm` for reusable values; `&:hover``&&:after` for psuedo
- Nesting: to nest selectors inside of one another, allowing us to write less code
- Operators: for mathematical operations right inside of CSS `100%-20%`
- Mixins: `@mixin name{}` `@include name()` define style that can be re-used in the CSS 
- Functions: similar to mixins, with the difference that they produce a value that can be used `@mixin name($parameter){}`
- Partials and imports: `@import` to write CSS in different files and importing them all into one single file 
- Extends: `@extend` allow a selector to inherit the styles of another one, you can overwrite the style
- Placeholder: styles that were meant to be extended `%placeholder``@extend %placeholder`
- Control directives: for writing complex code using conditionals and loops

#### Mixin function in Sass
```css
@mixin flexCenter ($direction){
  display:  flex;
  justify-content: center;
  align-items: center;
  flex-direction: $direction;
}
header{
  @include flexCenter(column);
}
```

#### Sass comments
- regular CSS starts with `/* comments…*/`
- SASS: the single line comments `//` and the multiline CSS comments with `/* */`.

#### Data Types that SassScript supports
SassScript supports seven main data types
1. Numbers ( eg; 1,5 ,10px)
2. Strings of texts ( g., “foo”, ‘bar’, etc.)
3. Colors (blue, #04a3f9)
4. Booleans (true or false)
5. Nulls (e.g; null)
6. List of values, separated by space or commas (g., 1.5em, Arial, Helvetica etc.)
7. Maps from one value to another (g., ( key 1: value1, key 2: Value 2))

#### How interpolation is used in Sass?
- Define an element in a variable and interpolate it inside the Sass code
- It is useful when you keep your modules in separate files.

#### the meaning of DRY-ing out a mixin?
- splitting it into dynamic and static parts.
- the dynamic mixin is the one that the user actually going to call
- the static mixin is the pieces of information that would otherwise get duplicated. 

#### what Sass Maps is and what is the use of Sass Maps?
A structured data in a hierarchical way and not just a bunch of variables, helps in organizing the code.
- It is very useful when dealing with layers of elements
- It can be helpful in color management when there is long list of different color and shade
- Use icon map for various social media icons for example: facebook: ‘\e607’ or twitter: ‘\e602’
- Unlike other programming libraries, Sass map will consist only of code that is going to be used

[[↑] Back to top](#table-of-contents)

## JavaScript

#### what is V8?
Internal JavaScript engine built in Chrome.

#### "use strict" Mode
It gives you less tolerate to errors, put on top of your program

#### data type
primitive data types, variable stores the values
```js
let a = 1; //number
a= "hello" //string
a = true // boolean
a = undefined // let a;
a = null; // let a = null;
```

non-primitive, object points to a reference, not the value itself
```js
a = {} // object
arr = [] // object (array)
function(){}  //function - object
```

false values: false, 0, -0, 0n, "", null, undefined, and NaN

#### =, ==, ===
- `=` - assignment operator, which sets the variable on the left of the = to the value of the expression that is on its right
- `==` - comparison operator, which transforms the operands having the same type before comparison `2=='2'`
- `===` - strict equality comparison operator, which returns false for the values which are not of a similar type  `2==='2'`

#### concat
It is recommended to use `+` and `+=` which are better/faster over `.concat()` for performance reason.
```js
//automatically convert to string; number + -> concat
console.log(1+"2")     //12
console.log(2+"1")     //21
console.log(1+2+"1")    //31

//no concat, will automatically convert to math operation
console.log(5-"2")  //3
console.log(5-"a") //NaN
//Not a number, invalid operation, no ascii code in JS
```

#### dynamic casting
```js
console.log(typeof Boolean(1)) //boolean
let a = 1
console.log(typeof !a) //boolean, check the 2nd value
console.log(!1) //false
let a = 1
console.log(typeof !!a) //true, !! - double negation
let a = 0
console.log(typeof !!a)  //false, boolean will be false
!!""    //false, nothing in there
!!" " //true, there is a space, it is not empty
!!{}    //true - it is object, empty box but there is something

=   assign
==   same value
===   same type same value, everything equals
null == false    //false
undefined == false  //false
null == undefined   //true
null === undefined  //false
console.log()    //undefined

|| or
&& and
! not
console.log(1 || 0)    //1
console.log(1 && 0)    //0
console.log(1 || 2 || 3) //1 - OR - looking for the first TRUCY value, otherwise return last element
console.log(1 && 2 && 3) //3 - AND - looking for the first FALSY value, if not any, return last element
```

#### error-handling
- The try statement lets you test a block of code for errors.
- The catch statement lets you handle the error.
- The throw statement lets you create custom errors. (execution of the current function will stop, the statements after throw won't be executed, and control will be passed to the first catch block in the call stack. If no catch block exists, the program will terminate.)
- The finally statement lets you execute code, after try and catch, regardless of the result.

[[↑] Back to top](#table-of-contents)

## ES6

#### New Features of ES6
1. let const vs var 
2. arrow function
3. template literal 
4. default params
5. destructuring
6. spreading (...) /rest (...rest)
7. promises
8. class syntax

#### Difference between var and let/const 
- var - value hoisting, put things on the top, scope to the function
- let/const - not accessible before the line we declare them, scope to the block
```js
console.log(a);    //undefined - variable exist, not able to access to the value
var a = 1;
console.log(b);   //referenceError - b is not exist, temporal dead zone
let b = 1;
```
- var - old time, issue with variable hoisting
- let - we can still re-assign value
- const - no re-assign value allowed, good with objects because we are not changing pointer

#### Hoisting
- Variable hoisting means the JavaScript engine moves the variable declarations to the top of the script. 

#### Temporal Dead Zone
- accessing a let or const variable before its declaration (within its scope) causes a ReferenceError.
- between the creation of a variable’s binding and its declaration, is called the temporal dead zone.

#### Describe Arrow Function
- simple syntax, less code
- does not have its own "this" to be referred to the current object
- does not need to bind functions
- does not have "arguments" which access to all the inputs parameters
- use lexical scoping — 'this' refers to it's current surrounding scope and no further.

Disadvantage of Arrow Function
- can never be used as constructor functions
- can never be invoked with the new keyword
- a prototype property does not exist for an arrow function.

```js
var obj = {
	name: "mic",
	getName: function(){
		return this.name    //"this" belongs to the obj that calls the function
	}
};
console.log(obj.getName())    //mic

var obj = {
	name: "mic",
	getName: () => {    
		return this.name    //arrow function does not have its own "this", "this" here means the Window    
	}
};
console.log(obj.getName())    //undefined
```

#### default params
```js
const genParam = () => {
  console.log("Called");
  return 5;
};

function f(x, y = genParam()) {
  console.log(x, y);
}

f(1); //Called  1, 5
f(1,  9); //1, 9
f(1, undefined);  //Called  1, 5 - no difference from f(1);
f(1, null); //1, null - null considered to be a valid input
```

#### destructuring
```js
const obj = { x: 1 };
const { x: otherX } = obj;  //re-naming, will be stored in the new name
console.log(otherX)   //1
//console.log(x)   //no good, referenceError, x is not defined.

//in array, order matters
const arr = [1, 2];
let [z, q] = arr;
console.log(q, z);  //2 1
[q, z] = [z, q];
console.log(q, z);  //1 2 - reassign the value

//Re-naming
const obj = { x: 1 };
const { x: newVariable } = obj;   //just about the syntax, change the name x to newVariable
// const newVariable = obj.x    //x as the key to get the value and stores in the variable
console.log(newVariable)  //1
```

#### spreading (...)
```js
const obj = { x: 1 };
const newObj = { ...obj };
console.log(newObj)    //{ x: 1 }
console.log(obj === newObj)   //false - shallow clone

const newObj = { ...obj, y: 2 }; // addition
const newObj = { ...obj, x: 2 }; // overwrite

const s = "Hello";
const sArr = [...s];
console.log(sArr) //["H", "e", "l", "l", "o"]
console.log(sArr.length); //5
```

#### rest (...rest)
```js
function func(a) {
  console.log(a); //1
}
func(1);

function func(a, ...rest) {   //rest element must be the last parameter
  console.log(rest); //[2, 3, 4, 5, 6, 7]
}
func(1, 2, 3, 4, 5, 6, 7);

function func(a, b, ...rest) {
  console.log(rest); //[3, 4, 5, 6, 7]
  console.log(arguments[0]); //1 - arguments is for everything in the params, it returns array like object, but does not carry any array methods
}
func(1, 2, 3, 4, 5, 6, 7);
```

#### Promise(Event-loop, task scheduling)
- JS is a single-threaded language, use promise to handle async operation
- new feature of ES6 -> avoid callback hell - a chained nested code

3 phrases -> pending, fulfilled, rejected
- chain .then() to do something, and/or .catch() to catch error
- will return another promise so we can chain more then()
- output order - only after the main thread is done

`Promoise.all` to send all promises, will reject immediately upon any of the input promises rejecting

`main thread (console.log) > micro (promise, async/await-pauses) > macro (timeout, interval)`

```js
const promise = new Promise(function(resolve, reject) {
  return setTimeout(() => resolve("done"), 3000);
});

promise.then((resolve) => {console.log(resolve)});
```

[[↑] Back to top](#table-of-contents)

## This

#### bind vs apply vs call
`bind()`
- The bind() method creates a new function used to provide a proper "this" reference to the function
- it returns a new bound function, does not call the function, but refer to it that you can execute later

`apply()/call()`
- same, just the different way to put in the parameter: call => comma; apply => array
- directly triggers itself, call it right now, unlike bind, not yet to call

#### "this" keyword
- refers to the object that the function is a property of. 
- the value will always depend on the object that is invoking the function.

the key word "this" behaves differently in arrow functions compared to a regular function.
- "this" in function, this belongs to function, it binds its own value, like person.fullName(), "this" refers to the left to the '.' 
- "this" in arrow function, "this" DOES NOT belong to arrFunc, it is outside of the function, arrow functions don't bind their own this value
```js
//1. this IN method, this -> object owner
const person = {
    firstName: 'Viggo',
    lastName: 'Mortensen',
    fullName: function () {
        return `${this.firstName} ${this.lastName}`     //just like ${person.firstName} ${person.lastName}, this -> object owner
    },
    
//     fullName: () => {        //"this" has nothing to do with the scope where the function is created, it has to do with how the function is executed
//         console.log(this);  // "this" refers to Window, if we do person.fullName() which means Window.fullName() - it will be undefined
//         return `${this.firstName} ${this.lastName}`
//     },       //when we are using arrow function, "this" will be jumping out to the original block which will be global scope
    
    shoutName: function () {
        setTimeout(() => { 
            //keyword 'this' in arrow functions refers to the value of 'this' when the function is created
            console.log(this);       //"this" refers to the person Object
            console.log(this.fullName())
        }, 3000)
        
//     shoutName: function () {
//         setTimeout(function () => {      //we have to use arrow function here instead
//             console.log(this);       // "this" refers to Window object here
//             console.log(this.fullName())     //this.fullName is not a function - it has to do with the execution context
//         }, 3000)        
    }
}
person.fullName()   //"this" refers to the left to the '.' here is the person

//2. this IN function, this -> global on browser -> Window
function a() {
    console.log(this)   //Window, this -> global
}
a()     //Window
console.log(this)      //Window

//2.1 this IN function, strick mode, this -> undefined
function a() {
    "use strict"
    console.log(this) 
}
a();   //undefined

//3. this IN event, this -> HTML element that received the event
<button onClick="this.style.display"="none">
    click to remove me!
</button>
```

[[↑] Back to top](#table-of-contents)

## JS Methods

#### Closure 
- a function retured by another function that still has access to its outer scope variable
- used to enable data privacy.
- cons: cause memory leak
```js
function makeCounter(){
    let count = 0;      //private variable for keeping data private and safe
    			//value by the function will be saved as it will be needed by the inner function, not for garbage collection
    return function(){
        count++
        return count;
    };
}
const counterFunc = makeCounter();
console.log(counterFunc()); //1
console.log(counterFunc()); //2
const newFunc = makeCounter();  //a new function, variabel value start over
console.log(newFunc());  //1
console.log(newFunc());  //2
```

#### Callbacks
- a function passed into another function as an argument to be executed later after another function has finished executing
- it is a great way to handle something after something else has been completed.

#### Currying
- transform a function of arguments n, to n functions of one or less arguments. 
- we do not change the functionality of a function, we just change the way it is invoked. 
- `const addNumber = (a) => (b) => (c) => a+b+c;`

#### First Order Function
First-order function is a function that doesn’t accept another function as an argument and doesn’t return a function as its return value.
- `const firstOrder = () => console.log ('I am a first order function!');`

#### Higher Order Function
Higher-order function is a function that accepts another function as an argument or returns a function as a return value or both.
```js
const firstOrderFunc = () => console.log ('Hello, I am a First order function');
const higherOrder = ReturnFirstOrderFunc => ReturnFirstOrderFunc();
higherOrder(firstOrderFunc);
```

#### Unary Function
Unary function is a function that accepts exactly one argument. It stands for a single argument accepted by a function.
- `const unaryFunction = a => console.log (a + 10); // Add 10 to the given argument and display the value`

#### Function Declaration vs Function Expression in JS
- Function declarations load before any code is executed 
- Similar to the var statement, function declarations are hoisted to the top of other code. 
- Function expressions load only when the interpreter reaches that line of code. 
- Function expressions aren’t hoisted, which allows them to retain a copy of the local variables from the scope where they were defined.
```js
myF()
function myF(){
	console.log("My Function")    //it is okay to under the function declaration using keyword function
}
myF()
const myF = function(){
	console.log("My Function")  //ReferenceError, no good with function expression, can not access function initialization, myF() failed directly
}
myF()
var myF = function(){
	console.log("My Function")  //TypeError, no good, myF is not a function, var myF = undefined;
	//when you try to execute myF(), it is good, it is there, but it triggers the function which is undefined, that it breaks the rule. 
}
```

Benefits of Function Expressions:
- As closures
- As arguments to other functions
- As Immediately Invoked Function Expressions (IIFE)

#### IIFE - immediate invoked function expression 
- runs as soon as it is defined, invoke immediately
- variables declared in the function expression will not be available outside the function
- primary purpose: data privacy because any variables declared within the IIFE cannot be accessed by the outside world.

contains two major parts: 
1. function expression within the Grouping Operator () 
2. immediately invoke the function ()

```js
(function() {
  /* */
})()

(() => {
  /* */
})()
```

#### Shallow Comparison & Deep Comparison
- Shallow strategy compares superficially 2 operands equality — 1st level in depth only,
- Deep strategy compares the equality from all depth levels.

#### Deep Clone vs Shallow Clone
Deep Clone - no more contact with previous reference, they are not related, any modification would not influence original copy

2 ways to implement deep clone
1. third party lib => _lodash.cloneDeep()
2. JSON parse and stringify
```js
//1. Lodash
// var _ = require("lodash");
import { cloneDeep } from "lodash";
const obj = { x: 1 };
const newObj = _.cloneDeep(obj);
console.log(newObj);  //{x: 1}

//2. JSON parse and stringify 
//completely convert to a raw string and convert back, so every layer will be completely different
const newObj2 = JSON.parse(JSON.stringify(obj));
console.log(newObj2); //{x: 1}
```

Shallow Clone - reuse previous reference, certain (sub-)values are still connected to the original variable
```js
// value => primitive type -> Number String Boolean Null Undefined
const obj = { x: 1 } };
const newObje = {...obj}; //shallow copy
newObj.x = 9;
console.log(newObj);  //{x:9)	
console.log(obj); //{x:1)   //original object not touched, different addresses in memory

// value => non-primitive -> Object Array
//assigning everything in a different type but because the value type is different, it is an object
//there is a reference pointer points to the object
const obj = { x: { y: 1 } };  //add one more layer
const newObj = {...obj}; //shallow copy - only restirct to the shallow level
newObj.x.y = 9;
console.log(newObj); //{x: { y: 9 } - only direct properties on the object point to different address, nested properties point to the same
console.log(obj);  //{x: { y: 9 } - also change to 9, both get update
```

## DOM Event

#### JS mechanism (how to handle the sync and async code)
The event loops behind the browser handles the sync and async JavaScript code, like when JS engine that built in the browser (for chrome is V8) runs JS code, because JS is a single threaded language, the code will be read line by line, and stores the memory in the heap, and push the function call to the call stack. If it is async function code, it will be then pushed to the web API instead to wait for the condition to be met while the call stack keeps running as first in last out and garbage collects the variables that are no longer in use. Once the async code in the web API is ready to run, it will then be pushed to the message queue. When there are no functions to run in the call stack, the Event Loop will take the first event from the Queue and will push it to the Call Stack to run.

#### addEventListener()
- `element.addEventListener(event, function, useCapture)`
- addEventListener() method attaches an event handler to the specified element.
- removeEventListener() method to remove an event handler that has been attached with the addEventListener() method.
- event: A String that specifies the name of the event like "click", "mouseover", "keyup"
- function: Specifies the function to run when the event occurs
- useCapture: Optional. A Boolean value that specifies whether the event should be executed in the capturing or in the bubbling phase.

Using the optional useCapture parameter to demonstrate the difference between bubbling and capturing:
`document.getElementById("myDiv").addEventListener("click", myFunction, true);`

useCapture Possible values:
- true: The event handler is executed in the capturing phase
- false: Default. The event handler is executed in the bubbling phase

#### Event Propagation
- like a deeper ocean goes to the layer one by one travel through the DOM tree to arrive at its target and what happens to it afterward
- Event.stopPropagation() - prevents further propagation of the current event in the capturing and bubbling phases. 

Three phases in order are:
1. the event capturing phase - top to the botton - outermost to inner - click outter which will trigger the inner one. 
2. the target phase - all the listeners registered on the event target will be invoked
3. the event bubbling phase - buttom to the top - innermost to outer - click the inner one, the outter one will also be clicked

#### Event Delegation
- Allow you to avoid adding event listeners to specific nodes; instead, the event listener is added to one parent. 
- That event listener analyzes bubbled events to find a match on child elements.
- Instead of attaching the event listeners directly to the buttons, you delegate listening to the parent `<div id="buttons">`. 
- When a button is clicked, the listener of the parent element catches the bubbling event (recall the event propagation).

[[↑] Back to top](#table-of-contents)