#### Coding Questions:

*Question: What is the value of `foo`?*
```javascript
var foo = 10 + '20';
```
* Answer
  - `"1020"` the `+` operator acts as a concatinator and is joining the 2 values together without logic.

*Question: How would you make this work?*
```javascript
add(2, 5); // 7
add(2)(5); // 7
```
* Answer
```javascript 
function add (valueA, valueB) {
var sum = valueA + valueB;
return sum;
}
add(2, 5); // 7
```

*Question: What value is returned from the following statement?*
```javascript
"i'm a lasagna hog".split("").reverse().join("");
```
* Answer
`"goh angasal a m'i"`
  - Lets break it down further though
```javascript
"i'm a lasagna hog".split("");
// ["i", "'", "m", " ", "a", " ", "l", "a", "s", "a", "g", "n", "a", " ", "h", "o", "g"]

"i'm a lasagna hog".split("").reverse();
// ["g", "o", "h", " ", "a", "n", "g", "a", "s", "a", "l", " ", "a", " ", "m", "'", "i"]

"i'm a lasagna hog".split("").reverse().join("");
// "goh angasal a m'i"
```

*Question: What is the value of `window.foo`?*
```javascript
( window.foo || ( window.foo = "bar" ) );
```
* Answer
  - `// "bar"`
  - invalid left side, not setting `window.foo` to anything so it goes on to the other side which is a valid expression

*Question: What is the outcome of the two alerts below?*
```javascript
var foo = "Hello";
(function() {
  var bar = " World";
  alert(foo + bar);
})();
alert(foo + bar);
```
* Answer
  - Only the inside alert works because the variable `bar` is scoped within the iife. This is also a basic example of a closure, I'm pretty sure. 

*Question: What is the value of `foo.length`?*
```javascript
var foo = [];
foo.push(1);
foo.push(2);
```
* Answer
  - 2 because `.push()` is putting 1 element inside the array each time. `.push(4)` and `.push("3")` will both result in a length of 1 individually.
