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

Please see the test folder for examples.

TODO add markup

## Demo

Have a look at this ecommerce shop in production: https://www.call4drinks.de/.

## Feedback

Create an issue if you have feedback, tips or find bugs!

_deloma equals SEO_
