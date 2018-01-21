# Type Conversions

* In many cases developers needs to convert data from one type to another.

* For Example all `HTML` input fileds read user input as string.

* Then it's the developer job to convert number fields (ex: number of items to buy) to the number type.

* Some built-in functions do implicit type conversion to their arguments, ex:
  - alert converts it's arguments to string
  - console.log converts it's arguments to string

## ToString

We can also use a call `String(value)` function for that:

```javascript
value = String(13.14); // now value is a string "13.14"
alert(typeof value); // string
```

* String conversion is mostly obvious.

* A `false` becomes `"false"`, `null` becomes `"null"` etc.

## ToNumber

* Numeric conversion happens in mathematical functions and expressions automatically.

* For example, when division `/` is applied to non-numbers:

```javascript
alert( "6" / "2" ); // 3, strings are converted to numbers
```

* We can use a `Number(value)` function to explicitly convert a `value`:

```javascript
let str = "123";
let num = Number(str); // becomes a number 123
alert(typeof num); // number
```

* If the string is not a valid number, the result of such conversion is `NaN`, for instance:

```javascript
let age = Number("an arbitrary string instead of a number");
alert(age); // NaN, conversion failed
```

Examples:

```javascript
alert( Number("   123   ") ); // 123
alert( Number("123z") );      // NaN (error reading a number at "z")
alert( Number(true) );        // 1
alert( Number(false) );       // 0
```

**concatenation of a number and a string**

```javascript
alert( 1 + '2' ); // '12' (string to the right)
alert( '1' + 2 ); // '12' (string to the left)
```

## ToBoolean

* Boolean conversion is the simplest one.

* Can be performed with the call of `Boolean(value)`.

The conversion rule:

* Values that are intuitively _“empty”_, like `0`, an `empty string`, `null`, `undefined` and `NaN` become `false`.

* Other values become true.

```javascript
alert( Boolean(1) ); // true
alert( Boolean(0) ); // false

alert( Boolean("hello") ); // true
alert( Boolean("") ); // false
```

## Summary

There are three most widely used type conversions: to string, to number and to boolean.

**ToString** – Occurs when we output something, can be performed with `String(value)`. The conversion to string is usually obvious for primitive values.

**ToNumber** – Occurs in math operations, can be performed with `Number(value)`.

The conversion follows the rules:

Value           |  becomes
----------------|----------
undefined       |  NaN
null            | 0
true and false  | 1 and 0
string          | Whitespaces from the start and the end are removed. Then, if the remaining string is empty, the result is 0. Otherwise, the number is “read” from the string. An error gives NaN.

**ToBoolean** – Occurs in logical operations, or can be performed with `Boolean(value)`.

Follows the rules:

Value                        |  becomes...
-----------------------------|--
0, null, undefined, NaN, ""  |  false
any other value              |  true

Most of these rules are easy to understand and memorize. The notable exceptions where people usually make mistakes are:

* `undefined` is `NaN` as a number, not `0`.

* `"0"` and space-only strings like `" "` are true as a boolean.

## Exercises

**Type conversions**

What are results of these expressions?

```javascript
"" + 1 + 0
"" - 1 + 0
true + false
6 / "3"
"2" * "3"
4 + 5 + "px"
"$" + 4 + 5
"4" - 2
"4px" - 2
7 / 0
"  -9\n" + 5
"  -9\n" - 5
null + 1
undefined + 1
```
