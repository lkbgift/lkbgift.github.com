---
layout: post
title: "Foundation from Zurb"
date: 2012-12-16 11:59
comments: true
categories: tools framework website
---
**TLDR: The SASS Zurb Foundation install makes it easy to make a fully customized responsive website.**

Making a new website can be extremely easy or very time consuming. Tools available through Opensource projects, Creative Commons, and GNU licenses make it easy to layout a prototype in no time. 

Some of the obvious ones are [Twitter Bootstrap](http://twitter.github.com/bootstrap/) (+20,000 stars on Github) and [HTML5 Boilerplate](http://html5boilerplate.com/). My personal recent favorite is [Foundation](http://foundation.zurb.com/) from [Zurb](http://zurb.com/). I took a liking to Foundation because it gave me an edge at mocking up marketing pages without having to go through an extensive design and copywriting process.

Zurb's Foundation uses [Compass](http://compass-style.org/) and [SASS](http://sass-lang.com/) to make getting started and customizing very easy. You don't have to track down CSS elements or worse, overwrite existing declarations. Foundation provides clear documentation regarding what is provided and how it can be used. 

When paired with Compass, Foundation compiles a series of "Foundational" SASS stylesheets into a clearly documented CSS file. The SASS files make use of the [variable notation](http://thecodingdesigner.com/tutorials/variables-css-sass), allowing new users to change the existing styles, rather than overwriting. This can be particularly useful when you are trying to keep your CSS clean and well documented.

To make changes, Foundation provides a file called [_settings.sass](http://foundation.zurb.com/docs/sass.php). This file has all of the variables available for customization. All variables are presented commented out, so to make changes, just uncomment and change. Rather than overwriting the existing selectors, this keeps the CSS selectors light and easy to manage ([Snooks](http://smacss.com/) would approve).

Foundation makes a webpage look really great from the beginning (like Twitter Bootstrap). Some of us don't like the default Helvetica Neue and recognizable colors.  Differentiating your installation of Foundation is easy. The [problem](http://zurb.com/) with Twitter Bootstrap is that most websites using it don't do enough altercations to make it look different.

The two major changes that make your website look different are changing the default colors and the fonts. Again, using the SASS [_settings](http://foundation.zurb.com/docs/sass.php) file, you only make changes to the $mainColor, $bodyFontFamily, and $headerFontFamily. Once these changes are made, you have a extremely unique, responsive, well functioning website.

One letdown of Foundation is the dependence on [box-model](http://www.w3.org/TR/CSS2/box.html). (Let it be know, I [love box-model](http://paulirish.com/2012/box-sizing-border-box-ftw/) too. Still, it doesn't work with old browsers.) Box-model as a CSS property which calculates the padding inside the width. This simplifies calculating percentages for fluid layouts, but sadly this property is not available in IE6. 

Fortunately the dependance on box-model can be circumvented with [polyfills](https://github.com/h5bp/mobile-boilerplate/wiki/Media-Queries-Polyfill) and [explicitly defined layouts](https://github.com/zurb/foundation/issues/684). Still, Foundation's development without consideration for older browsers makes it difficult to use for my current demographic.

Overall, Foundation makes it easy to build websites. Paired with [Codekit](http://incident57.com/codekit/) (which deserves a post of its own) or [Compass](http://compass-style.org/), starting and managing new sites enjoyable!