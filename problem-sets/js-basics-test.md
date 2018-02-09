# Full Stack JavaScript
The goal of these exercises is to make sure that you understand the
fundamentals of JavaScript, DOM and AJAX.

Feel free to look for any JavaScript syntax reference, but try to solve the problems without googling for solutions.

These exercise make part of your learning experience and will help you deepen your understanding of JavaScript, DOM and AJAX.

Therefore we encourage you to block in advance at least 2 hours of your time.

## JavaScript - Part I

**Exercise 1 - data types**

JavaScript has 7 data types (sting, number, boolean, null, undefined, symbol).

Using `typeof` operator write a function `isOfType` that performs the following checks.

```javascript
let isOfType = (data, type) => {
  // your code here
}

console.log(isOfType('hello', 'string'))  // true
console.log(isOfType('123', 'number'))    // false
console.log(isOfType(13.4, 'number'))     // true
console.log(isOfType('True', 'boolean'))  // false
console.log(isOfType(false, 'boolean'))   // true
console.log(isOfType(null, 'null'))       // true !! (let's fix JavaScript ^_^)
console.log(isOfType(undefined, 'undefined')) // true
console.log(isOfType(()=>{}, 'function'))     // true
console.log(isOfType(function() {}, 'function')) // true
console.log(isOfType(isOfType, 'function'))      // false
console.log(isOfType([2,7], 'array'))            // false
console.log(isOfType({}, 'object'))              // false
console.log(isOfType('{}', 'object'))            // false
console.log(isOfType(Symbol('id'), 'symbol'))    // false
```

**Exercise 2 - loops**

Write a function **printTrianle** that makes **7** calls to **console.log**
to output the following triangle:

```code
#
##
###
####
#####
######
#######
```

Re-write the previous function so that it makes **n** calls to **console.log**.
(**n** is the argument of the function)

**Optional Exercise - loops**

Write a function **printChessBoard** that creates a string that represents an **8×8** grid,

using newline characters **\n** to separate lines.

At each position of the grid there is either a **space** or a **"#"** character.
The characters should form a chess board.

Passing this string to **console.log** should show something like this:

```code
 # # # #
# # # #
 # # # #
# # # #
 # # # #
# # # #
 # # # #
# # # #
```

Re-write the previous function so that it prints **n×n** grid where **n** is the function argument.

**Exercise 3 - functions**

Write a **range** function that takes two arguments, **start** and **end**,
and returns an array containing all the numbers from **start** up to (and including) **end**.

```javascript
function range(start, end) {
  // your code goes here
}

console.log(range(1,3)) // [1, 2]
console.log(range(5,9)) // [5, 6, 7, 8]
```

Write a **sum** function that takes an array of numbers and returns the sum of these numbers.

```javascript
function sum(list) {
  // your code goes here
}

console.log(sum([1,3])) // 4
console.log(sum([5,9, 10])) // 24
```

**Exercise 4 - functions**

Write a function **reverseArray** that takes an array as argument and produces
an new array that has the same elements in the order reversed.

Do not use the standard **reverse** method!

```javascript
function reverseArray(list) {
  // your code goes here
}

let letters = ['A', 'B', 'C']
let lettersReversed = reverseArray(['A', 'B', 'C'])
console.log(lettersReversed) // ['C', 'B', 'A']
console.log(letters === lettersReversed) // false
```

Write a function **reverseArrayInPlace** that takes an array as argument
then reverses it's elements in place. (modify the argument array)

Do not use the standard **reverse** method!

```javascript
function reverseArrayInPlace(list) {
  // your code goes here
}

let letters = ['A', 'B', 'C']
let lettersReversed = reverseArray(['A', 'B', 'C'])
console.log(lettersReversed) // undefined
console.log(letters) // ['C', 'B', 'A']
```

**Exercise 5 - functions (local, global variables)**

For each the following code snippets try to identify the **global** and **local** variables.


**snippet1**
```javascript
let cardNumber = '0011125';
let isValid = false;

function validate(threshold) {
  if (typeof cardNumber === 'string') {
    return cardNumber.length > threshold;
  }
  return false;
}
```
**snippet2**
```javascript
const DEFAULT_TYPE = 'div'
let elt = {
  classNames: ['active', 'li-item'],
  type: 'li',
  text: 'hello all'
}

etl.createDom = function() {
  let type = this.type || DEFAULT_TYPE
  if (!this.dom) {
    this.dom = document.createElement(type)
  }
}

function append(parent, child) {
  parent.append(child)
}

elt.append = append
```

**snippet 3**
```javascript
let submitBtn = $('.submit-btn')
let searchTerm = $('.search-input').val()
const BASE_URL = 'https://google.com/'

function fetchData(e) {
  e.preventDefault()
  let searchResults = $('.search-results')
  function displayData(data) {
    searchResults.append(data)
  }

  let url = `BASE_URL?q=${searchTerm}`
  fetch(url)
    .then(result => result.json())
    .then(displayData)
}

submitBtn.addEventListener('click', fetchData)
```

**Exercise 6 - Higher order functions**

A function that takes other functions as argument is called a **higher order function**.

Write the function **summation(n, term)** that returns
the sum **term(1) + term(2) + ... + term(n)**.

```javascript
function summation(n, term) {
  // your code goes here
}
let identity = k => k
let square = n => n*n
let double = n => 2*n

console.log(summation(3, identity)) // 6 = 1 + 2 + 3
console.log(summation(3, square))   // 14 = 1*1 + 2*2 + 3*3
console.log(summation(3, double))   // 12 = 2*1 + 2*2 + 2*3
```

Write a function **product(n, term)** that returns the product
**term(1) * term(2) + ... + term(n)**.

```javascript
function product(n, term) {
  // your code goes here
}
let identity = k => k
let square = n => n*n
let double = n => 2*n

console.log(product(3, identity)) // 6 = 1 * 2 * 3
console.log(product(3, square))   // 14 = (1*1) * (2*2) * (3*3)
console.log(product(3, double))   // 12 = (2*1) * (2*2) * (2*3)
```

Using the **product(n, term)** function write a **factorial(n)** function.
