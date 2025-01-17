![interactive map screenshot showing Living Valley iframe](iframeScreenshot.png)

# ebr-interactive-map
A web-based interactive map for use alongside the cooperative adventure card game Earthborne Rangers

# Explanation of current files
* locations.js: This is a JavaScript file containing one variable named `locationData`, which is an array containing information about all of the current locations on the map.
* styles.css: This is a standard CSS file containing the styles for making the page and links look a certain way.
* test.html: This is the main HTML file containing the SVG to render the map and the JavaScript to allow interactivity.
* ValleyMapOLD.jpg: This is an old version of the map, containing at least two errors. It will need to be replaced eventually.

# Current Features
* Valley map is rendered via SVG
* Map can be panned by clicking and dragging
* Map can be zoomed in and out by clicking the zoom buttons in the top right or by using scroll wheel
* Each location has an invisible button that highlights when hovered/clicked
* When clicked, each location opens an iframe with the corresponding Living Valley entry in it

# Potential Features (TODO)
* Get newer version of map
* Add map overlays from expansions
* Add menu to toggle expansions
* Add iframe for Living Valley entry (replace new tab functionality)
* Add animation (zoom in, zoom out, menu open, menu close, open Living Valley iframe, automatically pan map to bring Living Valley iframe into view)
* Add functionality to allow users to take notes at specific locations
* Add functionality to allow users to search and highlight locations based on traits

# Known Bug(s)
* Zoom in/zoom out functionality does not perfectly zoom from the center of the SVG frame. There is a strange wobble observed when zooming quickly.
