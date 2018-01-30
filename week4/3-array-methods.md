# Array methods

Arrays provide a lot of methods.

We can use array methods to
  - search for an element.
  - serach fo the index of an element.
  - apply a function to all array elements.
  - reduce all elements inside an array to a single value.

## Add/remove items

* **arr.push(...items)** – adds items to the end.
* **arr.pop()** – extracts an item from the end.

```javascript
let notes = [15, 17, 18]

notes.push(17)
alert(notes) // [15, 17, 18, 17]

notes.pop(17)
alert(notes) // [15, 17, 18]
```

## slice

```javascript
arr.slice(start, end)
```

It returns a new array where it copies all items start index **"start"** to **"end"** (not including **"end"**).

```javascript
let str = "test";
let arr = ["t", "e", "s", "t"];

alert( str.slice(1, 3) ); // "es"
alert( arr.slice(1, 3) ); // ["e","s"]
```

## concat

The method **arr.concat** joins the array with other arrays and/or items and return the resulting array.

For instance:

```javascript
let arr = [1, 2];

// merge arr with [3,4]
let resultA = arr.concat([3, 4]);
alert( resultA ); // [1,2,3,4]
alert( arr); // [1, 2]

// merge arr with [3,4] and [5,6]
let resultB = arr.concat([3, 4], [5, 6]);
alert( resultB ); // [1,2,3,4,5,6]
alert( resultB );
```
