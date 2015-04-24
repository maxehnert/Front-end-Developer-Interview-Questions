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

*Question: What will be printed in the console?*
```javascript
(function() {
   var a = b = 5;
})();
 
console.log(b);
```
* Answer
  - `5` because `b` is NOT assigned with `var` so it is assigned to the GLOBAL scope.

*Question: Define a repeatify function on the String object. The function accepts an integer that specifies how many times the string has to be repeated. The function returns the string repeated the number of times specified.*
For example: `console.log('hello'.repeatify(3));` should print `hellohellohello`
* Answer
```javascript
String.prototype.repeatify = String.prototype.repeatify || function(times){
  var str = '';
  for(var i = 0; i < times; i++) {
    str += this;
  }
  return str;
};
console.log('hello'.repeatify(3));
```
*Question: What is the result of the following code?*
```javascript
var fullname = 'John Doe';
var obj = {
   fullname: 'Colin Ihrig',
   prop: {
      fullname: 'Aurelio De Rosa',
      getFullname: function() {
         return this.fullname;
      }
   }
};
 
console.log(obj.prop.getFullname());
 
var test = obj.prop.getFullname;
 
console.log(test());
```
* Answer
  - `console.log(obj.prop.getFullname());` prints `Aurelio De Rosa`
  - `console.log(test());` prints `John Doe`
  - The reason is because of the context of the `this` keyword
  - In the first `log` the`getFullname()` call is invoked as a function of the `obj.prop` object
  - On the second `log`, `test` is set as a property of the global object. Therefore the `this` of `test` is what is set in the global scope `John Doe`
