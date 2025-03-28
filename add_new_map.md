# Brief Tutorial on Adding a New Map
As of the initial publication of this interactive map tool, there are two map images, the Valley from the base _Lure of the Valley_ campaign, and the Arcology from the _Legacy of the Ancestors_ expansion. There may be more maps added in the future, and I may not be around to do it. Hence, this tutorial.

### Step 1: Prepare and upload the map image and map select banner image
The map image should be a high-quality `.jpg` file, uploaded into the `Assets` folder. Keep a copy handy in an image editing software, because we will have to find certain coordinates later. In order to make some future steps easier, try to use an image that is at the same scale as the current images. The boxart banner image should be a `.jpg` with dimensions 380x140. Upload this to the Assets folder as well.

![image](https://github.com/user-attachments/assets/12b4fc7f-3ee6-4c1d-bb8f-8a53bd2f282b)
### Step 2: Modify `locations.js`
1. Background: `locations.js` is a JavaScript file that contains a single variable in it, but this variable is an array of dictionaries, where each dictionary represents one location, from across all (both) of the existing maps.
2. Add a comma after the last right curly bracket (`}`) but before the last right square bracket (`]`).
3. Append one new dictionary for each new location to the end of the array, making sure to include a comma after each one except for the final one.
4. Fill in all of the data fields for each new location dictionary.
    - `name` is the name of the location
    - `url` is the __last part__ of the associated Living Valley URL, e.g., `lone_tree_station` in the URL `https://thelivingvalley.earthbornegames.com/docs/campaign_guide/lone_tree_station`
    - `set` will be a new string, named by you. The current sets are named `valleyBase` and `legacyArcology`
    - `setCardNum` is an integer, and it represents the number of the location within its set, e.g., White Sky is card 1 in the Valley set
    - `isPivotal` is a Boolean, either true or false, depending on whether the location is a pivotal location or not
    - `x` and `y` represent the pixel coordinates of the center of the location icon on the map. You can estimate these now and fine tune them later
    - `presence` gives the presence of the location. This currently is not used
    - `trait1` through `trait5` are the location's traits. If a location has fewer than five traits, enter `null` for any unused trait slots

### Step 3: Duplicate `valley_map.html`
You'll want to copy the HTML file and give it a different name, appropriate for whatever map you're adding.

### Step 4: Modify the new HTML file
1. Line 13: Change the `id` from `valleyBody` to another appropriately named `somethingBody`
2. Line 23: Change the following values corresponding to the new map image
     - `width` is the total width in pixels of the map image, including the padding
     - `height` is the total height in pixels of the map image, including the padding
     - `x` is the negation of the left edge of the visible portion of the map (i.e., the width of the left padding)
     - `y` is the negation of the top edge of the visible portion of the map (i.e., the height of the top padding)
     - `href` should point to the new map image URL
3. Line 54: Change the `mapImageWidth` to give the width in number of pixels of the visible portion of the map (i.e. the width of the image with the width of the left and right padding subtracted)
4. Lines 84-87: Change the `topBound`, `leftBound`, `rightBound`, and `bottomBound`. These values represent how far you can drag the map off screen before the function prevents further dragging in that direction. The current maps are set to just allow the main parts of the map off screen
5. Line 195: Change the `mapImageWidth` to give the width in number of pixels of the visible portion of the map. This should match the value on Line 54
6. Lines 239-240: Change the `gradientOffset` values to match the negations of the `x` and `y` from Line 23 (e.g., if `x` is -1310, `gradientOffsetX` should be 1310)
7. Line 257: Note this and come back to it when we are fine tuning
8. Line 278: Note this and come back to it when we are fine tuning
9. Line 328: Note this and come back to it when we are fine tuning
10. Line 339: Note this and come back to it when we are fine tuning
11. Line 362-363: Change `gradientOffsetX` and `gradientOffsetY` to match the values in Lines 239-240
12. Line 473: Change `valleyBase` to match the `set` of the new map created in Step 2.4
13. Line 497: Change `valleyBase` to match the `set` of the new map created in Step 2.4
14. Line 813: Copy and paste the entire block above this and then modify it as follows
      - Change the comment at the top of the block of code to reflect the new map
      - Change all instances of the string `arcology` to a string that matches your new map. `arcology` and `valley` are taken by the existing maps
      - Change the `href` URL in the third line of the block so it points to the same name created in Step 3
      - Change the `src` in the tenth line of the block so it points to the correct banner image created in Step 1

### Step 5: Modify the old HTML files
Now that we have created a new link in the menu in Step 4.14, we need all of the maps to include that link. Copy that new block and paste it into Line 813 of both `valley_map.html` and `arcology_map.html`. Make sure the spacing matches the existing style.

### Step 6: Modify `styles.css`
Line 22: Copy and paste the whole block containing the `#valleyBody` rule, and rename it to match what you named the new body in Step 4.1. Select a `background-color` that will fade into the new map image

### Step 7: Fine tuning
1. Background: depending on how particular you are about how closely the location buttons match with the image of the locations, you may spend more or less time doing this. You may be happy with how the map looks already. If not, complete this step
2. Temporarily modify `styles.css` in the `.locationButton` block: change `fill-opacity` to be `40%`. This should show the buttons at all times
3. If the buttons look too large or too small, modify the numbers we skipped over in Steps 4.7 through 4.10. The easiest way to do this is just to go by trial and error
4. Modify the `x` and `y` values for the locations added in Step 2.4 to move the buttons exactly where they should be. This can be a very tedious process
5. Revert `styles.css` so the `fill-opacity` is `0%` again

And that's it! You should be done. Note that if this has already been done at least once and there are at least three existing maps, these same steps will be qualitatively correct, but some of the specific line numbers will be incorrect.
