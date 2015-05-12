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
  - `[1,2]` because `.push()` is putting 1 element inside the array each time.

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

*Question: Write a function that accepts any number of arguements and returns their sum (similar to earlier question). It should also accept and array and sum the array.*
* Answer
```javascript
function sum() {
  var i, l, result = 0;
  for (i = 0, l = arguments.length; i < l; i++) {
    result += arguments[i];
  }
  return result;
}

// list of numbers
sum(1,2,3); //6

// with array
var data = [1,2,3];
sum.apply(null, data); // 6
```

*Question: Write A Function That Capitalizes Every First Letter In A String*
```javascript
var str = "eCommerce rocks. crazyCamelCase stuff. _those  pigeon-toed shennanigans. Fiery trailblazing 345 thirty-two Roger. The quick brown fox jumped over the lazy dogs. Clancy Brown would have been cool as Lex Luthor. good_bye";
str.split(' ').map( function(x){
return x && x[0].toUpperCase()+x.slice(1);
}).join(' ');
```

*Question: Write a function that returns true for palindrome words?*
```javascript
function palindrome(str) {
    var len = str.length;
    for ( var i = 0; i < Math.floor(len/2); i++ ) {
        if (str[i] !== str[len - 1 - i]) {
            return false;
        }
    }
    return true;
}
```

*Question: Write a function that returns the largest prime factor of a number*
```javascript
function primeFactor() {
  // starting index (first prime)
  var i = 2;
  var num = 600851475143;

  while (num > i) {
    if (num % i === 0) {
      num = num / i;
    }

    i++;
  }

  console.log(i);
  return i;
};

var num = 600851475143;
primeFactor(num);
```
