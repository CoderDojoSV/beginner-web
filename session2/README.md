# Build a web page, Lesson 2 – CSS

## Overview

Today's lesson is about
[Cascading Style Sheets](http://en.wikipedia.org/wiki/CSS),
more commonly known as CSS. We are going to use CSS to improve the _look
and feel_ of our stories.

### What is CSS?

CSS is a language that can be used to describe how HTML is supposed to look.
The important distinction here is that HTML structures the content,
while CSS controls how it looks.

Let's look at the difference. Here's the CSS from @jonmagic's story last week:

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

And the HTML:

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

When we combine them using JSFiddle, we get a page that looks like this:

![Story with CSS](https://dl.dropboxusercontent.com/u/4042186/lesson2-sample.png)

### How CSS Works

We can get an idea of what's happening by looking at each line of the CSS.

* For any ```<body>``` tags
    1. Use ```Arial``` as the font
    2. Set the background color to ```#eee``` (A ***hex color***)
    3. Set the foreground color to ```green```
* For any ```<img>``` tags
    1. Give it a ```2px``` wide, ```solid``` border and color it ```green```
    2. Give it ```2px``` of ***padding***

> ***hex color*** - A way to describe colors using
> [hex code](http://en.wikipedia.org/wiki/Hexadecimal). This is used a lot in
> CSS because it allows more specific color selection than just ```blue``` or
> ```green```. A hex color mixes red, green, and blue components. In CSS code,
> a hex color looks kind of like ```#RRGGBB``` or ```#RGB```. Using CodePen,
> we can press Alt to bring up a color picker that can help us find hex color
> codes.

Notice how we are modifying visual features with CSS. We wrote the story in
HTML, but we never mentioned ```green``` anywhere! Separating content from
presentation helps us stay focused and organized.

CSS follows a basic pattern. First, we select the HTML elements we want to
change the look of. Then, we say what aspects of their look we want to change.
Take this snippet for example:

```css
body {
  font-family: Arial;
  background-color: #eee;
  color: green;
}
```

We are selecting all ```<body>``` tags (We only have 1),
then saying we want to modify the font, background color, and foreground color.

The part that selects the tags is called the **selector**, and each modification
is called a **declaration**. A combination of a selector and any number
of declarations is called a **rule**. A CSS file can contain as many rules as
we want.

Let's break down the concepts of **selectors** and **declarations**.

## Selectors

So far we have seen selectors that find HTML elements by tag name.
CSS allows us to be much more flexible about targeting HTML elements to modify.
We can select using **classes**, **IDs**, and **parent-child relationships**.

### Classes

Every HTML tag can have a ```class``` attribute. Classes help us be more
specific than just tag names. Let's take our ```<ul>``` for example, and add
the class ```blue``` to the ```<li>``` tag that represent our favorite season.

```html
<ul>
    <li>spring</li>
    <li class="blue">summer</li>
    <li>fall</li>
    <li>winter</li>
</ul>
```

![.blue class example](https://dl.dropboxusercontent.com/u/4042186/lesson2-css1.png)

Using a class, we only changed the color of one season in the list!

The same class can be added to multiple tags in the page. Let's try adding the same blue class into our ```<h1>``` tag:

```html
<h1 class="blue">My Favorite Season</h1>
```

![multiple .blue class example](https://dl.dropboxusercontent.com/u/4042186/lesson2-css2.png)

### IDs

An ID is useful for when we want to give an element a specific name. IDs
are meant to be unique, so we aren't supposed to have two elements with the
same ID. That's what makes an ID different from a class.

Let's say we want to give our first ```<p>``` the ID ```intro```. We just add
the ```id``` attribute. Here's our new HTML:

```html
<p id="intro">Today, I'd like to share about my favorite season.</p>
```

In CSS, we target an ID using a hash mark ```#``` followed by the ID. Here's
our new CSS rule:

```css
#intro {
    font-weight: bold;
}
```

![#intro ID example](https://dl.dropboxusercontent.com/u/4042186/lesson2-css3.png)

**Protip!** Selecting by ID is faster for the browser to process than selecting
by class or tag name. Use IDs whenever you need to style just one element!

## Declarations

I have some good news for you... Selectors were the hard part, and declarations
are the fun part! Declarations are the style modifications we apply in each
CSS rule. There are two parts to each declaration: the **property** and the
**value**. The pattern is:

```property: value;```

### Properties

The properties we are able to modify with CSS are set by the web browser. A list
of most common ones can be found [here](http://www.w3schools.com/cssref/). A few
examples of CSS properties we have already seen are ```background-color```,
```font-family```, ```border```, and ```text-decoration```.

### Values

The values we can use are determined by the properties. For example, the
```width``` property can accept a size, and the ```background-color``` property
can accept a color. It wouldn't make much sense to say ```width: red;``` or
```background-color: 100px;``` would it? Check a
[reference guide](http://www.w3schools.com/cssref/) for help finding out which
values can go with which properties.

Here's a copy of the page so far on my jsfiddle:
[http://jsfiddle.net/r7T26/14/](http://jsfiddle.net/r7T26/14/)

## Next Lesson

Next week, we are going to look more deeply into the layout system and start
understanding how to arrange our pages in more dynamic ways! We're also
going to start looking at some common design patterns, and we'll learn how to
plan the layout of our page.