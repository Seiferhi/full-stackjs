# JS: Functions

## Question 1 - make changes to get the right display.

```javascript
function double() {
  return 2 * n
}

alert(double(3))
```

This should display **6**

```javascript
function square(n) {
  alert(n * n)
}

alert(square(3) === 9)
```

This should display **true**

```javascript
function getVectorSum(vector) {
  let sum = 0
  for(let elt of vector) {
    sum += vector
  }
  return sum
}

alert(getVectorSum(1,2,3))
```
This should display **66**

## Question 2 - Extend the program

```javascript
let discount = 0.5
let taxRate = 0.1

function computeItemPrice(cost) {
  return cost + (cost*taxRate)
}

function computeTotalPrice(prices) {
  let total = 0

  for(let price of prices) {
    total += computeItemPrice(price)
  }

  return total
}

alert(computeTotalPrice([10, 20, 30]))
```

1. what's the output of the following functions (don't run the code)

2. Write a function **computeDiscount** that takes a cost of type number and a discount amount (also number) and return the new price after discount.

3. use the **computeDiscount** with your **computeTotalPrice** function.

## Question 3 - Local / Outer variables

```javascript
let remainingLives = 3
let gameOver = false

function updateRemainingLives(score, newLife = false) {
  if (score === 0) {
    remainingLives -= 1
    let gameOver = true
  }

  if (newLife === true) {
    remainingLives += 1
  }
}

updateRemainingLives(0)
updateRemainingLives(0)
alert(remainingLives)
alert(gameOver)

updateRemainingLives(1)
updateRemainingLives(0)
alert(remainingLives)
alert(gameOver)

updateRemainingLives(0)
alert(remainingLives)
alert(gameOver)
```

1. Name the local variables for **updateRemainingLives** function.

2. Try to explain to predict the output of the above code.

3. Try to correct the behavior of the above code.

## Question 4 - Convert the following functions to arrow functions.

```javascript
function isValidInput(min=5, max=15, input) {
  let len = input.length
  if (len >= 5 && len <= 15) {
    return true
  } else {
    return false
  }
}

function areSamePassword(password, confirmPassword) {
  if (password.length !== confirmPassword.length) {
    return false
  } else if (password === confirmPassword) {
    return true
  }
  return false
}
```

## Question 5 - Write a test function for the following code.

```javascript
function isPalindrome(word) {
  let len = word.length - 1
  let middle = Math.floor((len + 1)/ 2)
  for(let i = 0; i < middle; i++) {
    if (word[i] !== word[len - i]) {
      return false
    }
  }

  return true
}
```
