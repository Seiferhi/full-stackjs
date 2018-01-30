# Callback functions

In JavaScript functions can take other functions as parameters.

A **callback function** is a JavaScript function, passed to another function as parameter.

```javascript
function executor(callback) {
  return callback(5);
}

function square(n) {
  return n * n;
}

// square is the callback function
alert(executor(square))
```

## Why callbacks?

### 1. Orchestrate asynchronous actions

Suppose I request data from the server then update the user interface according to the incoming data.

```javascript
function fetchUser() {
  return {
    name: 'alpha'
  }
}

function updateUI(user) {
  let userElt = document.querySelector('.user-name')
  if (user) {
    userElt.textContent = user.name
  } else {
    userElt.textContent = 'anonymous'
  }
}

let user = getUser()
updateUI(user)
```

* In real situation fetching user data requires a call to the server which cannot be done in a synchronous way* (as done in the code above).

* Let' simulate a server call using the built-in function **setTimeout**

```javascript
function fetchUser() {
  let user = null;
  // simulate a delay using setTimeout function
  // user object will be available after 3 seconds
  setTimeout(function getUser() {
    user = {
      name: 'alpha'
    }
  }, 3000)

  return user
}

let user = fetchUser()
alert(user)
```

* Alert display **null**

* JavaScript will not wait inside the function for setTimeout to execute it's callback function **getUser**.

* after 3 seconds **getUser** will execute in the background.

**Callbacks to the rescue**!

```javascript
function fetchUser(callback) {
  // simulate a delay using setTimeout function
  // user object will be available after 3 seconds
  setTimeout(function getUser() {
    let user = {name: 'alpha'}
    // callback will be executed and user is defined :)
    callback(user)
  }, 3000)
}

// updateUI is a callback function.
fetchUser(updateUI)
```

### 2. Built-in functions take functions as parameters

* Array built-in functions: **map**, **filter**, **reduce**, etc take functions as parameter.

```javascript
let languages = ['javascript', 'python', 'julia']

// dont do this
let languages_uppercase = []
for (let lang of languages) {
  languages_uppercase.push(lang.toUpperCase())
}

// do this
let toUpperCase = (str) => str.toUpperCase()
let languages_uppercase = languages.map(toUpperCase)

// or do this
let languages_uppercase = languages.map((str) => str.toUpperCase())
```

## Exercises

```javascript
function execute(callbackA, callbackB, n) {
  let res = []
  if (typeof callbackA === 'function' && typeof callbackB === 'function') {
    // from 1 up to (n-1) call double if i is odd and triple
    // anotherwise and push the result into res
    return res
  }

  throw Error(`Expecting "callback" of type "function" got: ${typeof callback}`)
}

function double(n) {
  return 2 * n;
}

function triple(n) {
  return 3 * n
}

alert(execute(double, triple, 11))
```

<hr>

1. Try to call **execute** function in a way that do not throw an error.

2. Try to call **execute** function in a way that throw an error.
```javascript
function execute(callback, args=null) {
  if (typeof callback === 'function') {
    callback(args);
    return;
  }

  throw Error(`Expecting "callback" of type "function" got: ${typeof callback}`)
}
```

<hr>

```javascript

function all(predicate, arr) {
  // return true if all elements of the array statisfy the predicate
}

function isEven(n) {
  return n % 2 === 0
}

all(isEven, [4, 8, 12]) // true
all(isEven, [4, 8, 13]) // false
```
