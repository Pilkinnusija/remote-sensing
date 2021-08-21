

# Google Earth Engine Introduction

## Why Google Earth? 

Research in Remote Sensing has evolved drastically over the past few decades. Initially, only a handful of governments had the capability to deploy satellites and reliably process satellite imagery, and its use was largely limited to the military and intelligence communities. Organizations such as National Aeronautics and Space Administration (NASA) and the European Space Agency (ESA) were established to bridge the technology gap and incorporate civilian academic research, but there remained significant hurdles in the process and research was constrained by scheduling funding and political interests. Even if a researcher had identified available data, they would have to obtain it, store it, obtain time to use a computing system that could handle the task, perform geo-rectification and then process the results. This was a time-consuming, costly and often prohibitively inefficient way of using satellite imagery for research. 

Enter Google Earth Engine (GEE). As part of Google's quest to make the world's information universally accessible and useful, the Earth Engine is their answer to organizing and simplifying satellite imagery and geospatial data in a way that supports an end-to-end solution for research. This is a valuable tool that solves many of the historical problems that Remote Sensing researchers have struggled with. It has collected petabytes of imagery from both public and private sources, including the most-used Landsat, MODIS and Sentinel data. Additionally, it allows users to process the data and conduct sophisticated analysis on their data of choice within Google's Cloud environment (even allowing advanced Machine Learning using TensorFlow Processing Units). They also geo-rectify the image and provide pre-built algorithms that simplify the analysis process. In case you need to build your own algorithms, Google Earth Engine has built functionality within JavaScript and Python, allowing a virtually unlimited toolbox for working with the data. The user can even import their own data and work with it within GEE. Finally, the user owns the analysis and algorithms written within GEE, providing fair and open use.   

As researchers intending to use Remote Sensing, learning Google Earth Engine will provide an invaluable toolset throughout your career. 

## Getting Started

To begin, ensure you sign-up for the Google Earth Engine [here](https://signup.earthengine.google.com). Registration is free and straightforward, but it takes approximately 24 hours to be approved to use the code editor. While waiting, let's get familiar with the Google Earth Engine. The video below is a quick introduction to Google Earth Engine to get you familiar with the resources available. 

[Video](https://www.youtube.com/watch?v=Ypo28T6wPbQ)

####  Resource Links

* Google Earth Engine [link](https://earthengine.google.com)
* Code Editor [Map](https://developers.google.com/earth-engine/guides/playground?hl=en)
* [Datasets](https://developers.google.com/earth-engine/datasets/)
* [Case Studies](https://earthengine.google.com/case_studies/)
* Google Earth Engine [Blog](https://medium.com/google-earth)
* [Video](https://developers.google.com/earth-engine/tutorials/tutorials) tutorials on using GEE (from the Earth Engine Users' Summit)

## Getting Set Up

Google Earth Engine allows you to work with your own data. You are able to import raster imagery, vector imagery and tabular data and then incorporate those assets into your analysis. This is process is automatically linked to the Google Drive account that signed up for GEE. If you are not familiar with Google Drive, there is a '[Getting Started Guide](https://support.google.com/a/users/answer/9282958?hl=en)' that goes over the basics of setting up and organizing your Google Drive account. We will not be covering Google Cloud Platform Storage in this course. Below are some helpful links to documentation on working with external data. 

* [Managing Assets](https://developers.google.com/earth-engine/guides/asset_manager)
* [Import Raster](https://developers.google.com/earth-engine/guides/image_upload)
* [Import Vector / Tabular Data](https://developers.google.com/earth-engine/guides/table_upload)
  * Note that GEE only supports Shapefiles and .csv files
* [Exporting Data](https://developers.google.com/earth-engine/guides/exporting)

## Understanding Google Earth Engine

It is important to understand the basics of how Google Earth Engine works. The Developer's [overview](https://developers.google.com/earth-engine/guides/concepts_overview) provides much more detail on the intricacies of how GEE processes data on the Google Cloud Platform, but in the simplest terms, there are two sides to the process - the `client` side and `server` side. When you open your web browser and begin to work in the code editor, that is considered the `client` side. You can write JavaScript code in the editor and the code will be processed within your browser. The code below simply creates a variables `x` and `y`, adds them together as the variable `z` and prints the result, which shows up in the console of the code editor. Even though the code is written in the GEE editor, it plays no role in the execution of this code - your browser executes it. 

```javascript
var x = 1; var y = 2;
var z = x + y;
print(z)
```

To begin using GEE effectively, we have to tell GEE what we need it to do. Let's say we want to import an image collection. In the snippet below, you can see that there is an `ee` before the `ImageCollection` constructor. In simple terms, this signals to Earth Engine that we will be using its resources. Without that indicator, GEE will cede operations to the browser to process the JavaScript. 

```javascript
var sentinelCollection = ee.ImageCollection('COPERNICUS/S2_SR');
```

Over time, you will gain experience understanding the role of working with JavaScript on the `client` side and the `server` side, but the main point in this section is that when programming, we will be building 'packages' that explicitly define what we need GEE to do.

An extension of this topic is listed [here](https://developers.google.com/earth-engine/guides/client_server), along with discussions of programming specific topics (ie, mapping instead of looping). 

## JavaScript

The intent of this course is not to teach the intricacies of programming within JavaScript. JavaScript is the core language for web development, and you will likely find that many of the tutorials and resources you find will not be directly relevant to the type of JavaScript that you will need to work in Earth Engine (ie, working with React, JQuery, dynamic app development, etc). JavaScript was chosen because it is an extremely popular language (~97% of websites use it in some fashion) and as an object-oriented language, it is well-suited to pair objects (in this case, imagery provided by Google Earth Engine) with methods (such as using the `reduce` function to summarize the analytical information from a processed image). 

There are some excellent resources that will assist your understanding of working with JavaScript. One helpful tutorial is [Javascript.info](https://javascript.info), which provides a thorough overview of working with JavaScript. In this tutorial, focus on part I, as part II and III are focused on web development. 

[W3Schools](https://www.w3schools.com/js/default.asp) provides good information on each individual component of working with JavaScript. For instance, if you see the word `var` and wanted more information on it, W3Schools has some helpful definitions and code snippets that will be of use. 

Finally, [JavaScript & JQuery](http://www.javascriptbook.com) is an excellent, well-designed book that goes through the fundamentals of working with JavaScript and provides helpful illustrations and use cases. The second half of the book is outside the scope of this course, but if you did want to extend your skillset, this book is a great starting point. 

