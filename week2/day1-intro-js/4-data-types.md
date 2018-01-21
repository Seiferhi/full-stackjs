# Data types

* A variable in JavaScript can contain any data.

* A variable can at one moment be a string and later receive a numeric value

```javascript
// no error
let message = "hello";
message = 123456;
```

* Programming languages that allow such things are called “dynamically typed”

* There are seven basic data types in JavaScript.

## A number

```javascript
let n = 123;
n = 12.345;
```

* The number type serves both for integer and floating point numbers.

* Besides regular numbers, there are  “special numeric values” which also belong to the `number` type: `Infinity`, `-Infinity` and `NaN`.

* `Infinity` represents the mathematical Infinity.

```javascript
alert( 1 / 0 ); // Infinity
```

* `NaN` represents a computational error.

```javascript
alert( "not a number" / 2 ); // NaN, such division is erroneous
```

* Special numeric values formally belong to the `“number”` type.

## A string

A string in JavaScript must be quoted.

```javascript
let str = "Hello";
let str2 = 'Single quotes are ok too';
let phrase = `can embed ${str}`;
```

In JavaScript, there are 3 types of quotes.

1. Double quotes: `"Hello"`.
2. Single quotes: `'Hello'`.
3. Backticks: <strong>\`Hello\`</strong>.

* **Double** and **single** quotes are “simple” quotes.

* **There’s no difference between them in JavaScript**.

* `Backticks` allow us to embed variables and expressions into a string by enclosing them in `${…}`.

```javascript
let name = "John";

// embed a variable
alert( `Hello, ${name}!` ); // Hello, John!

// embed an expression
alert( `the result is ${1 + 2}` ); // the result is 3
```

* First, the expression inside `${ ... }` is evaluated.

* Second, the result becomes a part of the string.

* We can put anything inside `${ ... }`:
  - A variable like **account**, `${account}`.
  - An arithmetical expression like **1 + 2**, `${1 + 2}`.
  - A function call like `${getUsername()}`

**Please note that this can only be done in backticks. Other quotes do not allow such embedding!**

```javascript
alert( "the result is ${1 + 2}" ); // the result is ${1 + 2} (double quotes do nothing)
```

**There is no character type.**

## A boolean (logical type)

* The boolean type has only two values: `true` and `false`.

```javascript
let nameFieldChecked = true; // yes, name field is checked
let ageFieldChecked = false; // no, age field is not checked
```

* Boolean values also come as a result of comparisons:

```javascript
let isGreater = 4 > 1;

alert( isGreater ); // true (the comparison result is "yes")
```

## The `null` value

* `null` forms a separate type of its own, which contains only the `null` value:

```javascript
let age = null;
```

* The code above states that the age is unknown or empty for some reason.

It’s a special value which has meaning of “nothing”, “empty” or “value unknown”.

## The `undefined` value

* `undefined` makes a type of its own.

* The meaning of `undefined` is “value is not assigned”.

* If a variable is declared, but not assigned, then its value is  `undefined`:

```javascript
let x;

alert(x); // shows "undefined"
```

* Normally, we use `null` to write an “empty” or an “unknown” value into the variable

* Normally `undefined` is only used for checks, to see if the variable is assigned or similar.

## A Symbol

* The `symbol` type is used to create unique identifiers for objects.

* We study them after objects.

## An object

* All other types are called “primitive”, because their values can contain only a single thing (be it a string or a number or whatever).

* In contrast, objects are used to store collections of data

* Arrays and functions are objects in JavaScript

## Summary

There are 7 basic types in JavaScript.

* Primitive data types:
  - `number` for numbers of any kind: integer or floating-point.
  - `string` for strings. A string may have one or more characters, there’s no separate single-character type.
  - `boolean` for true/false.
  - `null` for unknown values – a standalone type that has a single value null.
  - `undefined` for unassigned values – a standalone type that has a single value undefined.
  - `symbol` for unique identifiers.

* Object data types
  - `function` is an object type.
  - `array` is an object type.

## Exercises

Try to predict the result of the following operations.

```javascript
let name = "javascript";
let description = "more than a programming language"

alert(name + " " + description)
alert(`${name.toUpperCase()}`)
alert(`${description.toUpperCase()}`)
alert(`${name.toUpperCase() + ' ' + description.toUpperCase()}`)

let piEstimate = 3.14
let PI = Math.PI
let radius = 15

alert( `an estimatoin of Pi: ${piEstimate}` );
alert(`a more accurate estimation of Pi: ${PI}`)
alert(`the circumference is ${2 * PI * radius}`)
```
