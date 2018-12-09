---
layout: post
title: "Novice trying ScrollMagic"
categories: Readings
---

Afte some experimentation, I started to figure out the basic structure of a website.
1. HTML - The structure of the website
2. CSS - The aesthetics and some behavior
3. JS - Most of the Behavior

I wanted to try to at least learn a bit about how one would use a simple JavaScript library to create an interactive data experience.
I followed this tutorial (https://github.com/janpaepke/ScrollMagic/wiki/Get-Started-Setup)!

Note that the javascript that is required for the behavior of the website is imported in the `<head>`.
```
<html>
<head>
    <title>ScrollMagic Tutorial #1</title>
	
	<script src="http://ajax.googleapis.com/ajax/libs/jquery/1.9.1/jquery.min.js"></script>
    <script src="http://cdnjs.cloudflare.com/ajax/libs/gsap/1.14.2/TweenMax.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/ScrollMagic/2.0.3/ScrollMagic.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/ScrollMagic/2.0.3/plugins/animation.gsap.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/ScrollMagic/2.0.3/plugins/debug.addIndicators.js"></script>

</head>

<body>
    Hello World!
</body>
</html>
```

This tutorial involved using another JS package called GreenSock where you can design animations that are vector art based. From my previous experience with GIFs ... I know that they are often pixelated and take away from the professional look of the website so it might be wise for me to learn how to animate SVGs at some point.
We now need to add the `style` and `script` elements.

```
<html>
<head>
    <title>ScrollMagic Tutorial #1</title>
	<script src="http://ajax.googleapis.com/ajax/libs/jquery/1.9.1/jquery.min.js"></script>
    <script src="http://cdnjs.cloudflare.com/ajax/libs/gsap/1.14.2/TweenMax.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/ScrollMagic/2.0.3/ScrollMagic.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/ScrollMagic/2.0.3/plugins/animation.gsap.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/ScrollMagic/2.0.3/plugins/debug.addIndicators.js"></script>
    
    <style>
    html, body {
        height: 100%;
        margin: 0;
        padding: 0;
    }
    #container {
    margin: 55vh 0;
    padding: 50px;
    outline: 1px dashed orange;
	}

	#block {
    padding: 10px;
    border: 1px solid black;
    font-family: Helvetica;
	}
    </style>

</head>
<body>
    <div id="container">
        <div id="block">
            Hi there !
        </div>
    </div>
    
    <script>
    CODE GOES HERE
	</script>
    </body>
</html>
```

The first step of ScrollMagic is to create a controller object wrapped in jQuery's onReady function. Then create the Tween object (that is the transition) and link it to the scrolling. As someone who has taken computer science courses, it is really hard to understand the syntax of JavaScript but the guide does a good job of explaining all the steps!

```
$(function() {
    var controller = new ScrollMagic.Controller();
});
var blockTween = new TweenMax.to('#block', 1.5, {
    backgroundColor: 'red'
});
var containerScene = new ScrollMagic.Scene({
    triggerElement: '#container'
})
.setTween(blockTween)
.addIndicators()
.addTo(controller);
```

This was my end result. Even though I just followed the blog post to the tea, it is always nice when something actually works.

<video controls loop>
  <source src="https://github.com/sathvikpal/Data_Visualization_Studio/blob/master/assets/ScrollMagic/Screen%20Recording%202018-12-08%20at%207.26.25%20PM.mov?raw=true" type="video/mp4">
  <video>
