## Browser environment

* The JavaScript language evolved and became a language with many uses and platforms.

* A platform may be either
  - A browser.
  - A web-server.
  - An washing machine or another host.

* Each of them provides platform-specific functionality.

Here’s a bird’s-eye view of what we have when JavaScript runs in a web-browser:

<p align="center">
  <img src="../resources/images/window-objects.png">
</p>

## Document Object Model (DOM)

* The Document Object Model is a programming interface for `HTML`

* Developers use the DOM built-in functions to:
  - Create **HTML** elements from **JavaScript**.
  - Add an **HTML** element to the web page.
  - Update the content of an **HTM** element.
  - Delete and **HTML** element from the web page.

```javascript
// change the background color to red
document.body.style.background = "red";

// change it back after 1 second
setTimeout(() => document.body.style.background = "", 1000);
```

Here we used **document.body.style**, but there’s much, much more.

## BOM (part of HTML spec)

Browser Object Model (BOM) are additional objects provided by the browser (host environment) to work with everything **except** the document.

* `navigator` object provides background information about the browser and the operating system.
  - `navigator.userAgent` – information about the current browser.
  - `navigator.platform` – information about the platform (can help to differ between Windows/Linux/Mac etc).


* `location` object allows to read the current URL and redirects the browser to a new one.

```javascript
alert(location.href); // shows current URL
if (confirm("Go to wikipedia?")) {
  location.href = "https://wikipedia.org"; // redirect the browser to another URL
}
```

* Functions **alert/confirm/prompt** are also a part of BOM

## Summary

Talking about standards, we have:

<strong>DOM specification</strong>
Describes the document structure, manipulations and events, see https://dom.spec.whatwg.org.

<strong>HTML specification</strong>
Describes HTML language (tags etc) and also BOM (browser object model) – various browser functions: setTimeout, alert, location and so on, see https://html.spec.whatwg.org. It takes DOM specification and extends it with many additional properties and methods.

Now we’ll get down to learning DOM, because the document plays the central role in the UI, and working with it is the most complex part.

## Exercises

1. User the function setTimeout that display a message to the user after 3 seconds

2. Using the navigator object create a web page that display some informations about the navigator and the user's operating system.

3. Using the setInerval function create a web page that display a count down timer.
