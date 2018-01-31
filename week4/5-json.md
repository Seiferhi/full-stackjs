# JSON methods, toJSON

* Suppose we have a javascript object and we want to convert it to a string.

```javascript
let user = {
  name: "John",
  age: 30,

  toString() {
    return `{name: "${this.name}", age: ${this.age}}`;
  }
};

alert(user); // {name: "John", age: 30}
```

* In the process of development:
  - new properties are added
  - old properties are renamed
  - old properties are removed

* Updating such **toString** every time can become a pain.

* There’s no need to write the code to handle all this. The task has been solved already using **JSON.stringify**.

## JSON.stringify

The JSON (JavaScript Object Notation) is a general format to represent values and objects.

It’s common to use JSON for data exchange between applications.

JavaScript provides methods:

* **JSON.stringify** to convert objects into JSON.
* **JSON.parse** to convert JSON back into an object.

```javascript
let student = {
  name: 'John',
  age: 30,
  isAdmin: false,
  courses: ['html', 'css', 'js'],
  wife: null
};

let json = JSON.stringify(student);

console.log(typeof json); // we've got a string!

console.log(json);
/* JSON-encoded object:
{
  "name": "John",
  "age": 30,
  "isAdmin": false,
  "courses": ["html", "css", "js"],
  "wife": null
}
*/
```

* The method **JSON.stringify(student)** takes the object and converts it into a string.

* The resulting json string is a called **JSON-encoded** or **serialized** or **stringified**.

* Please note that JSON-encoded object has several important differences from the object literal:

  - Strings use double quotes. No single quotes or backticks in JSON. So **'John'** becomes **"John"**.

  - Object property names are double-quoted also. That’s obligatory. So **age:30** becomes **"age":30**.



* Nested objects are supported and converted automatically.

```javascript
let meetup = {
  title: "Conference",
  room: {
    number: 123,
    participants: ["john", "ann"]
  }
};

alert( JSON.stringify(meetup) );
/* The whole structure is stringified:
{
  "title":"Conference",
  "room":{"number":23,"participants":["john","ann"]},
}
*/
```

## JSON.parse

* To **decode** a JSON-string, we need another method named **JSON.parse**.

let value = JSON.parse(str[, reviver]);

* str: JSON-string to parse.
* reviver: Optional function(key,value) that will be called for each (key,value) pair and can transform the value.

```javascript
let user = '{ "name": "John", "age": 35, "isAdmin": false, "friends": [0,1,2,3] }';

user = JSON.parse(user);

alert( user.friends.length ); // 1
```

## Summary

* JSON is a data format that has its own independent standard and libraries for most programming languages.

* JSON supports plain objects, arrays, strings, numbers, booleans and null.

* JavaScript provides methods **JSON.stringify** to **encode** into **JSON**
* JavaScript provides **JSON.parse** to **decode** from **JSON**.

## Exercises

Search some use cases for JSON format and cite 3 here (Mr Google is your friend)

<hr>

1. Try to predict the output of the following code.

2. After running the code try to explain its behavior.

```javascript
let server = {
  address: '127.0.0.1',
  software: 'node'
}
console.log(JSON.stringify(server))

let client = {
  address: '127.0.0.1',
  software: ['react', 'react-router', 'redux']
  mode: null,
  version: undefined
}
console.log(JSON.stringify(client))

let secretName = Symbol('secret-agent')
let person = {
  name: 'adam',
  [secretName]: 'CAI-AGENT-007'
  sayHi() {
    alert(`my name is: ${this.name}`)
  }
}
console.log(JSON.stringify(person))
```

<hr>

1. What's wrong with the following json? make the neccessairy corrections so they are valid json.

2. What's a valid json?

```javascript
// case 1
{
  name: "JavaScript",
  inventor: "Branden eich"
}

// case 2
{
  'name': "JavaScript",
  'inventor': "Branden eich"
}

// case 3
{
  "languages" : ["JS", "Python"],
  "dynamic": true
  "multi-paradignm": true
}

// case 4
['1', '2', '3']

// case 5
`JavaScript is awesome`

// case 6
7

// case 7
True

// case 8
[true, 1, false, "hello", undefined, null]
```
