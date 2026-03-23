# seo-slider

jQuery simple slider / slideshow / caoursel widget that is lightweigt, seo friendly and has fade effect between slide transitions.

## Internet says sliders hurt SEO and usability?

The internet is full of false statement that slideshows are bad for search engine optimizations (SEO) or usability. Its not the slideshow that is bad, its how the slider is interpreted and how the designer and developer define the slider technically and visually.

Why else is amazon sometimes using a simple slider at its main page? 

## How is it this plugin user friendly?

Many slider plugins are heavy and bloated with many features for a large target audience of developers, agencys and artists. 
The more tools you get the more you do without reflecting if it really helps the user.

This plugin does not support animations so with static slides you must analyse what is important for your users intention to reach his target.

## Features

* seo optimized for _Web Core vitals_ 
* faster loading speed compared to competition
* easy to configure
* fade transition between slides
* responsive
* control buttons
* * previous and next 
* * slide indicator dots


## How is it this plugin SEO friendly?

### 1. Content is indexable

Content is completely visible in DOM in a natural HTML tag structure and so visible for search engine crawlers.

### 2. Lightweight resources

The CSS stylesheet file and javascript JS file are very small in size. 

### 3. Optimized for _Web Core Vitals_ metric 

_Web Core Vitals_ is a framework for search engines to test the quality of a webpage technically and visually. You can check your rating inside google search console or using google test page https://pagespeed.web.dev or developer tool _Lighthouse_ in your browser.

*Test it out yourself:* Use the example html without the javascript file and see if the first slide is still visible!

#### 3.1 _Largest Contentful paint (LCP)_ 

An important metric is _"Largest contentful paint" (LCP)_ which represents how fast the upper visible content (above the fold) is rendered and visible to the user. For content below the fold the user must scroll so its less important. _First impression counts!_

This slider is LCP friendly because the first slide is immediately visible and all other slides hidden, even without the use of javascript. Other slideshow / carousel plugins require javascript to display the first slide which in fact, can hurt your SEO much since the most important _"hero"_ image of the first slide will only load once the resources or even the whole DOM has been loaded which can delay it by a second or more.

Since the javascript code is *not needed to display the first slide* so the loading of the JS file can be deferred or loaded asynchronously.

#### 3.1 _Cumulated layout shift (CLS)_ 

Metric _cumulated layout shift_ is an important metric since it measures how much the page will jump during loading which lead to annoying user behavior, especially on mobile small screens.

This slider is CLS friendly since there is no shift if you use a fixed css `height` on the slider or if thats not possible repeat the first background `<img>` tag after the slides so no additional javascript is required to calculate the height on initialization and windows resizing.

## Documentation

In this tutorial, we'll create a simple image slider for a web page. We'll cover initializing the slider, adding captions, and optimizing images for performance and SEO. We use css classes from library [PrimeFlex](https://primeflex.org/).

### Step 1: Creating the Basic Slider

First, add the HTML code for the slider. We use simple images with full width and automatic height.
```html
<div id="slider" class="del-slider">
    
	<!-- slide 1 -->
	<div>
		<img  class="w-full h-auto"  src="path_to_your_image1.jpg" alt="Description of the first image" width="1800" height="700"/>
	</div>
	<!-- slide 2 -->
	<div>
		<img  class="w-full h-auto"  src="path_to_your_image2.jpg" alt="Description of the second image" width="1800" height="700"/>
	</div>

 </div>
```

This sets up a basic slider where each image will stretch to the full width of the slider container.

![ezgif com-crop](https://github.com/deloma-de/seo-slider/assets/104908394/be9f8c9d-2235-457a-8874-b6ed414be915)

### Step 2: Adding Captions

Add captions with relative font size (em) to ensure better responsiveness on different screen sizes.
```html
<div id="slider" class="del-slider">

	<div>
		<img  class="w-full h-auto"  src="path_to_your_image1.jpg" alt="Description of the first image" width="1800" height="700"/>

         <div class="caption" style="position: absolute; top: 20%; left: 10%; font-size: 2em;">
            Your caption here
        </div>

        <!-- img caption -->
		<img class="absolute" height="384"src="path_to_your_image1.jpg" height="384" style="width: 30%; height: auto; left: 33%; top: 51%;" width="704" />
				
	</div>

 </div>
```
Position the caption absolutely within the .slide div. Adjust the 'top' and 'left' properties to place the caption as needed.

![ezgif com-crop (2)](https://github.com/deloma-de/seo-slider/assets/104908394/513ac166-90fe-4029-8cc7-accbf6caa8ed)

### Step 3: Add dummy image to reduce layout shift.

To reduce layout shifting, especially before the javascript has loaded the browser needs to determine the height of the slider. For this we need to add an dummy image at the end. You can repeat the first image again or use a white background image.

```html
<div id="slider" class="slider">

    <!-- Your slides -->

    <!-- dummy background image a) repeat the first image at the end -->
    <img class="w-full h-auto" src="path_to_your_first_image.jpg" alt="Description of the first image" width="1800" height="700">


    <!-- or use data src attribute with a white background that is exactly the wished dimension (here 1800x700)
        <img class="w-full h-auto" fetchpriority="low" height="700" loading="lazy" alt="Background white" src="data:image/webp;base64,UklGRlgAAABXRUJQVlA4TEwAAAAvB8euAAfQ//73v/8BAUnS//9hRP8z/vOf//znP//5z3/+85///Oc///nPf/7zn//85z//+c9//vOf//znP//5z3/+85///Oc//wcL" width="1800"> -->

</div>
```

This technique helps in maintaining a consistent height for the slider, especially before the JavaScript has loaded.


### Step 4: Initialize Slider with jQuery

```html
<script>
    $(document).ready(function() {

        ('#slider').delSlider();
    });
</script>
```

### Optimizing Image Loading and Rendering

Optimize image loading by adding loading, fetchPriority, and srcSet attributes.

- Add `loading="lazy"` for images that aren't immediately visible.
- `fetchPriority="high"` for the first or crucial images and `"low"` for the other slides.
- Use attribute `srcSet` for responsive image sizes.
- Add dimension attributes `height` and `width` to improve browser rendering speed and reduce layout shift.

```html
<div id="slider" class="slider">

    <img class="w-full h-auto" src="path_to_your_first_image.jpg" alt="Description of the first image" loading="lazy" fetchPriority="high">
   
</div>
```

Include alt, width, and height attributes for each image for better SEO performance.

## Demo

Have a look at this ecommerce shop in production: https://www.call4drinks.de/.

## Feedback

Create an issue if you have feedback, tips or find bugs!

_deloma equals SEO_
