![image](https://github.com/user-attachments/assets/e416d7f3-f88b-4f12-ae41-f51b525be12d)

# ebr-interactive-map
A web-based interactive map for use alongside the cooperative adventure card game Earthborne Rangers

# Explanation of current files
* add_new_map.md: This is a tutorial for adding a new map, in case somebody else takes over this project in the future
* arcology_map.html: This is the main HTML file of the Legacy of the Ancestors map, containing an SVG to render the map and JavaScript to allow interactivity
* Assets/banner-legacy: The Legacy of the Ancestors banner that appears in the menu for map selection
* Assets/banner-lure: The Lure of the Valley banner that appears in the menu for map selection
* Assets/EBR001_Valley Map_eng.jpg: The map image from Lure of the Valley
* Assets/EBR023_Deluxe LotA Map_eng.jpg: The map image from Legacy of the Ancestors
* locations.js: This is a JavaScript file containing one variable named `locationData`, which is an array containing information about all of the current locations on the map
* styles.css: This is a standard CSS file containing the styles for making the page and links look a certain way
* valley_map.html: This is the main HTML file of the Lure of the Valley map, containing an SVG to render the map and JavaScript to allow interactivity

# Current Features
* Valley map is rendered via SVG
* Map can be panned by clicking and dragging or by touching and dragging
* Map cannot be panned too far off screen
* Map can be zoomed in and out by clicking the zoom buttons in the top right or by using scroll wheel
* Each location has an invisible button that highlights when hovered/clicked
* When clicked, each location opens an iframe with the corresponding Living Valley entry in it
* Menu button opens a menu to switch between maps
* Menu, zoom control, location pop-up user interface style matches The Living Valley
* User can toggle location card numbers to show over the map
* User can highlight locations based on selected location trait, highlighted locations have an animated pulse

# Potential Features (TODO)
* Add animation (zoom in, zoom out, menu open, menu close, open Living Valley iframe, automatically pan map to bring Living Valley iframe into view)
* Add functionality to allow users to take notes at specific locations

# Known Bug(s)
* After moving the map with the location card numbers toggled off, toggling them on without moving the cursor does not update their positions until after they have reappeared.
