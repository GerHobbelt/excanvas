# ExplorerCanvas

Copyright 2006 Google Inc.

## DESCRIPTION

Firefox, Safari and Opera 9 support the canvas tag to allow 2D command-based 
drawing operations. ExplorerCanvas brings the same functionality to Internet 
Explorer 8 and older; web developers only need to include a single script tag in their 
existing canvas webpages to enable this support.


## Installation / How to use 

Place the ExplorerCanvas source file `excanvas.js` in the same directory as your HTML files.


## Include the script om your HTML files

The `excanvas.js` file must be included in the page before any occurrences of canvas elements in the markup. This is due to limitations in IE and we need to do our magic before IE sees any instance of `<canvas>` in the markup. It is recommended to put it in the head. More on "[Can I use the HTML5 canvas element?](http://caniuse.com/canvas)".

	<head>
	<!--[if lte IE 8]><script src="excanvas.js"></script><![endif]-->
	</head>


## Dynamically created elements

If you have created your canvas element dynamically it will not have the `getContext` method added to the element. To get it working you need to call `initElement` on the `G_vmlCanvasManager` object.

	var el = document.createElement('canvas');
	G_vmlCanvasManager.initElement(el);
	var ctx = el.getContext('2d');

Thats it. Now you can use the [HTML5 spec for Canvas](http://www.whatwg.org/specs/web-apps/current-work/multipage/the-canvas-element.html) as your reference.


## In Trouble / Notice

If you run into trouble, please look at the included example code to see how
to best implement this.

In the case you found a bug or have a enhancement proposal, please  [create an issue](http://code.google.com/p/explorercanvas/issues/list), or if you need help about using the library, please go and read the [mailing list](http://groups.google.com/group/google-excanvas).



# Contributor License Agreements

Before we can accept a patch from you, you must sign a Contributor License
Agreement (CLA). The CLA protects you and us.

* If you are an individual writing original source code that you wish to contribute to ExplorerCanvas and you are sure you own the intellectual property, then you'll need to sign an [individual CLA](http://code.google.com/legal/individual-cla-v1.0.html).
* If you work for a company that wants to allow you to contribute your work to ExplorerCanvas, then you will need to sign a [corporate CLA](http://code.google.com/legal/corporate-cla-v1.0.html).

Follow either of the two links above to access the appropriate CLA and instructions for how to sign and return it.

----
_Copyright 2008 Google Inc._
_This work is licensed under a_
[Apache License 2.0](http://www.apache.org/licenses/LICENSE-2.0)
