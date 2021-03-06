cytoscape-supportimages-port
================================================================================
## Trying to port this plugin to support v3.x.
Any Help is appreciated!
Notes: 
 * The latest cytoscape supported is : 2.6.13
 * Breaks at 2.7

## Useful links (porting guides by cytoscape) : 
 * https://github.com/cytoscape/cytoscape.js/issues/1092
 * http://blog.js.cytoscape.org/2017/04/11/3.0.0-release/#api-changes-and-migration

## DONE things:
 * [#1541](https://github.com/cytoscape/cytoscape.js/issues/1541)
	Coudnt find any instances of onRender and offRender
 * [#1537](https://github.com/cytoscape/cytoscape.js/issues/1537)
	Corrected in this commit

## Description

A plugin that enables support images on cytoscape.js

Available functionalities:
 * add image
 * remove image
 * list images
 * change drawing order
 * change visibility
 * change locking (can be selected or moved)
 * resize (shift pressed when resizing keeps the image center, ctrl pressed when resizing keeps the aspect ratio)


## Dependencies

 * Cytoscape.js >=2.3.8

## Usage instructions

Download the library:
 * via npm: `npm install cytoscape-supportimages`,
 * via bower: `bower install cytoscape-supportimages`, or
 * via direct download in the repository (probably from a tag).

`require()` the library as appropriate for your project:

CommonJS:
```js
var cytoscape = require('cytoscape');
var supportimages = require('cytoscape-supportimages');

supportimages( cytoscape ); // register extension
```

AMD:
```js
require(['cytoscape', 'cytoscape-supportimages'], function( cytoscape, supportimages ){
  supportimages( cytoscape ); // register extension
});
```

Plain HTML/JS has the extension registered for you automatically, because no `require()` is needed.


## API



```js
// init/get the extension
var si = cy.supportimages();

// add a support image
si.addSupportImage({
	url: 'yourimageurl',
	name: 'yourimagename'
});

// list images
var imgs = si.images();

var myImg = imgs[0];

// set image locked
si.setImageLocked(myImg, true);

// set image visible
si.setImageVisible(myImg, false);

// move image up in the drawing order
si.moveImageUp(myImg);

// move image down in the drawing order
si.moveImageDown(myImg);

// remove image
si.removeSupportImage(myImg);
```
