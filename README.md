LATEST NOTES
===========================================================
Re-downloaded the original pizza image to get rid of blurriness. Added a pizza-sm image that is much more compressed and is used for the mover elements.

Please make sure you use my hosted website (www.swolebrain.com/mobile_portfolio) for the pagespeed insights test. My web server is running apache 2.2 with mod_pagespeed configured so it minifies, concatenates and embeds css files automatically so long as they are within certain length limits. I have pagespeed score of 99.

SEQUENTIAL NOTES
===========================================================
For the pagespeed part of the project, I did the following:

1) Added the media attribute to the css link which only applies to print media
2) Made sure all scripts were async, since none of them were scripts that manipulate the DOM
3) Shrank several of the images in photoshop so that they loaded faster and corresponded 
	better to their actual display sizes. This included creating a smaller version of the pizza 
	counter jpg for the portfolio page and leaving the larger one for the pizza page.
4) Auto compression, auto minification and css concatenation were already up and running on my web server

For the 60fps portion of the pizza project, I took the following steps:
1) Experimented with simply not running the update code on pizzas which were out of bounds of the screen. This didn't work <br>
2) Experimented with trying to do the more library-dependent part of the phase calculation outside the loop, couldn't get it to work <br>
3) Changed the domcontentloaded event handler to only add an appropriate amount of pizza dom elements (depending on
	screen size) rather than 200 of them. Even on a 1440p display all I had room for was 32 of them so 200 was way too much. <br>
4) (Second submission) In the function updatePositions, reduced number of calls to document.body.scrollTop <br>
5) (Second submission) Suggestion to restrict the number of pizzas to an adequate number other than 200 (depending on screen size)
	had already been observed for the first submission but was reviewed for second submission.  <br>
6) (Second submission) Removed call to updatePositions from generateSlidingPizzas and did the style.left code in the loop inside
	the first method in order to save on execution time when initially creating the sliding pizza dom elements (one pass through
	the n elements rather than two passes) <br>
7) (Second submission) Found out that the number of mover pizza columns wasn't being computed correctly on mobile and inserted a 
	quick hack to fix it (made it so number of columns couldn't be lower than 4) <br>
8) (Third submission) Added global variable to keep track of mover pizza elements so I didn't need to access the DOM for every scroll <br>
9) (Third submission) Hardcoded all the 5 possible phase values so i didn't have to call math.sin n times inside a loop <br>
10) (Third submission) Changed the movement of the pizzas from using style.left to using css translateX <br>
11) (Third submission) Added the backface visibility hack to the css for the movers <br>
12) (Third submission) Changed the row and column counting code from using screen width and height to using window width and height <br>
13) (Fourth submission) Fixed bug where all pizzas in a given column move in sync if the computed number of columns is 5.<br>
14) (Fifth submission) Added code comments and undid the compression to the pizza images

	
For the pizza resizing portion of the project, I simply moved the call to determineDx() and the calculation of newWidth to
outside the loop since the new width is the same for all pizzas given the same slider value. This brought down the execution time
to 2ms and change. Steps taken in additional submissions:
1) (Second submission) Changed queryselectorall calls to getElementsByClassName to improve performance
2) (Second submission) Reduced number of dom traversals in changePizzaSizes function by assigning document.getElementsByClassName("randomPizzaContainer") to a variable


HOW TO RUN
===========================================================
Go to http://http://www.swolebrain.com/mobile_portfolio/
 <br> <br>
Pagespeed insights link: https://developers.google.com/speed/pagespeed/insights/?url=http%3A%2F%2Fwww.swolebrain.com%2Fmobile_portfolio%2F&tab=mobile



