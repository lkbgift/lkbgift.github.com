---
layout: post
title: "Using multiple icon fonts from Zurb"
date: 2013-03-11 13:31
comments: true
categories: design icon fonts zurb
---

![Zurb's Foundation Icons](http://cdn.css-tricks.com/wp-content/uploads/2012/04/set-zurb.jpg)

#Using multiple icon fonts from Zurb

## Preface

The creators of Foundation, Zurb, provide useful tools for full-stack developers. One of their freely available tools are the Icon Fonts found [here](http://www.zurb.com/playground/foundation-icons). The fonts are free. There are four sets: general, enclosed, social, and accessibility. 

Of the four sets, it is difficult to simply choose one. Personally, I took a couple icons from each set. Because Zurb sets up their font sets in SASS files, this becomes exceptionally easy. 

*This guide is for users of Foundation and SASS* 

## How to setup

### 1. Download

First, download the fonts that you want from the Foundation Icons page. The link is here: [http://www.zurb.com/playground/foundation-icons](http://www.zurb.com/playground/foundation-icons).

### 2. Moving files

Second, grab the files located in the ``/sass`` and ``/fonts`` directory. Move these two directories to your website's main root directory. My home directory is setup like this:

 	/
	/index.html
	/css/*.css
	/css/*.scss
	/css/[ONE-FONT-SET]/[scss-FILES]
	/fonts/[FONTS-GO-HERE]
	/images/
	/scripts/
		
		
I have my SASS files and CSS files in the same directory. I create a separate directory in the ``/css/`` directory for each individual font ``.scss`` file set. Because I use SASS, I try to keep my working directories as organized as possible. I place the font files (``.eot``, ``.svg``, ``.tff``, ``.woff``) into the ``/fonts/`` directory.

### 3. Update Foundation Icon .scss files

After your files are placed in their respective directories, you need to update the files paths declared in the files. Also, if you are using multiple fonts, then you need to update the CSS class names, so the fonts do not overwrite one another. 

First, open the ``_settings.scss`` file for each font set. You should have something that looks like this:

	$fontFileName: "../fonts/general_foundicons";
	$fontName: "GeneralFoundicons";
	$classPrefix: "foundicon-";
	
	@mixin i-class($name,$pua) {
	  .#{$classPrefix}#{$name}:before { 
	    content: "\f#{$pua}";
	  }
	}
	
	@mixin ie-class($name,$pua) {
	  .#{$classPrefix}#{$name} { 
	    *zoom: expression( this.runtimeStyle['zoom'] = "1", this.innerHTML = "&#xf#{$pua};"); 
	  }
	}
	
	@mixin face {
	  @font-face { 
	    font-family: $fontName;
	    src: url('#{$fontFileName}.eot');
	    src: url('#{$fontFileName}.eot?#iefix') format('embedded-opentype'),
	         url('#{$fontFileName}.woff') format('woff'),
	         url('#{$fontFileName}.ttf') format('truetype'),
	         url('#{$fontFileName}.svg##{$fontName}') format('svg');
	    font-weight: normal;
	    font-style: normal;
	  }
	}

You need to change the first and third lines, respective to your own setup. The first line declares where you font files are located, respective to where you compiled .scss files appear. For me, my CSS files render in ``/css/*``. To access the ``/fonts/`` directory, I use ``../fonts/general_foundicons`` to go up one directory and into ``/fonts/``.

If you are using multiple fonts, you need to change the ``$classPrefix`` statement on the third time of ``_settings.scss`` to be unique. I change the name of my General Set from 

	$classPrefix: "foundicon-";

to

	$classPrefix: "foundicongen-";
	
Similarly, I changed my accessibility, social, and enclosed sets respectively, by adding one three letters after ``foundicon``.

### 4. Using icons in webpage

For this part, you can follow the directions on Zurb's instructions. You need to find out the name of the font icon you want to declare. Then, using the ``<i>`` tag, set the class ``foundicon-[icon]``, where [icon] is the name of the icon you want to declare.

In my case, because I am using multiple fonts, I needed to rename the class prefix above. Therefore, depending on the icon set I am pulling, I need to declare class that reflects the icon set.

For example, if I want the globe icon from the General Icons set, I will declare: 

	<i class="foundicongen-globe"></i>
	
This will appropriately pull the Globe icon associated with the General Icon set.

### 5. Style Away!

Again, just as the Zurb page says, you can now freely use CSS techniques to manipulate the icons. You can change colors, add triggers (hover, focus, active), as well as set animations using CSS3.

Enjoy!

For any questions, feel free to contact me at [@lkbcc](http://twitter.com/lkbcc)