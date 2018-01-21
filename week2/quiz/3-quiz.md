# JS Quiz

## DOM, true or false and explain

1. The document object gives access to the page content. We can change or create anything on the page using it.
2. The document object gives access to the page style. We can change or create anything on the stylesheet (css files) using it.
3. The document object is part of the JavaScript language core.
4. Developers use tools (ex: chrome dev tools) to inspect the document object and change it manually.

## BOM, true or false and explain

1. Browser Object Model (BOM) are additional objects provided by the browser (host environment) to work with everything except the document.
2. `navigator` is an object provided by the browser.
3. `navigator` object provides background information about the browser and the operating system.
4. `location` is an object provided by the browser.
5. `location` object allows to read the current URL and redirects the browser to a new one.

## What's the difference between the DOM and BOM?

## Draw the DOM tree that represent the following html page

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>From HTML to DOM</title>
  </head>
  <body>
    <header>
      <div class="logo">
        <img src="path/to/log.png" alt="react logo">
      </div>
      <nav>
        <ul>
          <ul>Get started</ul>
          <ul>Documentation</ul>
          <ul>Tutorial</ul>
        </ul>
      </nav>
    </header>
    <main>
      <article class="">
        <section>
          <p>
            blabla
          </p>
          <p>
            blabla
          </p>
        </section>
      </article>
      <aside class="">
        <div class="pub">
          <img src="path/to/pub.png" alt="">
        </div>
      </aside>
    </main>
  </body>
</html>
```

## using method on the `document` object, how to select:

1. the `head` element.
2. the `body` element.
3. the `header` element.
4. the `main` element.
5. the `img` element inside the `header` element.
6. the `img` element inside the `aside` element.
