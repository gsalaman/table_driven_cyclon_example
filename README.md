# Loop consolidation notes

## Overview:
The cyclon eye itself is made up of a "bright" leading pixel, followed by a mid pixel, followed by a dim pixel.  These pixels travel first right until the leading pixel hits the right boarder, then reverse positions such that the dim pixel is on the far right.  We then travel these pixels across the display until we hit the left boarder, then reverse positions and continue right.

## Data used:
NUMPIXELS tells us how many pixels long our display is.  Currently 8.
CYLONSIZE tells how many of those pixels make up the cyclon eye.

pixelState is an array that tells us whether each pixel is a part of the cylon or part of the background.
cylonIndex

## Algorithm:
```
Initialize lights (setup)

While we've got space to shift lights right:   (meaning the far right pixel is still a background pixel)
  Copy all pixels one slot to the right (for loop)
  Set the far left pixel to be a background pixel.
  show the LEDs
  update the speed based on the pot
  check for button presses.  If there's one, update the color palette.
Then, after we can't go right anymore...
While we've got space to shift lights left: (meaning the far left pixel is still a background pixel)
  Copy all pixels one slot to the left (for loop)
  set the far right pixel to be a background pixel
  show the LEDs
  update the speed based on the pot
  check for button presses.  If there's one, update the color palette.
  ```
  
  First decomposition:
  
  

 
