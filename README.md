#Immersive Slider by Pete R.
Create an immersive slider that changes the whole container to match the viewing slide
Created by [Pete R.](http://www.thepetedesign.com), Founder of [BucketListly](http://www.bucketlistly.com)

[![Immersive Slider](http://www.thepetedesign.com/images/immersive_slider_image.png "Immersive Slider")](http://www.thepetedesign.com/demos/immersive_slider_demo.html)

## Demo
[View demo](http://www.thepetedesign.com/demos/immersive_slider_demo.html)

## Compatibility
Modern browsers such as Chrome, Firefox, and Safari on both desktop and smartphones have been tested. Not tested on IE.

## Basic Usage
Immersive Slider let you create a unique immersive slider experience that changes the whole container to match the viewing slide like you see at the [Google's TV website](http://www.google.com/tv/). The plugin will let you assign background images per slide without you doing all the hard work. 

To add this to your website, simply include the latest jQuery library together with `jquery.immersive-slider.js`, and `immersive-slider.css` into your document's `<head>` and create an HTML markup as follows:

````html
<div class="main">
  ...
  <div id="immersive_slider">
    <div class="slide" data-blurred="<<background-image-url>>">
      ...
    </div>
    <div class="slide" data-blurred="<<background-image-url>>">
      ...
    </div>
    
    ...
  
    <a href="#" class="is-prev">&laquo;</a>
    <a href="#" class="is-next">&raquo;</a>
  </div>
</div>
````
The container main will be used to display the background images. Make sure you change all the `<<background-image-url>>` occurrences to the image path you wish the slider to show when that slide is active. Feel free to remove the navigational buttons if you don't need it. Once that is done, simply call the script like this:
 
````javascript
$("#immersive_slider").immersive_slider({
  animation: "bounce", // As usual, you can change the animation to these: slide (default), bounce, fade, slideUp, and bounceUp
  slideSelector: ".slide", // This option will let you assign custom selector for each slides in case .slide is already taken
  container: ".main", // This option lets you define the container of which the background will appear. Make sure the slider is inside this container as well.
  cssBlur: false, // Experimental: In case you don't want to keep adding new data-blurred attributes, trigger this to true and it will generate the blur image on the fly (more info below).
  pagination: true, // Toggle this to false if you don't want a pagination
  loop: true, // Toggle to false if you don't want the slider to loop. Default is true.
  autoStart: 5000 // Define the number of milliseconds before it navigates automatically. Change this to 0 or false to disable autoStart. The default value is 5000.
});
````
And that's all you have to do to get this plugin up and running on your website. Pretty easy right?

## Experimental Feature: CSSBlur
The plugin is capable of blurring the first image it finds in each slide, blow them up and use it as a background without you having to manually set each slide a background image. This is done using the CSS3 style called Filter which only works on Chrome, and maybe a performance hog. Use it at your own risk.

To do this simply toggle the cssBlur option to true like this:

````javascript
$("#immersive_slider").immersive_slider({
  cssBlur: true
});
```` 

and make sure the images you want to blow up as a background are in each slides like this:

````html
<div class="main">
  ...
  <div id="immersive_slider">
    <div class="slide">
      <img src="<<background-image-url>>">
      ...
    </div>
    <div class="slide">
      <img src="<<background-image-url>>">
      ...
    </div>
    ...
  </div>
</div>
````

The script will grab this first image, apply the CSS filter and blow them up with CSS filling the container for you. This is great when you already have an existing slider and you don't want to add a new attribute for the background.

## Public Methods
You can also trigger the slider to move programmatically as well:

### $.fn.moveNext()
This method allows you to move the slider to the next one.

````javascript
  $("#immersive_slider").moveNext();
````

### $.fn.movePrev()
This method allows you to move the slider to the previous one.

````javascript
  $("#immersive_slider").movePrev();
````

If you want to see more of my plugins, visit [The Pete Design](http://www.thepetedesign.com/#design), or follow me on [Twitter](http://www.twitter.com/peachananr) and [Github](http://www.github.com/peachananr).

## Other Resources
- Tutorial (Coming Soon)
- [Eike Send's jQuery Swipe Events](https://github.com/eikes/jquery.swipe-events.js)