# The `typeof` operator

* The `typeof` operator returns the type of the argument.

* It supports two forms of syntax:

1. As an operator: `typeof x`.
2. Function style: `typeof(x)`.

* `typeof` works both with parentheses or without them.

* The call to `typeof x` returns a string with the type name:

```javascript
typeof undefined // "undefined"

typeof 0 // "number"

typeof true // "boolean"

typeof "foo" // "string"

typeof Symbol("id") // "symbol"

typeof Math // "object"  (1)

typeof null // "object"  (2)

typeof alert // "function"  (3)
```

The last three lines may need additional explanations:

1. `Math` is a built-in object that provides mathematical operations.

2. The result of `typeof null` is `"object"`, that’s an error in the language (yes language designers make errors too).

3. Explanation
  - The result of `typeof alert` is `"function"`, because alert is a function.
  - There’s no special `“function”` type in the language.
  - Functions belong to the object type.
  - Formally, it’s incorrect, but very convenient in practice.

## Exercises

Try to predict the type of the different expressions

```javascript
typeof 'hello world'
typeof 13.14
typeof (15 < 17)
typeof [1, 2, 3]
typeof Number('not a number')
typeof String(13.14)
typeof Math.pow(2, 4)
typeof `PI number: ${Math.PI}`
typeof Math
typeof (1 / 0)
typeof (0 / 1)
typeof NaN
typeof undefined
typeof null
```
