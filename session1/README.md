# Build a web page - HTML - Lesson 1

## Overview

Today we are going to use [HTML](http://en.wikipedia.org/wiki/HTML) to help us tell a story in the web browser that we can show our friends and family.

```html
<p>HTML is a markup language that we can use to add structure and formatting to our story in web browsers, like Safari or Chrome. When we use HTML to tell a story in the web browser, we are creating a web page.</p>
```

A web page is made up of many html elements, each a tag, or more commonly a set of tags, enclosed in angle brackets. The paragraph above is an example of how you mark a paragraph in html, by surrounding it in opening and closing `<p>` tags.

**Description**

To get started in web development we'll need to learn how to use html, so today we are going to:

* Start with a basic HTML template
* Tell our story and use HTML to add structure and formatting

**Demo**

This bit of code:

```
<!DOCTYPE html>
<html>
  <head>
  </head>
  <body>
   <h1>My Favorite Season</h1>
   <p>Today, I'd like to share about my favorite season.</p>
   <p>There are four seasons in a year.</p>
   <ul>
    <li>spring</li>
    <li>summer</li>
    <li>fall</li>
    <li>winter</li>
   </ul>
   <p>My favorite season is summer, because I can go to the beach with my family.</p>

   <img src="http://images.pinchit.com/deals/2012/04/16/012292aa53_1334616708_550.jpg" alt="">
    
   <p>Click <a href="http://baytobeachlife.files.wordpress.com/2013/02/male-sealion3-by-chris-parsons.jpg">here</a> to see my favorite sea animal.</p>   
  </body>
</html>
```

Will produce a web page that looks like this:

![demo](https://dl.dropboxusercontent.com/u/4042186/lesson1-sample.png)

Check out the [live demo](http://jsfiddle.net/jeeyun/r7T26/10/) to experiment yourself.

## Prerequisites

**Tools**

* [JSFIDDLE](http://jsfiddle.net/)

## Getting Started

To get started you should open a blank project on JSFIDDLE: [http://jsfiddle.net/](http://jsfiddle.net/)


JSFiddle already adds the opening and closing `<html>` tags, as well as the `<head>` and `<body>` tags in the resulting page. 

```html
<html>
  <head></head>
  <body></body>
</html>
```

The content inside the html window is assumed to be the `<body>` tag of the html page. The `<body>` tags tell the web browser that this part of the page should be rendered (displayed). 

## Telling Your Story

Now you can start telling your story by typing it inside of the html window! Here is an example of a header:

```html
<h1>My Favorite Season</h1>
```

[Basic demo of HTML in action](http://jsfiddle.net/jeeyun/r7T26/1/)

Now add some content to your story:

```html
<h1>My Favorite Season</h1>
Today, I'd like to share about my favorite season.
There are four seasons in a year.
```

[Telling more of the story](http://jsfiddle.net/jeeyun/r7T26/2/)

## Using Paragraphs

Here you can see that I separated my paragraphs using new lines (on the right) but the rendered html (on the left) didn't get separated into paragraphs. This is because I did not use HTML to add  paragraph (`<p>` tags) to my story.

Add the `<p>` around the paragraphs:

```html
<h1>My Favorite Season</h1>
<p>Today, I'd like to share about my favorite season.</p>
<p>There are four seasons in a year.</p>
```

[Adding paragraph tags](http://jsfiddle.net/jeeyun/r7T26/3/)

Now the paragraphs are displayed correctly!

## Lists

You can easily add a list to your story using `<ul>` and `<li>` tags. Here is an example:

```html
<h1>My Favorite Season</h1>
<p>Today, I'd like to share about my favorite season.</p>
<p>There are four seasons in a year.</p>
<ul>
    <li>spring</li>
    <li>summer</li>
    <li>fall</li>
    <li>winter</li>
</ul>
```

The `<ul>` tag tells the browser this is a list of items. The `<li>` tags are used around each list item.

[Story with list of seasons](http://jsfiddle.net/jeeyun/r7T26/5/)

If you want the list to use numbers instead of bullet points you can change the `<ul>` tag (unordered list) to an `<ol>` tag (ordered list).

```html
<h1>My Favorite Season</h1>
<p>Today, I'd like to share about my favorite season.</p>
<p>There are four seasons in a year.</p>
<ol>
    <li>spring</li>
    <li>summer</li>
    <li>fall</li>
    <li>winter</li>
</ol>
</html>
```

## Picture Time!

This story would be a lot more interesting with pictures! Adding a picture to our story is simple, we just use the `<img>` tag and tell it where our image is.

The `<img>` tag has an attribute called `src` and this is where we tell it the url to the image we want to use in our story. Here is an example `<img>` tag:

```html
<img src="http://f.cl.ly/items/2f473l1d233S0S1k3J3d/dogs-playing.jpg">
```

Adding this to our story is easy:

```html
<h1>My Favorite Season</h1>
<p>Today, I'd like to share about my favorite season.</p>
<p>There are four seasons in a year.</p>
<ul>
    <li>spring</li>
    <li>summer</li>
    <li>fall</li>
    <li>winter</li>
</ul>
<p>My favorite season is summer, because I can go to the beach with my family.</p>

<img src="http://images.pinchit.com/deals/2012/04/16/012292aa53_1334616708_550.jpg" alt="">
```


[Story with images](http://jsfiddle.net/jeeyun/r7T26/7/)



## Hyperlinks

One of the things that makes web pages so amazing for telling stories is you can **link** things together with other web pages on the internet and it is really easy to do!

In the pervious example I included three kinds of dogs that we saw at the park, now I'm going to use hyperlinks (the `<a>` tag) to link the dog names to their descriptions on Wikipedia.

The `<a>` tag has an attribute called `href` and we will set that attribute equal to the url of the web page we want to link to. Here is an example where I link the word Poodles to the web page about Poodles on Wikipedia:

```
<a href="http://en.wikipedia.org/wiki/Poodle">Poodles</a>
```

Here is what it looks like in the context of our story:

```html
<h1>My Favorite Season</h1>
<p>Today, I'd like to share about my favorite season.</p>
<p>There are four seasons in a year.</p>
<ul>
    <li>spring</li>
    <li>summer</li>
    <li>fall</li>
    <li>winter</li>
</ul>
<p>My favorite season is summer, because I can go to the beach with my family.</p>

<img src="http://images.pinchit.com/deals/2012/04/16/012292aa53_1334616708_550.jpg" alt="">
    
<p>Click <a href="http://baytobeachlife.files.wordpress.com/2013/02/male-sealion3-by-chris-parsons.jpg">here</a> to see my favorite sea animal.</p> 
```


## Style

In the next lesson we will start learning how to add style to our story using html attributes and css. Here is an example to help get you excited about the next lesson.

In JSFiddle we want to paste the following css code into the CSS box:

```css
body {
  font-family: Arial;
  background-color: #eee;
  color: green;
}

img {
  border: 2px solid green;
  padding: 2px;
}
```

[Story with CSS](http://jsfiddle.net/jeeyun/r7T26/11/)

## Advanced Topics

### HTML Doctype

Web browsers look for a document type tag at the beginning of an HTML document in order to determine how they should read and render the HTML. We can add the `<!DOCTYPE html>` tag to our web page to tell browsers that we are using the latest version of HTML.

```html
<!DOCTYPE html>
<html>
  <head>
  </head>
  <body>
   <h1>My Favorite Season</h1>
   <p>Today, I'd like to share about my favorite season.</p>
   <p>There are four seasons in a year.</p>
   <ul>
    <li>spring</li>
    <li>summer</li>
    <li>fall</li>
    <li>winter</li>
   </ul>
   <p>My favorite season is summer, because I can go to the beach with my family.</p>

   <img src="http://images.pinchit.com/deals/2012/04/16/012292aa53_1334616708_550.jpg" alt="">
    
   <p>Click <a href="http://baytobeachlife.files.wordpress.com/2013/02/male-sealion3-by-chris-parsons.jpg">here</a> to see my favorite sea animal.</p>   
  </body>
</html>
```
You can read more about document type [here](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Introduction_to_HTML5).

## Other Resources

* [HTML Glossary](http://www.codecademy.com/glossary/html)
* [Mozilla Developer Network](https://developer.mozilla.org/en-US/)
