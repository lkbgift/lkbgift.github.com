---
layout: post
title: "Basic TileMill: Making Beautiful Maps"
date: 2013-03-14 12:57
comments: true
categories: Maps design graphic 
---
![Using TileMill](https://forrst-live.s3.amazonaws.com/multiposts/images/39039/mega.png?1363124354)
# TileMill makes beautiful maps

[TileMill](http://mapbox.com/tilemill/) is a downloadable program that allows you to make beautiful maps. The software is developed by [MapBox](http://mapbox.com/), a company that provides OpenSource maps as a service.

TileMill is a basic GUI for skinning GIS data. Using a CSS like language, called [CartoCSS](http://mapbox.com/tilemill/docs/manual/carto/), users can modify and add visual elements. CartoCSS provides conditional logic, allowing styles to target specific segments of data. 

An example of segmented data styling is in open data regarding city populations. Using the CartoCSS, you can render a circle on all of the cities in the world. Using conditional logic, you can make the circle bigger or smaller based on the population of the city.

## Getting started

To get an introduction to TileMill, I suggest going through the [Crash Course](http://mapbox.com/tilemill/docs/crashcourse/introduction/) provided by MapBox. The crash course will show you how to load in external data sets, provide conditional styling, and export your map (or upload it online).

## Quick Lesson

I [showcased a map](http://forrst.com/posts/Beautiful_maps_with_CSS_and_open_data-FRM) I made for Acquinity Interactive on [Forrst](http://forrst.com) this week. On it, I showed the working files of the TileMill map I created. One of the users requested that I explain how to make something like this.

### Step 1: Download and install

I won't go into detail. Get the program [here](http://mapbox.com/tilemill/) and install it.

### Step 2: Start a new project

Click Projects > New project. Set a filename. Make sure the "Default data" box is check. Then click Add. Click the newly created project to open up the Editor.

### Step 3: Add in open data

Just as you will learn in the Crash Course I mentioned above, we will add in a new layer of data. For the sake of this example, we will select the urban city data.

Click Add Layer, at the top right. Once the Add layer model pops up, click Browse. In Browse, click MapBox.

Once in MapBox, click to mapbox-geodata / natural-earth-1.4.0 / cultural / 10m-populated-places.zip. Then click done and save.

### Step 4: Find the data to style

From here, you can style anything from the countries you can see, to the data that you just loaded in. For the sake of simplicity, we will make a selector on the cities we loaded in and differentiate them by population.

For more specific selectors, you can go to the CartoCSS documentation.

### Step 4.5: Code example

After looking at the Layer's "Feature" data, I found the data column **POP_MIN** that I would like to target.

The proper syntax for selecting a data attribute is similar to CSS. I will use ``#10mpopulatedplaces{}`` to make a selector for the data we imported.

Second, I will made a distinction between the small, medium, and large cities with a conditional selector. The conditional selector should go onsite the one we created above. You can make something like this:

	#10mpopulatedplaces {
	  marker-width:1;
	  marker-fill-opacity: 0;
	  marker-line-color:#ec9a14;
	  marker-allow-overlap:true;
	  
	  [POP_MIN <= 1200000] { marker-width:100;marker-opacity: 0.4; marker-line-width:1.0; }
	  [POP_MIN > 1200000]   { marker-width:400; marker-opacity: 0.1; }
	  [POP_MIN > 10000000]   { marker-width:700; marker-opacity: 0.5; marker-line-width:.3;}

This will make three different styles targeting cities with a minimum population smaller than or equal to 1,200,000, larger than 1,200,000 and larger than 10,000,000. The styles that I select are the marker *size*, *opacity*, and *border*. CartoCSS documentation explains there are a number of other styling features such as fill, glow, and much others.

### Step 5: Export

From here, you have a map with some generic circles. You can make some additional styling choices to the land and ocean. If you want to make the purple map that I had, you can find the style.mss content [here](https://gist.github.com/lkbgift/5163407)

Go ahead and click Export to get the choices of different export formats. Personally, I like to screenshot the export screen, then modify the screenshot in Photoshop. I have found it looks more like the way I want it to. Otherwise, explore in PNG and set the dimensions. 

## Learning More

The above was a really basic instruction set. This doesn't do justice to the capacity of TileMill, so I highly suggest that you go and follow the Crash Course provided by TileMill and experiment yourself.

If you are interested in digital maps, I highly suggest listening to the [WebAhead podcast on Maps with Alex Barth](http://5by5.tv/webahead/23). This was the first time I learned about TileMill and MapBox. 