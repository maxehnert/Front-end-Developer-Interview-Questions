#### JS Questions:

* Explain event delegation
 - Event delegation allows us to attach a single event listener, to a parent element, that will fire for all descendants matching a selector, whether those descendants exist now or are added in the future.
 - src - https://learn.jquery.com/events/event-delegation/
* Explain how `this` works in JavaScript
 - In the global execution context (outside of any function), `this` refers to the global object, whether in strict mode or not.
 - Inside a function, the value of `this` depends on how the function is called.
 - When a function is called as a method of an object, its `this` is set to the object the method is called on.
 - When a function is used as a constructor (with the new keyword), its `this is bound to new object being constructed.
 - When a function is used as an event handler, its `this` is set to the element the event fired from
 - src - https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this
* Explain how prototypal inheritance works
 - In JavaScript, any function can be added to an object in the form of a property. An inherited function acts just as any other property
 - When an inherited function is executed, the value of this points to the inheriting object, not to the prototype object where the function is an own property.
 - src - https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain
* How do you go about testing your JavaScript?
 - unit tests
 - end to end tests
* What do you think of AMD vs CommonJS?
* Explain why the following doesn't work as an IIFE: `function foo(){ }();`.
  * What needs to be changed to properly make it an IIFE?
* What's the difference between a variable that is: `null`, `undefined` or `undeclared`?
 - `undefined` means a variable has been declared but has not yet been assigned a value
 - `null` is an assignment value. It can be assigned to a variable as a representation of no value
 - A variable is `undeclared` when it does not use the var keyword
  * How would you go about checking for any of these states?
* What is a closure, and how/why would you use one?
 - Closures are functions that refer to independent (free) variables. In other words, the function defined in the closure remembers the environment in which it was created.
 - Much of the code we write in web JavaScript is event-based — we define some behavior, then attach it to an event that is triggered by the user (such as a click or a keypress). Our code is generally attached as a callback: a single function which is executed in response to the event
 - src - https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures
 - src - http://stackoverflow.com/questions/111102/how-do-javascript-closures-work
* What's a typical use case for anonymous functions?
 - Function expressions are convenient when passing a function as an argument to another function.
 - need more
 - https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions
* How do you organize your code? (module pattern, classical inheritance?)
 - good reference of prototypal and classical inheritance structures
 - http://stackoverflow.com/questions/19633762/classical-inheritance-vs-protoypal-inheritance-in-javascript
* What's the difference between host objects and native objects?
 - host object- object supplied by the host env to complete the execution env of ECMAscript
 - ex. - Host objects (assuming browser environment): window, document, location, history, XMLHttpRequest, setTimeout, getElementsByTagName, querySelectorAll
 - native object- obj in ECMA implementation whose semantics are fully defined by this spec rather than by the host env.
 - ex. - Native objects: Object (constructor), Date, Math, parseInt, eval, string methods like indexOf and replace, array methods
 - src - http://es5.github.io/#x4.3.6 && http://es5.github.com/#x4.3.8
* Difference between: `function Person(){}`, `var person = Person()`, and `var person = new Person()`?
 - `function Person(){}` - creating a function
 - `var person = Person()` - assigning variable `person` to the callback method `Person()`
 - `var person = new Person()` - ???
* What's the difference between `.call` and `.apply`?
 - `apply()` method calls a function with a given `this` value and arguments provided as an **array**
 - `call()` method calls a function with a given `this` value and arguments provided individually
 - The fundamental difference is that call() accepts an argument list, while apply() accepts a single array of arguments.
 - src - https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/call
* Explain `Function.prototype.bind`.
 - bind() method creates a new function that, when called, has its `this` keyword set to the provided value, with a given sequence of arguments preceding any provided when the new function is called
 - `fun.bind(thisArg[, arg1[, arg2[, ...]]])`
 - Binds the `this` value from the function it's being called from.
 - Example:
 ```javascript
 this.x = 9; 
var module = {
  x: 81,
  getX: function() { return this.x; }
};

module.getX(); // 81

var getX = module.getX;
getX(); // 9, because in this case, "this" refers to the global object

// Create a new function with 'this' bound to module
var boundGetX = getX.bind(module);
boundGetX(); // 81
```
 - src - https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/bind
* When would you use `document.write()`?
 - enter new content into the document *after* it has already loaded
 - src - https://developer.mozilla.org/en-US/docs/Web/API/Document/write
* What's the difference between feature detection, feature inference, and using the UA string?
 - Feature detection checks for an existing feature
 - Feature inference also checks for an existing feature but uses another function because assumes it exists
 - User Agent string is an outdated method that is not standard practice to use
 - src - https://developer.mozilla.org/en-US/docs/Browser_detection_using_the_user_agent
 - src - http://learn.jquery.com/code-organization/feature-browser-detection/
* What is the difference between `.substr()` and `.substring()`?
 - `substr` takes parameters as `(from, length)`
 - `substring` takes parameters as `(from, to)`
 - ex: 
  ```javascript
   alert("abc".substr(1,2)); // returns "bc"
   alert("abc".substring(1,2)); // returns "b"
```
 - src - https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/substring
 - src - https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/substr

 **Continued in js2.md**
-
