#Front-end Job Interview Questions

This file contains a number of front-end interview questions that can be used when vetting potential candidates. It is by no means recommended to use every single question here on the same candidate (that would take hours). Choosing a few items from this list should help you vet the intended skills you require.

**Note:** Keep in mind that many of these questions are open-ended and could lead to interesting discussions that tell you more about the person's capabilities than a straight answer would.

## Table of Contents

  1. [General Questions](#general-questions)
  1. [HTML Questions](#html-questions)
  1. [CSS Questions](#css-questions)
  1. [JS Questions](#js-questions)
  1. [Testing Questions](#testing-questions)
  1. [Performance Questions](#performance-questions)
  1. [Network Questions](#network-questions)
  1. [Coding Questions](#coding-questions)
  1. [Fun Questions](#fun-questions)

## Getting Involved

  1. [Contributors](#contributors)
  1. [How to Contribute](https://github.com/h5bp/Front-end-Developer-Interview-Questions/blob/master/CONTRIBUTING.md)
  1. [License](https://github.com/h5bp/Front-end-Developer-Interview-Questions/blob/master/LICENSE.md)

#### General Questions:

* What did you learn yesterday/this week?
* What excites or interests you about coding?
* What is a recent technical challenge you experienced and how did you solve it?
* What UI, Security, Performance, SEO, Maintainability or Technology considerations do you make while building a web application or site?
* Talk about your preferred development environment.
* Which version control systems are you familiar with?
* Can you describe your workflow when you create a web page?
* If you have 5 different stylesheets, how would you best integrate them into the site?
* Can you describe the difference between progressive enhancement and graceful degradation?
* How would you optimize a website's assets/resources?
* How many resources will a browser download from a given domain at a time?
  * What are the exceptions?
* Name 3 ways to decrease page load (perceived or actual load time).
* If you jumped on a project and they used tabs and you used spaces, what would you do?
* Describe how you would create a simple slideshow page.
* If you could master one technology this year, what would it be?
* Explain the importance of standards and standards bodies.
* What is Flash of Unstyled Content? How do you avoid FOUC?
* Explain what ARIA and screenreaders are, and how to make a website accessible.
* Explain some of the pros and cons for CSS animations versus JavaScript animations.
* What does CORS stand for and what issue does it address?

#### HTML Questions:

* What does a `doctype` do?
- Tells the HTML validator which standard/specification to use, tells browser how to render page in standards mode
* What's the difference between standards mode and quirks mode?
- Quirks mode occurs when a doctype is missing from html document, allows browser to render as it sees fit not according to a set standard
* What's the difference between HTML and XHTML?
- XHTML is based on xml, much more strict than HTML, will not render elements with malformed syntax
* Are there any problems with serving pages as `application/xhtml+xml`?
- Support in older IE is problematic, HTML entities are not well supported - only a view show up, any script or style tags need to be wrapped in block elements, need to be very specific, CSS applied not the same as HTML
* How do you serve a page with content in multiple languages?
- Ensure proper encoding (UTF) <meta charset="UTF-8">, formatting of date, timezone, <html lang="en">, dir="rtl"
* What kind of things must you be wary of when design or developing for multilingual sites?
- RTL languages, spacing issues - word wrapping and breaking
* What are `data-` attributes good for?
- allow us to store extra information, accessible through both JS and CSS
* Consider HTML5 as an open web platform. What are the building blocks of HTML5?
- Increase in semantic markup considerations (new elements), new APIs for audio, video, communications protocols, data storage, location and other multimedia APIs
* Describe the difference between a `cookie`, `sessionStorage` and `localStorage`.
- sessionStorage - only works for current live session, expires on window close. localStorage - persistent and scoped to domain, stores data with no expiration date, Cookies = the old school way of doing all of the above. Stores name/value pairs per domain.
* Describe the difference between `<script>`, `<script async>` and `<script defer>`.
* Why is it generally a good idea to position CSS `<link>`s between `<head></head>` and JS `<script>`s just before `</body>`? Do you know any exceptions?
- CSS needs to load fast to allow presentation to show, scripts can block page loading so should come at the very end
* What is progressive rendering?
- rendering what you can as soon as possible to give the perception of speed
* Have you used different HTML templating languages before?
  - handlebars, underscore, jade, mustache, twig

#### CSS Questions:

* What is the difference between classes and ID's in CSS?
- Specificity, classes can be used more than once, IDs will be scrolled to as Hash values,
* What's the difference between "resetting" and "normalizing" CSS? Which would you choose, and why?
- Resetting refers to removing Browser biases, normalizing is a bit more presecriptive in that it doesn't remove all base styles, but makes them equal
* Describe Floats and how they work.
- page elements with the CSS float property applied to them allow text and other elements to flow around them. Floated elements remain a part of the flow of the web page.
* Describe z-index and how stacking context is formed.
- z-index controlls elements in a virtual 3rd dimension. Lower values denote a lower stacking order. Value 9 will show on top of value 3
* Describe BFC(Block Formatting Context) and how it works.
- becomes responsible for the layout of its child elements. It's the child elements which are then "contained", whether that's floats or collapsing margins they should be wholly contained by their bounding parent.

* What are the various clearing techniques and which is appropriate for what context?
- Empty Div Method:
<div style="clear:both;"></div>

- Overflow Method: setting auto or hidden overflow property on parent will expand it to contain the floats.

- The Psuedo Method: uses the parent's :after to add the clear: both property
.clearfix:after {
content: ".";
visibility: hidden;
display: block;
height: 0;
clear: both;
}


* Explain CSS sprites, and how you would implement them on a page or site.
- A way to reduce HTTP requests by combining images together into one big image so you only have to request that one.

* What are your favourite image replacement techniques and which do you use when?

* How would you approach fixing browser-specific styling issues?
- Vendor prefixes where available, otherwise reevaluate styles to see if there's another way of coding something to render reliably across browsers

* How do you serve your pages for feature-constrained browsers?
- Progressive enhancement?

* What techniques/processes do you use?
- Have begun to implement RSCSS & ITCSS to help keep a more organized structure, scalable css project

* What are the different ways to visually hide content (and make it available only for screen readers)?
- #1: visibility: hidden
- #2: width: 0; height: 0;
- #3: text-indent: -1000px
- #4: absolute position off the screen

* Have you ever used a grid system, and if so, what do you prefer?
- 960, but today use a variation of bootstraps grid

* Have you used or implemented media queries or mobile specific layouts/CSS?
- yes, constantly. Mobile & responsive/adaptive design/dev is a strength

* Are you familiar with styling SVG?
- yes, I've used both plain CSS and JS to animate and affect SVG

* How do you optimize your webpages for print?
- @media print - depends on the layout, project, but may need to adjust text size, ensure relevant content is visible

* What are some of the "gotchas" for writing efficient CSS?
- prefer classes over elements/tags, avoid *

* What are the advantages/disadvantages of using CSS preprocessors?
- adv: SASS has so much power built into it for mixins, extend, includes etc. variables are now a necessity. Ability to break out stylesheets into components. Dis: easier to write sloppy css and get code bloat. Not a guarantee, but specificity can get too strong with too much nesting.

* Describe what you like and dislike about the CSS preprocessors you have used.
- I haven't disliked anything about the preprocessors I've used. They all have their quirks, but mostly (LESS & SASS) offer the same features. Stylus is great, but it's sparseness is not much of an improvement and I actually prefer the brackets/braces of less/sass

* How would you implement a web design comp that uses non-standard fonts?
- @font-face, Access rights to fonts, use fontforge or the like to to package necessary outputs, woff, eot, svg, etc. Call font family with non standar font first, then standard system fonts

* Explain how a browser determines what elements match a CSS selector.
Reads from right to left ( right overrides left )

* Describe pseudo-elements and discuss what they are used for.
- Powerful for layout (cf), adding special icons, characters

* Explain your understanding of the box model and how you would tell the browser in CSS to render your layout in different box models.
- For display purpose, every element in the page is considered a box. The box model refers to the specification of the box attributes such as the width, padding, border and margin.
- You can change the box model by setting the box-sizing property. Some values are: content-box (default), padding-box, and border-box) - Content-box: width & height includes content but not padding/border/margin, Padding-box: include up to padding, Border-box: include up to border, but not margin

* What does ```* { box-sizing: border-box; }``` do? What are its advantages?
- includes space up to border, but not margin. Adv: helps responsive layouts, reduces page overflow issues

* List as many values for the display property that you can remember.
- block, inline-block, table-cell, table, flex(box), inherit, initial, none

* What's the difference between inline and inline-block?
- All items default to inline: will accept padding and margin to left&right not top or bottom, will not use height or width, inline-blcok behaves as inline except accepts the features that inline does not as well as align property

* What's the difference between a relative, fixed, absolute and statically positioned element?
- fixed and abs are not in the layout anymore. Static is default, relative can use z index, cntains absolute,

* The 'C' in CSS stands for Cascading.  How is priority determined in assigning styles (a few examples)?  How can you use this system to your advantage?
- Important!, Inline > ID > Classes - from there it's about amount of specificity (in practice how much nesting has been done)

* What existing CSS frameworks have you used locally, or in production? How would you change/improve them?

* Have you played around with the new CSS Flexbox or Grid specs?
- Yes, my site is built on flexbox. I use modernizr for feature detection to adjust styles for old browsers

* How is responsive design different from adaptive design?
- Adaptive adapts to the device dimensions which is sometimes multiple versions of the same layout done for different devices
- Purely speaking, Adaptive uses breakpoints while responsive is completely percentage based

* Have you ever worked with retina graphics? If so, when and what techniques did you use?
-
* Is there any reason you'd want to use `translate()` instead of *absolute positioning*, or vice-versa? And why?
-

#### JS Questions:

* Explain event delegation
* Explain how `this` works in JavaScript
- The this object is bound at runtime based on the context in which a function is executed:
    when used inside global functions,this is equal to window in nostrict mode and undefined in strict mode.
    whereas this is equal to the object when called as an object method.
    as a constructor
    call and apply
    bound functions
    as dom event handler

* Explain how prototypal inheritance works
  - Whenever a function is created, its prototype property is also created according to a specific set of rules.
  When it comes to inheritance, JavaScript only has one construct: objects. Each object has an internal link to another object called its prototype. That prototype object has a prototype of its own, and so on until an object is reached with null as its prototype. null, by definition, has no prototype, and acts as the final link in this prototype chain.

* What do you think of AMD vs CommonJS?
* Explain why the following doesn't work as an IIFE: `function foo(){ }();`.
- Function definitions are not invocable
  * What needs to be changed to properly make it an IIFE?
  - need to wrap function in parentheses: (function foo(){ }());

* What's the difference between a variable that is: `null`, `undefined` or undeclared?
  - null is a value type signifying no value. A variable can be assigned a value of null
  undefined is returned when a variable has been declared but assigned no value,
  Undeclared variables are those that are not declared at all.

  * How would you go about checking for any of these states?
  - Null and undefined are the same value but different types, Use typeof to check for undefined

* What is a closure, and how/why would you use one?
  - closure is a case when an inside function is enclosed by an outside function and the inside function has access to all variables and values of it's enclosing function

* What's a typical use case for anonymous functions?
  - If no name is needed because the function is only ever called in one place, then why add a name to whatever namespace you're in.

  Anonymous functions are declared inline and inline functions have advantages in that they can access variables in the parent scopes. Yes, you can put a name on an anonymous function, but that's usually pointless if it's declared inline. So inline has a significant advantage and if you're doing inline, there's little reason to put a name on it

  The code seems more self-contained and readable when handlers are defined right inside the code that's calling them. You can read the code in almost sequential fashion rather than having to go find the function with that name.

* Lexical scoping
  - This means that the functions run in the scope in which they are defined, not the scope from which they are executed.

* How do you organize your code? (module pattern, classical inheritance?)

* What's the difference between host objects and native objects?
  - Native objects are those objects supplied by JavaScript. Examples of these are String, Number, Array, Image, Date, Math, etc.

  Host objects are objects that are supplied to JavaScript by the browser environment. Examples of these are window, document, forms, etc.

* Difference between: `function Person(){}`, `var person = Person()`, and `var person = new Person()`?
  - 1. declares Person function, 2. copies Person function to person, 3. creates copy of Person as Person is now a constructor function?

* What's the difference between `.call` and `.apply`?
  - Apply lets you invoke the function with arguments as an array; call requires the parameters be listed explicitly.

  function.apply(valueForThis, [arg1, arg2, ...])
  function.call(valueForThis, arg1, arg2, ...)

* Explain `Function.prototype.bind`.
  - ECMAScript 5 defines an addition method called 'bind()'.the 'bind()' method create a new function instance whose this value is bound to the value to that was passed into 'bind()'.

* When would you use `document.write()`?
  - As little as possible, namespacing, polluting the global window

* What's the difference between feature detection, feature inference, and using the UA string?
  - Feature Detection is to identify the browser's capabilities.
  Feature Inference is guess whether browser has certain feature through others feature or UA string.

  One inappropriate use of feature detection is called feature inference. Feature inference attempts to use multiple features after validating the presence of only one. The presence of one feature is inferred by the presence of another. The problem is, of course, that inference is an assumption rather than a fact, and that can lead to maintenance issues.

  UA String is User-Agent Detection.

* Explain AJAX in as much detail as possible.
  - Make http requests (use of the XMLHttpRequest object to communicate with server-side scripts). It can send as well as receive information in a variety of formats, including JSON, XML, HTML, and even text files.

  AJAX's most appealing characteristic, however, is its "asynchronous" nature, which means it can do all of this without having to refresh the page. This lets you update portions of a page based upon user events.

* Explain how JSONP works (and how it's not really AJAX).
  - By default, Ajax requests have to occur in the same domain of the page where the request originates. JSONP - "JSON with padding" - was created to allow you to request JSON resources from a different domain. (CORS is a newer and better alternative to JSONP.)

* Have you ever used JavaScript templating?
  * If so, what libraries have you used?
  - handlebars, underscore, jade, mustache

* Explain "hoisting".
  - Function declarations and variable declarations are always moved (“hoisted”) invisibly to the top of their containing scope by the JavaScript interpreter.

* Describe event bubbling.
  - Event bubbling and capturing are two ways of event propagation in HTML DOM.

  In bubbling the event is first captured and handled by the innermost child element and then propagated to outer parent elements.

  In capturing the event is first captured by the outermost parent element and propagated to the innermost child element.


* What's the difference between an "attribute" and a "property"?

* Why is extending built-in JavaScript objects not a good idea?
  - Not positive, but if I had to guess at it, I'd say that it can result in inheritance issues and other unplanned consequences

* Difference between document load event and document ready event?
  - ready means DOM is ready.
  load means the page fully loaded. Includes inner frames, images etc.

* What is the difference between `==` and `===`?
  - The == operator will compare for equality after doing any necessary type conversions. The === operator will not do the conversion, so if two values are not the same type === will simply return false. It's this case where === will be faster, and may return a different result than ==. In all other cases performance will be the same.

* Explain the same-origin policy with regards to JavaScript.
  - Related to domain source of files or referenced material

* Make this work:
```javascript
duplicate([1,2,3,4,5]); // [1,2,3,4,5,1,2,3,4,5]
```
  function duplicate(a) {
    var v = [];
    a.forEach(function(n){
      v.push(n);
    });
    x = a.concat(v);
    return x;
  }

* Why is it called a Ternary expression, what does the word "Ternary" indicate?
  - because it takes 3 (ter) operands. condition ? expr1 : expr2

* What is `"use strict";`? what are the advantages and disadvantages to using it?
  - Strict Mode is a new feature in ECMAScript 5 that allows you to place a program, or a function, in a "strict" operating context. This strict context prevents certain actions from being taken and throws more exceptions.

  Strict mode helps out in a couple ways:

  It catches some common coding bloopers, throwing exceptions.
  It prevents, or throws errors, when relatively "unsafe" actions are taken (such as gaining access to the global object).
  It disables features that are confusing or poorly thought out.


* Create a for loop that iterates up to `100` while outputting **"fizz"** at multiples of `3`, **"buzz"** at multiples of `5` and **"fizzbuzz"** at multiples of `3` and `5`
  function fizzbuzz(n) {
    for(var x = 1; x <= n; x++) {
      if (x % 3 == 0 && x % 5 == 0) {
        console.log(x + ' fizzbuzz');
      }
      else if (x % 3 == 0) {
        console.log(x + ' fizz');
      }
      else if (x % 5 == 0) {
        console.log(x + ' buzz');
      }
    }
  }

* Why is it, in general, a good idea to leave the global scope of a website as-is and never touch it?
  - Less chance of polluting global scope with functions, variables that you probably don't want every function to have access to.

* Why would you use something like the `load` event? Does this event have disadvantages? Do you know any alternatives, and why would you use those?
  - If I wanted something to happen as soon as possible. Could block other things if there's an error. Use ready instead

* Explain what a single page app is and how to make one SEO-friendly.
  - HTML5 History API (pretty urls), prerender.io, sitemap.xml

* What is the extent of your experience with Promises and/or their polyfills?

* What are the pros and cons of using Promises instead of callbacks?
* What are some of the advantages/disadvantages of writing JavaScript code in a language that compiles to JavaScript?
  - Coffeescript is fast, has a few smooth additions that make authoring better. Just like CSS precompilers it's easier to write stuff that compiles bulkier, but generally it isn't an issue.

* What tools and techniques do you use debugging JavaScript code?
  - Chrome dev tools

* What language constructions do you use for iterating over object properties and array items?
  - for in, forEach, while...

* Explain the difference between mutable and immutable objects.
  - mutable can be changed, immutable cannot

  * What is an example of an immutable object in JavaScript?
    - Strings - you can change the value of the var they point to, but not the string itself

  * What are the pros and cons of immutability?
  * How can you achieve immutability in your own code?

* Explain the difference between synchronous and asynchronous functions.
* What is event loop?
  * What is the difference between call stack and task queue?

#### Testing Questions:

* What are some advantages/disadvantages to testing your code?
* What tools would you use to test your code's functionality?
* What is the difference between a unit test and a functional/integration test?
* What is the purpose of a code style linting tool?

#### Performance Questions:

* What tools would you use to find a performance bug in your code?
- Chrome dev tools, yslow

* What are some ways you may improve your website's scrolling performance?
- throttle scroll event with setInterval

* Explain the difference between layout, painting and compositing.

#### Network Questions:

* Traditionally, why has it been better to serve site assets from multiple domains?
* Do your best to describe the process from the time you type in a website's URL to it finishing loading on your screen.
* What are the differences between Long-Polling, Websockets and Server-Sent Events?
* Explain the following request and response headers:
  * Diff. between Expires, Date, Age and If-Modified-...
  * Do Not Track
  * Cache-Control
  * Transfer-Encoding
  * ETag
  * X-Frame-Options
* What are HTTP actions? List all HTTP actions that you know, and explain them.

#### Coding Questions:

*Question: What is the value of `foo`?*
```javascript
var foo = 10 + '20';
```
- 1020


*Question: How would you make this work?*
```javascript
add(2, 5); // 7
add(2)(5); // 7
```
- this is currying - re read


*Question: What value is returned from the following statement?*
```javascript
"i'm a lasagna hog".split("").reverse().join("");
```
- goh angasal a m'i

*Question: What is the value of `window.foo`?*
```javascript
( window.foo || ( window.foo = "bar" ) );
```
- bar


*Question: What is the outcome of the two alerts below?*
```javascript
var foo = "Hello";
(function() {
  var bar = " World";
  alert(foo + bar);
})();
alert(foo + bar);
```
"Hello World"
and error because foo is not defined


*Question: What is the value of `foo.length`?*
```javascript
var foo = [];
foo.push(1);
foo.push(2);
```
- 2

*Question: What is the value of `foo.x`?*
```javascript
var foo = {n: 1};
var bar = foo;
foo.x = foo = {n: 2};
```
- {n: 2}
???

*Question: What does the following code print?*
```javascript
console.log('one');
setTimeout(function() {
  console.log('two');
}, 0);
console.log('three');
```
- one, three, two


#### Fun Questions:

* What's a cool project that you've recently worked on?
* What are some things you like about the developer tools you use?
* Do you have any pet projects? What kind?
* What's your favorite feature of Internet Explorer?
* How do you like your coffee?


#### Contributors:

This document started in 2009 as a collaboration of [@paul_irish](https://twitter.com/paul_irish) [@bentruyman](https://twitter.com/bentruyman) [@cowboy](https://twitter.com/cowboy) [@ajpiano](https://twitter.com/ajpiano)  [@SlexAxton](https://twitter.com/slexaxton) [@boazsender](https://twitter.com/boazsender) [@miketaylr](https://twitter.com/miketaylr) [@vladikoff](https://twitter.com/vladikoff) [@gf3](https://twitter.com/gf3) [@jon_neal](https://twitter.com/jon_neal) [@sambreed](https://twitter.com/sambreed) and [@iansym](https://twitter.com/iansym).

It has since received contributions from over [100 developers](https://github.com/h5bp/Front-end-Developer-Interview-Questions/graphs/contributors).










QUESTIONS:
  What kind of work will I be doing in general?
  Is this a new position that has opened up because of more work?
  What is the company’s policy on work-life balance?
  What kind of tools or software are provided in the workplace?
  What would I be working on first?
  Am I allowed to do other work after hours?
  Is there a budget for conferences or training?
