# Logical operators

* There are three logical operators in JavaScript:
  - || (OR).
  - && (AND).
  - ! (NOT).

* They can be applied to values of any type, not only boolean.

## || (OR)

```javascript
result = a || b;
```

* `result` is true if `a` or `b` is true.
* `result` is false if `a` and `b` are false.

There are four possible logical combinations:

```javascript
alert( true || true );   // true
alert( false || true );  // true
alert( true || false );  // true
alert( false || false ); // false
```

* As we can see, the result is always true except for the case when both operands are false.

* If an operand is not boolean, then it’s converted to boolean for the evaluation.

* For instance, a number 1 is treated as true, a number 0 – as false:

```javascript
if (1 || 0) { // works just like if( true || false )
  alert( 'truthy!' );
}
```

Most of the time, OR || is used in an if statement.

For example:

```javascript
let hour = 9;

if (hour < 10 || hour > 18) {
  alert( 'The office is closed.' );
}
```

We can pass more conditions:

```javascript
let hour = 12;
let isWeekend = true;

if (hour < 10 || hour > 18 || isWeekend) {
  alert( 'The office is closed.' ); // it is the weekend
}
```

## OR seeks the first truthy value

```JavaScript
result = value1 || value2 || value3;
```

The OR "||" operator does the following:

* Evaluate operands from left to right.

* For each operand, convert it to boolean:
  - If the result is true, then stop and return the **original value of that operand**.
  - If all operands were falsy, return the **last operand**.

```javascript
alert( 1 || 0 ); // 1 (1 is truthy)
alert( true || 'no matter what' ); // (true is truthy)

alert( null || 1 ); // 1 (1 is the first truthy value)
alert( null || 0 || 1 ); // 1 (the first truthy value)
alert( undefined || null || 0 ); // 0 (all falsy, returns the last value)
```

That leads to some interesting usages compared to a “pure, classical, boolean-only OR”.

```javascript
let currentUser = null;
let defaultUser = "John";

let name = currentUser || defaultUser || "unnamed";

alert( name ); // selects "John" – the first truthy value
```

## && (AND)

```javascript
result = a && b;
```
* `result` is true if `a` and `b` are true.
* `result` is false if `a` or `b` is false.

```javascript
alert( true && true );   // true
alert( false && true );  // false
alert( true && false );  // false
alert( false && false ); // false
```

An example with if:

```javascript
let hour = 12;
let minute = 30;

if (hour == 12 && minute == 30) {
  alert( 'Time is 12:30' );
}
```

Just as for OR, any value is allowed as an operand of AND:

```javascript
if (1 && 0) { // evaluated as true && false
  alert( "won't work, because the result is falsy" );
}
```

## AND seeks the first falsy value

```javascript
result = value1 && value2 && value3;
```

The AND `"&&"` operator does the following:

* Evaluate operands from left to right.

* For each operand, convert it to a boolean:
  - If the result is false, stop and return the original value of that operand.
  - If all operands have were truthy, return the last operand.

Examples:

```javascript
// if the first operand is truthy,
// AND returns the second operand:
alert( 1 && 0 ); // 0
alert( 1 && 5 ); // 5

// if the first operand is falsy,
// AND returns it. The second operand is ignored
alert( null && 5 ); // null
alert( 0 && "no matter what" ); // 0
```

## ! (NOT)

```javascript
result = !value;
```

The operator accepts a single argument and does the following:

1. Converts the operand to boolean type: true/false.
2. Returns an inverse value.

For instance:

```javascript
alert( !true ); // false
alert( !0 ); // true
```

## Exercises

**What's the result of OR**

```javascript
alert( null || 2 || undefined );
```

**What's the result of OR'ed alerts?**

```javascript
alert( undefined || 2 || alert(3) );
```

**What is the result of AND?**

```javascript
alert( 1 && null && 2 );
```

**What is the result of AND'ed alerts?**

```javascript
alert( null && alert(2) );
```

**The result of OR AND OR**

```javascript
alert( null || 2 && 3 || 4 );
```

**Check the range between**

Write an “if” condition to check that age is between 14 and 90 inclusively.

“Inclusively” means that age can reach the edges 14 or 90.

**Check the range outside**

Write an if condition to check that age is NOT between 14 and 90 inclusively.

Create two variants: the first one using NOT !, the second one – without it.

**A question about "if"**

Which of these alerts are going to execute?

What will be the results of the expressions inside if(...)?

```javascript
if (-1 || 0) alert( 'first' );
if (-1 && 0) alert( 'second' );
if (null || -1 && 1) alert( 'third' );
```
