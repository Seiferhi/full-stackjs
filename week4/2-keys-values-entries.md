# Object.keys, values, entries

For plain objects, the following methods are available:

* **Object.keys(obj)** – returns an array of keys.
* **Object.values(obj)** – returns an array of values.
* **Object.entries(obj)** – returns an array of [key, value] pairs.

For instance:

```javascript
let user = {
  name: "John",
  age: 30
};

console.log(Object.keys(user)) // ["name", "age"]
console.log(Object.values(user)) // ["John", 30]
console.log(Object.entries(user)) // [ ["name","John"], ["age",30] ]
```

Here’s an example of using **Object.values** to loop over property values:

```javascript
let user = {
  name: "John",
  age: 30
};

// loop over values
for (let value of Object.values(user)) {
  alert(value); // John, then 30
}
```

## Exercises

Sum the properties

Write the function **sumSalaries(salaries)** that returns the sum of all salaries using **Object.values** and the **for..of loop**.

If **salaries** is empty, then the result must be **0**.

```javascript
let salaries = {
  "John": 100,
  "Pete": 300,
  "Mary": 250
};

alert(sumSalaries({})); // 0
alert( sumSalaries(salaries) ); // 650
```

## Count properties

Write a function **count(obj)** that returns the number of properties in the object:

```javascript
let user = {
  name: 'John',
  age: 30
};

alert( count(user) ); // 2
```

Try to make the code as short as possible.
