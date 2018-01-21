# Loops: while and for

Loops are a way to repeat the same part of code multiple times.

## The “while” loop

The while loop has the following syntax:

```javascript
while (condition) {
  // code
  // so-called "loop body"
}
```

* While the **condition is true**, the code from the **loop body** is executed.

The loop below outputs **i** while **i < 3**:

```javascript
let i = 0;
while (i < 3) { // shows 0, then 1, then 2
  alert( i );
  i++;
}
```

The shorter way to write **while (i != 0)** could be **while (i)**:

```javascript
let i = 3;
while (i) { // when i becomes 0, the condition becomes falsy, and the loop stops
  alert( i );
  i--;
}
```

## The “for” loop

The for loop is the most often used one.

```javascript
for (begin; condition; step) {
  // ... loop body ...
}
```

* The loop below runs **alert(i)** for **i** from **0** up to (but not including) **3**:

```javascript
for (let i = 0; i < 3; i++) { // shows 0, then 1, then 2
  alert(i);
}
```

Let’s examine the for statement part by part:

**parts**

* begin 	i = 0 	Executes once upon entering the loop.

* condition 	i < 3 	Checked before every loop iteration, if fails the loop stops.

* step 	i++ 	Executes after the body on each iteration, but before the condition check.

* body 	alert(i) 	Runs again and again while the condition is truthy

The general loop algorithm works like this:

```code
Run begin
→ (if condition → run body and run step)
→ (if condition → run body and run step)
→ (if condition → run body and run step)
→ ...
```

**If you are new to loops, then maybe it would help if you go back to the example and reproduce how it runs step-by-step on a piece of paper.**

Here’s what exactly happens in our case:

```javascript
// for (let i = 0; i < 3; i++) alert(i)

// run begin
let i = 0
// if condition → run body and run step
if (i < 3) { alert(i); i++ }
// if condition → run body and run step
if (i < 3) { alert(i); i++ }
// if condition → run body and run step
if (i < 3) { alert(i); i++ }
// ...finish, because now i == 3
```

## Breaking the loop

* Normally the loop exits when the condition becomes falsy.

* We can force the exit at any moment. There’s a special break directive for that.

```javascript
let sum = 0;

while (true) {

  let value = +prompt("Enter a number", '');

  if (!value) break; // (*)

  sum += value;

}
alert( 'Sum: ' + sum );
```

* **break** directive is executed in the line (*) if the user enters an empty line or cancels the input.

* **break** stops the loop immediately, passing the control to the first line after the loop.

## Summary

We covered 3 types of loops:

* while – The condition is checked before running the while body.

* If we want to exit the loop immediately we can use **break** key word.

* for (;;) – The condition is checked before running the for body, additional settings available.

## Exercises

**Last loop value**

What is the last value alerted by this code? Why?

```javascript
let i = 3;

while (i) {
  alert( i-- );
}
```

**Which values shows the while?**

For every loop, write down which values it shows, in your opinion. And then compare with the answer.

Both loops alert same values or not?

1. increment then alert:

```javascript
let i = 0;
while (i < 5) {
  i += 1
  alert( i );
}
```

2. Write the equivalent **for loop** for the previous **while loop**.

**Which values get shown by the "for" loop?**

Write down which values the loop is going to show.
Then compare with the answer.

```javascript
for (let i = 0; i < 5; i++) {
  alert(2 * i);
}
```

Write the equivalent **while loop**.

**Output even numbers in the loop**

Use the for loop to output even numbers from 2 to 10.

**Replace "for" with "while"**

Rewrite the code changing the for loop to while without altering its behavior (the output should stay same).

```javascript
for (let i = 0; i < 3; i++) {
  alert( `number ${i}!` );
}
```

**Repeat until the input is correct**

Write a loop which prompts for a number greater than 100. If the visitor enters another number – ask him to input again.

The loop must ask for a number until either the visitor enters a number greater than 100 or cancels the input/enters an empty line.

Here we can assume that the visitor only inputs numbers. There’s no need to implement a special handling for a non-numeric input in this task.

**Output prime numbers**

An integer number greater than 1 is called a prime if it cannot be divided without a remainder by anything except 1 and itself.

In other words, n > 1 is a prime if it can’t be evenly divided by anything except 1 and n.

For example, 5 is a prime, because it cannot be divided without a remainder by 2, 3 and 4.

_Write the code which outputs prime numbers in the interval from 2 to n_.

For n = 10 the result will be 2,3,5,7.

P.S. The code should work for any n, not be hard-tuned for any fixed value.
