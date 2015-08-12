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

*Question: Write a function that checks if a string can be a palindrome*
```javascript
function canBePalindrome(str)
{
    // set the string to lower case first
    var str = str.toLowerCase();
    
    var letterCounts = {};
    var letter;
    var palindromeSum = 0;
    
    for (var i = 0; i < str.length; i++) {
        letter = str[i];
        letterCounts[letter] = letterCounts[letter] || 0;
        letterCounts[letter]++;
    }
    
    for (var letterCount in letterCounts) {
        palindromeSum += letterCounts[letterCount] % 2;
    }

    return palindromeSum < 2;
}

canBePalindrome('aaa'); // true
canBePalindrome('aa1'); // true
canBePalindrome('aA1'); // true
canBePalindrome('aabb'); // true
canBePalindrome('aabbc'); // true
canBePalindrome('abbc'); // false
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

*Question: Determine if a number is a prime factor*
```javascript
function isPrime(num){
  // start at 2 because 1 = prime and 0=undefined
  var divisor = 2;
  
  while(num > divisor) {
    // if there is no remainder then it can't be prime
    if(num % divisor === 0) {
      return false;
    }
    else {
      divisor++;
    }    
  }
  // if it can loop through the entire while loop without finding a valid remainderthen it must be a prime number
  return true;
}

isPrime(5); // true
isPrime(6); //false
```
*Question: Write a function that returns all the prime factors of a number*
```javascript
function findPrimes(num) {
  var primes = [];
  var divisor = 2;
  
  while(num > 2) {
    // if the number is divisible by the divisor then store it in the array
    if(num % divisor === 0){
      primes.push(divisor);
    }
    else divisor++;
  }
  // return an array of all the prime factors 
  return primes;
}
findPrimes(12); //[2,2,3]
findPrimes(23); //[23]
```

*Question: Write a function that removes all duplicate numbers and sorts the array numerically*
```javascript
function removeDuplicate(arr) {
	var exists = {},
			outArr = [],
			elm;
	
	for(var i = 0; i<arr.length; i++) {
	  // store each number here temporarily
		elm = arr[i];
		
		// if the number ISN'T already there
		if(!exists[elm]) {
		  // put the new number into the final array
			outArr.push(elm);
			// mark that number so it skips it next time
			exists[elm] = true;
		}
	}
	// now use the sort method
	outArr.sort( function(a,b) {
	  // use a comparator or else it will return numbers lexicographically [1,11,2,245,3]
		return a - b;
	});
	
	return outArr;
 	
}

removeDuplicate([1,3,324,3,11,5,6,2,2,3,7,8,1]); // [1, 2, 3, 5, 6, 7, 8, 11, 324]
```

*Question: Write a function that merges 2 arrays and sorts the new array*
```javascript
function mergeAndSortArray(a, b){
  var merged = [], 
      aElm = a[0],
      bElm = b[0],
      i = 1,
      j = 1;
  
  // check for empty array
  if(a.length ==0) {
    return b;
  }

  // check for empty array
  if(b.length ==0) {
    return a;
  }
  
  // when either exist
  while(aElm || bElm) {
    
    // if only aElm exists OR is less than bElm
   if((aElm && !bElm) || aElm < bElm) {
     
     // insert aElm value into the array
     merged.push(aElm);
     
     // increment the value so you don't repeat it
     aElm = a[i++];
   } 
   // if bElm exists or is SMALLER than aElm  
   else {
     
     // insert bElm value into the array
     merged.push(bElm);
     
     // increment the value so you don't repeat it
     bElm = b[j++];
   }
  }
  // return the ne array, but first lets put the values in order
  return merged.sort( 
    // use a comparator to make it numerically ordered
    function(a,b) { 
      return a - b;
    });
}

mergeAndSortArray([5,777,3,3,4,8,9,1], [22,3,5,7,1,67]); // [1, 1, 3, 3, 3, 4, 5, 5, 7, 8, 9, 22, 67, 777]
```

*Question: Write a function that returns the nth fibonacci number*

```javascript
function fibSeq(num) {
  
  // start with the beginning sequence
  var fib = [0,1];
  
  // we don't even both with the first couple numbers
  if(num <= 2) {
    return 1;
  }
  
  // start 2 because of above and loop to the end of the number
  for(var i = 2; i <= num; i++) {
  
    // the bread and butter of a fibonacci sequence
    // it's always ((current number) - 1) + ((current number) - 2)
    fib[i] = fib[i-1] + fib[i-2];
  }
  return fib[num];
}
fibSeq(10); // 55
```

Now do the fibonaci sequence recursively.
```javascript
function fibSeq(num) {
 
 if(num < 2) {
  return 1;
 }
 else {
  return fibSeq(num - 1) + fibSeq(num - 2);
 }
}
```
This one was tricky and took a bit to fully comprehend, but there is a great explaination on SO about this question
- src - http://stackoverflow.com/questions/8845154/how-does-the-the-fibonacci-recursive-function-work
 ```shell
 
        fibonacci(7)
        ____|_____
       |          |
 fibonacci(5)  fibonacci(6)
  ____|____     ____|_____
 |        |    |         |
fib(3)  fib(4) fib(4)   fib(5)

// each time the function is called, it goes back and runs through it incrementally getting smaller and smaller each time
// stops at 2 
```


*Question: Write a function that shuffles and array in place.*
```javascript

//Fisher–Yates shuffle

function shuffle(array) {
  var currentIndex = array.length;
  var temporaryValue;
  var randomIndex;

  // While there remain elements to shuffle
  while (currentIndex) {

    // Pick a remaining element at random
    randomIndex = Math.floor( Math.random() * currentIndex-- );

    // And swap it with the current element.
    temporaryValue = array[currentIndex];

    array[currentIndex] = array[randomIndex];

    array[randomIndex] = temporaryValue;
  }

  return array;
}

var arr = ["a","b","c","d","e"];

shuffle(arr);  // ["b", "a", "d", "c", "e"];

// source http://bost.ocks.org/mike/shuffle/
```

*Question: Write a funtion that can shuffle a deck of cards in a single riffle*

```javascript
/* For this experiment I will take an array of 52 numbers (the deck of cards) and shuffle them in a single rifle */

var deck = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52];

// First half of the deck
var half1 = deck.slice(0, deck.length/2);

// Second half of the deck
var half2 = deck.slice(26, deck.length);

var shuffled_arr_deck = half1.map(function (e, i) {
    return [half1[i], half2[i]];
});
var shuffled_deck = shuffled_arr_deck.toString().split(',').map(Number);

// shuffled_deck = [1, 27, 2, 28, 3, 29, 4, 30, 5, 31, 6, 32, 7, 33, 8, 34, 9, 35, 10, 36, 11, 37, 12, 38, 13, 39, 14, 40, 15, 41, 16, 42, 17, 43, 18, 44, 19, 45, 20, 46, 21, 47, 22, 48, 23, 49, 24, 50, 25, 51, 26, 52]

/* Check if the Deck is a single rifle*/
function is_single_riffle(half1, half2, shuffled_deck) {
  
  var card;
  var half1_index = 0;
  var half2_index = 0;
  var half1_max_index = half1.length - 1;
  var half2_max_index = half2.length - 1;
  
  for ( index in shuffled_deck ) {
    if ( half1_index <= half1_max_index && index == half1[half1_index + 1] ) {
      half1_index += 1;
    } else if ( half2_index <= half2_max_index && index == half2[half2_index + 1] ) {
      half2_index += 1;
    } else {
      return false;
    }
return true;
  }
}

```
