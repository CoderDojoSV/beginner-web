Lesson 3 - Advanced CSS
============================

## Overview
Last week we learned a bit about [Cascading Style Sheets](http://en.wikipedia.org/wiki/CSS) (CSS for short). Today we're going to dig back in and learn some advanced CSS tactics to really make our page look awesome!

## Recap
Last week we learned about a few things...

### Selectors - Classes, IDs, and parent-child relationships
- [We added a ```class``` attribute](https://github.com/CoderDojoSV/beginner-web/tree/master/session2/README.md#classes) to one of our tags so we could apply styles to every element that was labeled with that class. 
- [We added an ```ID``` to an element](https://github.com/CoderDojoSV/beginner-web/tree/master/session2/README.md#ids) to uniquely style an element.

### Declarations
- [We learned about properties and values](https://github.com/CoderDojoSF/webdev-lesson-2-css/blob/master/README.md#properties) and how we can use them to give our elements some style.
- [We learned about states](https://github.com/CoderDojoSF/webdev-lesson-2-css/blob/master/README.md#css-rules-in-the-real-world) so you can make your CSS rules change when certain things happen.

## Box Model

In HTML, every element is a rectangular box. Every box a height and a width that defines how big it is and how much space it will take up on the page. 

If we want to make an image on our page 500px wide and 400px high, we could do the following:

```css
img {
	height: 200px;
	width: 300px;
}
```

However, that isn't the only thing that defines how our image fits on the page because every element is surrounded by three more things: **padding**, **border**, and **margin**. Understanding how your padding, borders, and margins work is essential to making sure that your elements look as expected. 

To help us understand this, we have this diagram:

![The Box Model](screenshots/box-model.png)

The "border" is the edge of your box. Padding controls how close things inside the box can be to the border and Margin controls how close things outside the box can be to the border. 

Let's see how this works in practice...

![No margin, padding, or border](screenshots/blankmargin.png)

If you look at the first image on the page, you'll notice how it  currently has no margin, padding, or border. As a result, it's pushed up against the left side of the page with no spacing.

Let's add some padding to the page to indent the image a little bit.

```css
img {
  width: 50%;
  padding-left: 10px;
}
```
![Image with padding](screenshots/img-padding-left.png)

Now let's see what happens when we change that padding to a margin.

```css
img {
  width: 50%;
  margin-left: 10px;
}
```
![Image with margin](screenshots/img-margin-left.png)

Nothing?! Wait a second... let's do some detective work. Let's change the color of the background for this element to see if there is any invisible spacing.

```css
img {
  width: 50%;
  margin-left: 10px;
	background-color: tomato; 
}
```
![Image with margin and color](screenshots/img-margin-color.png)

Hmm... that didn't seem to do anything. Let's change from margin back to padding? 

```css
img {
  width: 50%;
  padding-left: 10px;
	background-color: tomato; 
}
```
![Image with padding and color](screenshots/img-padding-color.png)

Aha! When you use padding there is space between the left edge of the element and the picture itself. 

Let's see what this looks like when we add a margin and a border.

```css
img {
  width: 50%;
  padding-left: 10px;
  margin-left: 10px;
  border-left: 5px solid dimgray; 
  background-color: tomato;
}
```
![Image with padding margin and color](screenshots/img-padding-margin-border.png)

You can see, the border color sits between the padding and the margin. If you're ever having trouble positioning your elements, make sure to check all 3: margin, padding, and border. 

## Float

Sometimes you'll want to move things around on the screen. Maybe you want to have the pictures on the right side of the screen and the descriptions on the left. Using ```float``` is a great way to make that happen.

Let's float our pictures to the right and our text to the left. 

```css
img {
  float: right;
  width: 50%;
  margin-left: 10px;
}
```
![Image floating to the right](screenshots/img-float.png)

Whoa! Everything moved. Before we fix things, let's try to understand why that happened. 

When floating an image, it is going to float all the way to the edge of its parent container. Because I applied float directly to ALL image tags on our page, the float looked to see what the parent container was and saw that it was ```<body>``` so it moved the images to the right edge of the body of the page. 

When floating an image, the other elements will begin to line up around it within the natural flow of the page. 

![Float Right](screenshots/float-right.png)

However, since **everything** got pushed up the page, our descriptions of the pictures no longer match up with the pictures themselves.

**We can fix this!**

Let's decide how we want this to look. Probably something like this...

![Floats](screenshots/floats.png)

*image thanks to [Shay Howe](http://learn.shayhowe.com/)*

We are going to have our top section stretch across the screen while the middle section is split into two columns. The bottom will be all one section.

To do that, we're going to wrap our pictures and their caption paragraphs in two different ```divs``` 

```html
<div id="first-picture"> 
	<p>Today I took the dogs to the park and <strong>we had a great time!</strong></p>
	<img src="http://f.cl.ly/items/2f473l1d233S0S1k3J3d/dogs-playing.jpg">
</div>
    
<div id="second-picture">
	<p>After the dogs played with their friends <em>we took a walk around the track together.</em></p>
	<img src="http://f.cl.ly/items/0o0T0V0g261C1R0I022z/walking-the-track.jpg">
</div>
  
<div id="summary"> 
	<!-- your bottom section goes here -->
```

```css 
#first-picture {
  height: 400px;
}
#first-picture p {
  float: left;
}
#second-picture {
  height: 400px
}
#second-picture p {
  float: left;
}
#summary {
  clear: both
}
```

![Pictures with their captions to the left](screenshots/floats-paragraphs.png)

> **Bonus #1**: What happens if you don't set a height? 

> **Bonus #2**: how would you go about cleaning up this messy code? 

**This can be messy.** There are a lot of weird rules to how floats work and we don't have time to go over all of them but you can [read more here](http://coding.smashingmagazine.com/2009/10/19/the-mystery-of-css-float-property/). 

## Position

Beyond just floating elements, you can also position them with the ```position``` property.

CSS gives you five different options for using position: ```static``` ```relative``` ```absolute``` ```fixed``` and ```inherit``` 

The default is ```static``` which is what gets set even if you don't bother to set any position. We'll talk about two others today, ```absolute``` and ```relative```.

Let's start by creating a label that we're going to place on top of our image that we've floated to the right.

```html
 <h1>A day at the dog park</h1>
    
    <div id="cool"> COOL! </div>
    
    <div id="first-picture"> 
```
```css
#cool {
  color: white;
  font-size: 3em; 
}
```

![Cool story](screenshots/cool-static.png)

This is what it looks like as a static div.

Now let's give it an absolute position and make it display on top of our image.

```css
#cool {
  position: absolute;
  left: 520px;
  top: 300px;
  color: white;
  font-size: 3em; 
}
```

![Cooler story](screenshots/cool-absolute.png)

Hmm... what would happen if we changed that absolute to "relative" 

```css
#cool {
  position: relative;
  left: 520px;
  top: 300px;
  color: white;
  font-size: 3em; 
}
```
![Coolest story](screenshots/cool-relative.png)

It moved! But why? Let's see what happens if we move the div to a different place in the HTML file...

We'll move it to just before the div that contains the second picture.

```html
    </div>
    
    <div id="cool"> COOL! </div>
    
    <div id="second-picture">
```

![Coolest story](screenshots/cool-relative2.png)

It moved down to just below the second picture.

Hmm... now what would happen if we changed the position back to absolute? 

```css
#cool {
  position: absolute;
  left: 520px;
  top: 300px;
  color: white;
  font-size: 3em; 
}
```

![Whoa!](screenshots/cool-absolute.png)

It went back up to the first picture! You see, when you set your position as absolute, CSS doesn't care where your HTML tag is because it's going to put the block **absolutely** where you tell it to go. When you use **relative** it puts it **relative** to the block listed right before it. 

In this case, our ```left``` and ```top``` position measurements were being taken **relative** to the ```h1``` in our body and then, after moving it, relative to our first-picture div.


## Summary

Thanks! Next week we'll start digging into Javascript and some other cool things.

[The Pen I used today](http://codepen.io/donjo/pen/vBFwl).