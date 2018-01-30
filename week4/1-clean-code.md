# Clean Coding Best Practices

* Writing clean code is what you must know and do in order to call yourself a professional developer.

> “Even bad code can function. But if the code isn’t clean, it can bring a development organization to its knees.” — Robert C. Martin (Uncle Bob)

## what does clean coding mean?

Clean coding means that you **write code for your later self and for your co-workers and not for the machine**.

## How should I name my variables?

* Use names that **describe** the content of the variable.

* If you follow this practice, your names become **searchable**.

```javascript
// DON'T
let d
let elapsed
const ages = arr.map((i) => i.age)

// DO
let daysSinceModification
const agesOfUsers = users.map((user) => user.age)
```

* **make meaningful distinctions** and **don't add extra, unnecessary nouns**.

```javascript
// DON'T
let nameString
let theUsers

// DO
let name
let users

// DON'T
let fName, lName
let cntr

let full = false
if (cart.size > 100) {
  full = true
}

// DO
let firstName, lastName
let counter

const MAX_CART_SIZE = 100
// ...
const isFull = cart.size > MAX_CART_SIZE
```

## How should I write my functions?

* Your functions should do one thing only.

> Functions should do one thing. They should do it well. They should do it only. — Robert C. Martin (Uncle Bob)

```javascript
let users = [
  {name:'userA', scores:[1,2,3]},
  {name:'userB', scores:[4,5,6]},
  {name:'userC', scores:[7,8,9]},
  {name:'userD', scores:[1,2,3]}
]

function total(userName) {
  let userScores
  for(let i = 0; i < users.length; i++) {
    if (users[i].name === userName) {
      userScores = users[i].scores
      break
    }
  }

  let totalScore = 0
  for (let i = 0; i < userScores.length; i++) {
    totalScore += userScores[i]
  }

  return totalScore
}
```

What wrong with above code?

* does the **function name** help you understand what it's supposed to do?

* Does the function do one and only one thing?

Let's give the function a **meaningful name**.

```javascript
...
function computeTotalScore(userName) {
  ...
  return totalScore
}
```

* The function is doing so much let's split it.

```javascript
...
function getUserScore(userName) {
  let userScores
  for(let i = 0; i < users.length; i++) {
    if (users[i].name === userName) {
      userScores = users[i].scores
      break
    }
  }
  return userScores
}

function computeTotalScore(userName) {
  let userScores = getUserScore(userName)
  let totalScore = 0

  for (let i = 0; i < userScores.length; i++) {
    totalScore += userScores[i]
  }

  return totalScore
}
```

* let's refactor the **getUserEmail** function

```javascript
function getUserScore(userName) {
  let userScores
  for(let user of users) {
    if (user.name === userName) {
      userScores = user.scores
      break
    }
  }
  return userScores
}
```

* This looks much better, but we can use some **array built-in** functions.

```javascript
function getUserScore(userName) {
  let user = user.find(function(user) {
    return user.userName === userName
  })
  return user.scores
}
```

* Lets try to improve computeTotalScore with **array built-in** functions

```javascript
function computeTotalScore(userName) {
  let userScores = getUserScore(userName)
  let totalScore = userScores.reduce(function(score, accum) {
    return score + accum
  }, 0)

  return totalScore
}
```

* So let's see the code after the improvements.

```javascript
let users = [
  {name:'userA', scores:[1,2,3]},
  {name:'userB', scores:[4,5,6]},
  {name:'userC', scores:[7,8,9]},
  {name:'userD', scores:[1,2,3]}
]

function getUserScore(userName) {
  let user = users.find(function(user) {
    return user.name === userName
  })
  return user.scores
}

function computeTotalScore(userName) {
  let userScores = getUserScore(userName)
  let totalScore = userScores.reduce(function(score, accum) {
    return score + accum
  }, 0)

  return totalScore
}
```

* Functions are actions.

* A function's name is usually a verb.

* A function's name should be brief.

* A function's name should be as accurately as possible describe what the function does.

## Exercises

Improve the following code, according to the above guide-lines.

```javascript
let users = [
  {name: 'userA', scores: [1, 2, 3], bonus: [0.7], premium: false},
  {name: 'userB', scores: [4, 5, 6], bonus: [0.3, 0.2], premium: true},
  {name: 'userC', scores: [7, 8, 9], bonus: [0.9, 0.2, 0.5], premim: false},
  {name: 'userD', scores: [1, 2, 3], bonus: [], premim: false}
  {name: 'userE', scores: [1, 2, 3], bonus: [0.1, 0.1, 0.5, 0.8], premium: true},
  {name: 'userF', scores: [4, 5, 6], bonus: [0.3, 0.2], premium: false},
  {name: 'userG', scores: [7, 8, 9], bonus: [0.9, 0.2, 0.5], premium: true}
]

function bonusToScore(users) {
  let someUsers = []
  for (let user of users) {
    if (user.premium === true) {
      someUsers.push(user)
    }
  }

  for (let user of someUsers) {
    let userbonus = 0
    for (let bonus in user.bonus) {
      userbonus += bonus
    }

    if (userbonus > 10) {
      user.scores.push(10)
      user.bonus = [userbonus % 10]
    } else {
      user.score.push(userbonus)
      user.bonus = []
    }
  }
}
```
