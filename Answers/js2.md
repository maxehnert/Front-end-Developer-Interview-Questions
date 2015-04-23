* Explain AJAX in as much detail as possible.
 - Asynchronous JavaScript and XML
 - It is the use of the XMLHttpRequest object to communicate with server-side scripts. 
 - It can send as well as receive information in a variety of formats, including JSON, XML, HTML, and even text files. 
 - AJAX’s most appealing characteristic, however, is its "asynchronous" nature, which means it can do all of this without having to refresh the page. This lets you update portions of a page based upon user events.
 - src -https://developer.mozilla.org/en-US/docs/AJAX/Getting_Started
* Explain how JSONP works (and how it's not really AJAX).
 - JSON-P works by making a `<script>` element (either in HTML markup or inserted into the DOM via JavaScript), which requests to a remote data service location. 
 - The response (the loaded "JavaScript" content) is the name of a function pre-defined on the requesting web page, with the parameter being passed to it being the JSON data being requested. 
 - When the script executes, the function is called and passed the JSON data, allowing the requesting page to receive and process the data.
 - src-http://json-p.org/
* Have you ever used JavaScript templating?
  * If so, what libraries have you used?
   - handlebars and mustache
* Explain "hoisting".
 - Because variables are read before js is executed, a variable can be called after it is used. This process is called "hoisting"
 - src-https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/var
* Describe event bubbling and event capturing.
 - when an event occurs in an element inside another element, and both elements have registered a handle for that event. The event propagation mode determines in which order the elements receive the event.
 - With bubbling, the event is first captured and handled by the innermost element and then propagated to outer elements.
 - With capturing, the event is first captured by the outermost element and propagated to the inner elements.
 - Capturing is also called "trickling", which helps remember the propagation order:
 - `bubble up, trickle down`
 - src w/great example and more info: http://stackoverflow.com/questions/4616694/what-is-event-bubbling-and-capturing
* What's the difference between an "attribute" and a "property"?
 - HTML representation of a DOM element has attributes.
 - When represented as a JavaScript object those attributes appear as object *properties.*
 - http://stackoverflow.com/questions/258469/what-is-the-difference-between-attribute-and-property
* Why is extending built in JavaScript objects not a good idea?
 - native prototypes should never be extended unless it is for the sake of compatibility with newer JavaScript features
 - Extending the prototype can cause other code to break that was using that prototype.
 - It is often ot obvious that the changes will cause code to break later and that is why it should be avoided. 
 - https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain
* Difference between document load event and document ready event?
 - `$( document ).ready()` will only run once the page Document Object Model (DOM) is ready for JavaScript code to execute. 
 - Code included inside `$( window ).load(function() { ... })` will run once the entire page, not just the DOM, is ready.
 - http://learn.jquery.com/using-jquery-core/document-ready/
* What is the difference between `==` and `===`?
 - pretty close `'1' == 1`
 - must be exact `1 === 1`
* Explain the same-origin policy with regards to JavaScript.
 - The same-origin policy restricts how a document or script loaded from one origin can interact with a resource from another origin. 
 - Same-origin Policy is used as a means to prevent some of the Cross-site Request Forgery attacks.
 * **Preventing XSS**
  - To prevent cross-origin writes, check for an unguessable token in the request, known as a Cross-Site Request Forgery (CSRF) token. You must prevent cross-origin reads of pages that know this token.
  - To prevent cross-origin reads of a resource, ensure that it is not embeddable. It is often necessary to prevent embedding, because embedding a resource always leaks some information about it.
  - To prevent cross-origin embedding, ensure that your resource can not be interpreted as one of the embeddable formats listed above. The browser does not respect the Content-Type in most cases.
 - src - https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy 
* Make this work:
`duplicate([1,2,3,4,5]); // [1,2,3,4,5,1,2,3,4,5]`
 - This is mostly correct
 - `var a = [1,2,3,4,5];`
 - `Array(3).join(a + ',');`
 - `// "1,2,3,4,5,1,2,3,4,5,"`
 
* Why is it called a Ternary expression, what does the word "Ternary" indicate?
 - The conditional (ternary) operator is the only JavaScript operator that takes three operands. 
 - This operator is frequently used as a shortcut for the if statement.
 - `condition ? expr1 : expr2`
 - src - https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator
* What is `"use strict";`? what are the advantages and disadvantages to using it?
 - strict mode is a way to opt in to a restricted variant of JavaScript
 - First, strict mode eliminates some JavaScript silent errors by changing them to throw errors. 
 - Second, strict mode fixes mistakes that make it difficult for JavaScript engines to perform optimizations: strict mode code can sometimes be made to run faster than identical code that's not strict mode. 
 - Third, strict mode prohibits some syntax likely to be defined in future versions of ECMAScript.
 - src - https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode
* Create a for loop that iterates up to `100` while outputting **"fizz"** at multiples of `3`, `"buzz"` at multiples of `5` and **"fizzbuzz"** at multiples of `3` and `5`
 ```javascript
 for( var i = 1; i <= 100; i++){
  if(i % 15 == 0){ console.log('fizzbuzz') }
  else if(i % 3 == 0){ console.log('fizz') }
  else if(i % 5 == 0){ console.log('buzz') }
  else console.log(i);
}
```

* Why is it, in general, a good idea to leave the global scope of a website as-is and never touch it?
 - 'polluting' the global scope can cause code to break much like extending built in javascript objects. 
* Why would you use something like the `load` event? Does this event have disadvantages? Do you know any alternatives, and why would you use those?
* Explain what a single page app is and how to make one SEO-friendly.
* What is the extent of your experience with Promises and/or their polyfills?
