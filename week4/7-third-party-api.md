# What are third party APIs?

* Third party APIs are APIs provided by third parties.

* Generally companies such as Facebook, Twitter, or Google — to allow you to access their functionality via JavaScript and use it on your own site.

## An approach for using thrid party APIs

* We'll take you through an exercise to show you how to use the NYTimes API

* Here we give you a general set of steps to follow that you can use as an approach for working with most APIs.

## Step 1 - find the documentation

* When you want to use a third party API, it is essential to find out where the documentation is

* The New York Times API documentation is at https://developer.nytimes.com/.

## step 2 - get a developer key

* Most APIs require you to use some kind of developer key, for reasons of security and accountability.

* To sign up for an NYTimes API key, you need to go to https://developer.nytimes.com/signup.


1. Let's request a key for the "Article Search API" — fill in the form, selecting this as the API you want to use.
2. Next, wait a few minutes, then get the key from your email.
3. Create a new project folder and copy [nytimes.html](https://github.com/mdn/learning-area/blob/master/javascript/apis/third-party-apis/nytimes/nytimes_start.html) and [nytimes.css](https://github.com/mdn/learning-area/blob/master/javascript/apis/third-party-apis/nytimes/nytimes.css)

## Step 3 - connect the API to your application

* First, you'll need to make a connection between the API, and your app.

* This is usually done by making requests to the correct URL(s).

In the case of this API

1. Find the following line:
```javascript
var key = 'INSERT-YOUR-API-KEY-HERE';
```
Replace **INSERT-YOUR-API-KEY-HERE** with the actual API key you got in the previous section.

2. Add the following line to your JavaScript, below the **"// Event listeners to control the functionality"**
```javascript
searchForm.addEventListener('submit', fetchResults);
```

3. Now add the **fetchResults()** function definition, below the previous line.

```javascript
function fetchResults(e) {
  // Use preventDefault() to stop the form submitting
  e.preventDefault();

  // Assemble the full URL
  url = baseURL + '?api-key=' + key + '&page=' + pageNumber + '&q=' + searchTerm.value;

  if(startDate.value !== '') {
    url += '&begin_date=' + startDate.value;
  };

  if(endDate.value !== '') {
    url += '&end_date=' + endDate.value;
  };

}
```

So, a complete URL would end up looking something like this:

```code
https://api.nytimes.com/svc/search/v2/articlesearch.json?api-key=4f3c267e125943d79b0a3e679f608a78&page=0&q=cats
&begin_date=20170301&end_date=20170312
```

## Step 4 - Requesting data from the API

* Add the following code block inside the **fetchResults()** function

```javascript
// Use fetch() to make the request to the API
fetch(url).then(function(result) {
  displayResults(result.json);
});
```

## Step 5 - display the data
