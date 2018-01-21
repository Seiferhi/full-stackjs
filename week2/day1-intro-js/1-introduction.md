# An Introduction To JavaScript

## What's JavaScript

* JavaScript is a high-level programming language.

* JavaScript is an interpreted
  - JavaScript code is run by the browser immediately.
  - JavaScript do not need to be compiled.


* JavaScript was initially created to “make webpages alive”.

* JavaScript programs are called scripts.

* They can be written right in the HTML and execute automatically as the page loads.

## What can in-browser JavaScript do?

For instance, in-browser JavaScript is able to:

* Send data to the server.

* Validate form inputs
  - example: make sure that the password has at least 8 characters.
  - exaple: make sure that the email is a valid email address.


* Animate some elements on the page.

* Respond to user actions such as
  - click on a menu to show sub-menu.
  - scroll the page to see more content.
  - write a comment on a blog post.

## What CAN’T in-browser JavaScript do?

* JavaScript’s abilities in the browser are limited for the sake of the user’s safety.

* The aim is to prevent an evil webpage from accessing private information.

* The examples of such restrictions are:
  - JavaScript on a webpage can not read/write files on the hard disk.
  - JavaScript programs can use the camera/microphone, but they require user’s explicit permission.


* Different tabs/windows generally do not know about each other.

## Summary

* JavaScript was initially created as a browser-only language, but now it is used in many other environments as well.

* At this moment, JavaScript has a unique position as the most widely-adopted browser language with full integration with HTML/CSS.

## Exercise

Where can a developer uses JavaScript other than the browserv?
Name at least three other environments.

Look at stackoverflow servey of last year and see where JavaScript is ranked among other programming languages?
Try to explain this ranking.

## Extra: JavaScript Engines

At present, JavaScript can execute not only in the browser, but also on the server, or actually on any device where there exists a special program called the JavaScript engine.

The browser has an embedded engine, sometimes it’s also called a “JavaScript virtual machine”.

Different engines have different `codenames`, for example:

* V8 – in Chrome and Opera.
* SpiderMonkey – in Firefox.
* There are other codenames like “Trident”, “Chakra” for different versions of IE, “ChakraCore” for Microsoft Edge, “Nitro” and “SquirrelFish” for Safari etc.

The terms above are good to remember, because they are used in developer articles on the internet. We’ll use them too. For instance, if “a feature X is supported by V8”, then it probably works in Chrome and Opera.


How engines work?

Engines are complicated. But the basics are easy.

1. The engine (embedded if it’s a browser) reads (“parses”) the script.
2. Then it converts (“compiles”) the script to the machine language.
3. And then the machine code runs, pretty fast.

The engine applies optimizations on every stage of the process. It even watches the compiled script as it runs, analyzes the data that flows through it and applies optimizations to the machine code based on that knowledge. At the end, scripts are quite fast.
