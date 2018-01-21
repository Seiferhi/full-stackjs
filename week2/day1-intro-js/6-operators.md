## Operators

* Many operators are known to us from school:
  - addition `+`,
  - multiplication `*`,
  - subtraction `-` and so on.


## Strings concatenation, `+`

* Usually the plus operator `'+'` sums numbers.

* If the `+` is applied to strings, it concatenates them:

```javascript
let s = "my" + "string";
alert(s); // mystring
```

* If any of operands is a string, then the other one is converted to a string too.

```javascript
alert( '1' + 2 ); // "12"
alert( 2 + '1' ); // "21"
```

## Remainder `%`

* `a % b` is the remainder of the integer division of `a` by `b`.

```javascript
alert( 5 % 2 ); // 1 is a remainder of 5 divided by 2
alert( 8 % 3 ); // 2 is a remainder of 8 divided by 3
alert( 6 % 3 ); // 0 is a remainder of 6 divided by 3
```

## Exponentiation `**`

For a natural number b, the result of `a ** b` is `a` multiplied by itself `b` times.

```javascript
alert( 2 ** 2 ); // 4  (2 * 2)
alert( 2 ** 3 ); // 8  (2 * 2 * 2)
alert( 2 ** 4 ); // 16 (2 * 2 * 2 * 2)
```

## Increment/decrement

* **Increment** `++` increases a variable by 1:

```javascript
let counter = 2;
counter++;      // works same as counter = counter + 1, but shorter
alert( counter ); // 3
```

* **Decrement** `--` decreases a variable by 1:

```javascript
let counter = 2;
counter--;      // works same as counter = counter - 1, but shorter
alert( counter ); // 1
```

## Modify-in-place

* We often need to apply an operator to a variable and store the new result in it.

```javascript
let n = 2;
n = n + 5;
n = n * 2;
```

This notation can be shortened using operators `+=` and `*=`:

```javascript
let n = 2;
n += 5; // now n = 7 (same as n = n + 5)
n *= 2; // now n = 14 (same as n = n * 2)

alert( n ); // 14
```

* Short “modify-and-assign” operators exist for all arithmetical operators: `/=`, `-=` etc.

## Summary

* `+` for numbers does exactly what's expected.
  - `1 + 2 === 3`, is true

* `+` for strings behaves as a concatenation operator.
  - `"hey !" + " you" === "hey ! you"`

* `+` for numbers and strings bahaves as a concatenation operator.
  - `"the number is: " + 42 === "the number is: 42"`, is true.

* `-, *, **, /, %` for numbers bahaves as expected.
  - `2 ** 3 === 8`, is true
  - `12 % 5 === 2`, is true

* `-, *, **, /, %` for numbers and strings do the following:
  - Try to convert the argument string to number
  - If the conversion returns a valid number, return the result
  - If the conversion returns `NaN`, the result is`NaN`
