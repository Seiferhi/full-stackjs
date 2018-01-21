# JS Quiz

## What are the standard language of the web

1. HTML/CSS/JQuery
2. HTML/CSS/Python
3. HTML/CSS/JavaScript ✓
3. XHTML/CSS/Bootstrap

## True or False

1. JavaScript is an compiled language.
2. JavaScript is staticly typed language.
3. JavaScript is a markup language.
4. JavaScript is a scripting language. ✓
5. Before building a web application we need to install JavaScript in the browser.
6. Historically JavaScript was named LiveScript ✓
7. JavaScript is not the only programming language supported by default in major browsers. ✓

## true or false

1. JavaScript can be used to make web page interactive. ✓
2. JavaScript can be used to write an operating system.
3. JavaScript can be used to write a file system.
4. JavaScript can be used to write an online text editor. ✓
5. javascript can be used to build an e-commerce website. ✓
6. JavaScript can be used only in the browser.

## How to inject JavaScript file in a web page

1. Using a script tag ✓
```html
<script>
  console.log('JS is awesome')
</script>
```

2. Using code tag
```html
<code>
  console.log('JS is awesome')
</code>
```

3. We can use both the script and the code tags

## True of False.

1. It's recommended that you put your script tag in the head of your web page.

```html
  ...
  <head>
  ...
  ...
  <script src="path/to/javascript.js"></script>
  </head>
```

2. It's recommended that you put your script tag just before closing your body tag. ✓

```html
  ...
  <body>
  ...
  <script src="path/to/javascript.js"></script>
  </body>
```

## What is the output of the alert ?

```javascript
let name = "javascript";

alert( `hello ${name}` ); // hello javascript

alert( `hello ${name + " is awesome"}` ); // hello javascript is awesome

alert( `hello ${name} is awesome` ); // hello javascript is awesome

alert( `hello "${name.length}"` ); // hello "${name.length}"

alert( `hello ${name.length}` ); // hello 10

alert( `hello ${name.toUpperCase()}` ); // hello JAVASCRIPT
```

## What are the results of these expressions

```javascript
" 9 " + 1 - 1  // number: 90
" 9 " - 1 + 1 // number: 9

24 + 'px' // string: 24px
'px' + 24 // string: px24

true + false - true // number 0
false - false + true // number 1

null + 99 // number 99
99 + null // number 99

undefined + 14 // NaN
14 + undefined // NaN
```
