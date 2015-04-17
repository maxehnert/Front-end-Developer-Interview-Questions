* Explain AJAX in as much detail as possible.
 - Asynchronous JavaScript and XML
 - It is the use of the XMLHttpRequest object to communicate with server-side scripts. 
 - It can send as well as receive information in a variety of formats, including JSON, XML, HTML, and even text files. 
 - AJAX’s most appealing characteristic, however, is its "asynchronous" nature, which means it can do all of this without having to refresh the page. This lets you update portions of a page based upon user events.
 - src - https://developer.mozilla.org/en-US/docs/AJAX/Getting_Started
* Explain how JSONP works (and how it's not really AJAX).
 - JSON-P works by making a `<script>` element (either in HTML markup or inserted into the DOM via JavaScript), which requests to a remote data service location. 
 - The response (the loaded "JavaScript" content) is the name of a function pre-defined on the requesting web page, with the parameter being passed to it being the JSON data being requested. 
 - When the script executes, the function is called and passed the JSON data, allowing the requesting page to receive and process the data.
 - src - http://json-p.org/
* Have you ever used JavaScript templating?
  * If so, what libraries have you used?
   - handlebars and mustache
* Explain "hoisting".
* Describe event bubbling.
* What's the difference between an "attribute" and a "property"?
* Why is extending built in JavaScript objects not a good idea?
* Difference between document load event and document ready event?
* What is the difference between `==` and `===`?
* Explain the same-origin policy with regards to JavaScript.
* Make this work:
```javascript
duplicate([1,2,3,4,5]); // [1,2,3,4,5,1,2,3,4,5]
```
* Why is it called a Ternary expression, what does the word "Ternary" indicate?
* What is `"use strict";`? what are the advantages and disadvantages to using it?
* Create a for loop that iterates up to `100` while outputting **"fizz"** at multiples of `3`, `"buzz"` at multiples of `5` and **"fizzbuzz"** at multiples of `3` and `5`
* Why is it, in general, a good idea to leave the global scope of a website as-is and never touch it?
* Why would you use something like the `load` event? Does this event have disadvantages? Do you know any alternatives, and why would you use those?
* Explain what a single page app is and how to make one SEO-friendly.
* What is the extent of your experience with Promises and/or their polyfills?
