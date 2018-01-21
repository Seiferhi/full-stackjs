# Introduction

* In this article we introduce the `script` tag.

* The `script` tag is used to inject JavaScript in a web page.

## The `script` tag

* JavaScript programs can be inserted in any part of an HTML document with the help of the `<script>` tag.

```html
<!DOCTYPE HTML>
<html>

<body>

  <p>Before the script...</p>

  <script>
    alert( 'Hello, world!' );
  </script>

  <p>...After the script.</p>

</body>

</html>
```

The `<script>` tag contains JavaScript code which is automatically executed when the browser meets the tag.

## External scripts

If we have a lot of JavaScript code, we can put it into a separate file.

The script file is attached to HTML with the `src` attribute:

```JavaScript
<script src="/path/to/script.js"></script>
```

* `/path/to/script.js` is an absolute path to the file with the script (`https://mywebsite.com/path/to/script.js`).

* It is also possible to provide a path relative to the current page. For instance, `src="script.js"` would mean a file `"script.js"` in the current folder.

We can give a full URL as well, for instance:

```JavaScript
<script src="https://cdnjs.cloudflare.com/ajax/libs/lodash.js/3.2.0/lodash.js"></script>
```

To attach several scripts, use multiple tags:

```JavaScript
<script src="/js/script1.js"></script>
<script src="/js/script2.js"></script>
…
```
* Only the simplest scripts are put into HTML.

* Complex scripts are put in separate files.

* The benefit of a separate file is that the browser will download it and then store in its cache.

* After this, other pages that want the same script will take it from the cache instead of downloading it.

* That saves traffic and makes pages faster.

## Summary

* We can use a `<script>` tag to add JavaScript code to the page.

* A script in an external file can be inserted with `<script src="path/to/script.js"></script>`.

## Exercises

<strong>Show an alert</strong>

Create a page that shows a message “I’m JavaScript!”.

Do it in a sandbox, or on your hard drive, doesn’t matter, just ensure that it works.

<hr>

<strong>Show an alert with an external script</strong>

Take the solution of the previous task Show an alert. Modify it by extracting the script content into an external file alert.js, residing in the same folder.

Open the page, ensure that the alert works.
