NOTES
===========================================================
For the pagespeed part of the project, I did the following:

1) Added the media attribute to the css link which only applies to print media
2) Made sure all scripts were async, since none of them were scripts that manipulate the DOM
3) Shrank several of the images in photoshop so that they loaded faster and corresponded 
	better to their actual display sizes. This included creating a smaller version of the pizza 
	counter jpg for the portfolio page and leaving the larger one for the pizza page.
4) Auto compression, auto minification and css concatenation were already up and running on my web server

For the 60fps portion of the pizza project, I took the following steps:
1) Experimented with simply not running the update code on pizzas which were out of bounds of the screen. This didn't work
2) Experimented with trying to do the more library-dependent part of the phase calculation outside the loop, couldn't get it to work
3) Changed the domcontentloaded event handler to only add an appropriate amount of pizza dom elements (depending on
	screen size) rather than 200 of them. Even on a 1440p display all I had room for was 32 of them so 200 was way too much.
	
For the pizza resizing portion of the project, I simply moved the call to determineDx() and the calculation of newWidth to
outside the loop since the new width is the same for all pizzas given the same slider value. This brought down the execution time
to 2ms and change.

HOW TO RUN
===========================================================
Go to http://http://www.swolebrain.com/mobile_portfolio/

pagespeed insights link: https://developers.google.com/speed/pagespeed/insights/?url=http%3A%2F%2Fwww.swolebrain.com%2Fmobile_portfolio%2F&tab=mobile
